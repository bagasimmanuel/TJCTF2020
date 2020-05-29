# TJCTF2020

## Forensics

### Fowarding - 10 Points

### Flag
tjctf{inevitable890898}
### Deskripsi soal

Login pada suatu Website


### Solusi
Jika melihat page source maka terlihat untuk setiap button di click akan melakukan function checkUsername dimana pada function checkUsername hanya mencocokan suatu nilai hash, maka solusinya adalah dengan melakukan decrypt(mencocokan nilai) hash MD5 yang ada
