# TJCTF2020

## Forensics

### Fowarding - 10 Points

### Flag
tjctf{n1c3_j0b_with_lf1_2_rc3}
### Deskripsi soal

Diberikan suatu Website yang memiliki 6 file yang bisa di read, dapatkan flagnya

### Solusi
Setelah mencoba memasukkan file yang didisplaykan, terlihat bahwa terdapat kelemahan LFI (Local File Intursion) maka dicoba untuk melakukan dirb (brute force) untuk mendapatkan suatu direktori tersembunyi, setelah dapat direktorinya, <i>[dir]/flag.php </i> Maka terdapat flag dalam base64, decode dan dapatkan flagnya
