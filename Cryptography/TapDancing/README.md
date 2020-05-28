# TJCTF2020

## Cryptography

### TapDancing - 25 Points

### Flag
M0RSEN0TB4SE3
### Deskripsi soal

Diberikan suatu [text](/text/tapdancing.txt) yang berisikan 0,1, dan 2 maka dapatkan flag


### Solusi
Dikarenakan hanya ada 0 1 dan 2 maka hanya ad 3 kemungkinan, seperti sandi morse hanya ada 3 kemungkinan dengan nilai antara " " , "." atau , "-"
maka dengan mencoba beberapa kemungkinan didapatkan kode morse sebagai berikut
```
.. ..... -.- --- - .- ..... . .--- ----. --- - ---..
```
Lalu bila kita decode kode morse tersebut maka didapatkan flagnya
