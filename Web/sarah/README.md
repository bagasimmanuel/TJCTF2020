# TJCTF2020

## Web

### Sarah Palin FanPage - 35 Points

### Flag
tjctf{wkDd2Pi4rxiRaM5lOcLo979rru8MFqVHKdTqPBm4k3iQd8n0sWbBkOfuq9vDTGN9suZgYlH3jq6QTp3tG3EYapzsTHL7ycqRTP5Qf6rQSB33DcQaaqwQhpbuqPBm4k3iQd8n0sWbBkOf}
### Deskripsi soal

Diredirect ke suatu Website, dimana ketika kita ingin masuk ke VIP area harus melakukan like 10 moment, dimana setiap like > 5 , akan muncul pop up yang memblokir agar tidak bisa melakukan like lagi

### Solusi
Yang pertama kali dilakukan adalah mencoba like, ketika di block, maka saya mencoba melakukan like di browser lain, ternyata like sebelumnya tidak tersimpan (data disimpan secara lokal di browser) --> Session, maka ketika melakukan Inspect Elemen, pada bagian storage Terdapat nilai suatu Session dengan value
```
eyIxIjpmYWxzZSwiMiI6ZmFsc2UsIjMiOmZhbHNlLCI0IjpmYWxzZSwiNSI6ZmFsc2UsIjYiOmZhbHNlLCI3IjpmYWxzZSwiOCI6ZmFsc2UsIjkiOmZhbHNlLCIxMCI6ZmFsc2V9
```
Setelah mencoba melakukan decode pada beberapa decoder maka didapatkan bahwa disini digunakan base64 Encoding maka ketika di decode didapatkan
```
{"1":false,"2":false,"3":false,"4":false,"5":false,"6":false,"7":false,"8":false,"9":false,"10":false}
```
Maka sekarang yang perlu dilakukan adalah merubah nilai false menjadi true, lalu melakukan encoding kembali ke base 64
```
eyIxIjp0cnVlLCIyIjp0cnVlLCIzIjp0cnVlLCI0Ijp0cnVlLCI1Ijp0cnVlLCI2Ijp0cnVlLCI3Ijp0cnVlLCI4Ijp0cnVlLCI5Ijp0cnVlLCIxMCI6dHJ1ZX0=
```
Paste Value tersebut ke Value Session pada Storage Maka setelah itu ktia dapat mengakses VIP Area dan mendapatkan Flag
