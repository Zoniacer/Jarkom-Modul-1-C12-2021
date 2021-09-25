# Jarkom-Modul-1-C12-2021

### C12
Daffa Amanullah Setyawan - 05111940000071\
Satrio Hanif Wicaksono - 05111940000103\
Shidqi Dhaifullah - 05111940000108

### PRAKTIKUM MODUL 1

1. Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 
Jawab
http.host == ichimarumaru.tech
nginx/1.18.0 (Ubuntu)

2. Temukan paket dari web-web yang menggunakan basic authentication method!
Jawab
http.authbasic

3. Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!
Jawab
http.host == basic.ichimarumaru.tech




4. Temukan paket mysql yang mengandung perintah query select!
Jawab
mysql.query matches select


5. Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!
Jawab
mysql.query matches insert

Username = akakanomi, password pemisah4lautan

6. Cari username dan password ketika melakukan login ke FTP Server!
Jawab
Wireshark filter expression: ftp.request.command == USER || ftp.request.command == PASS
Didapat : username = secretuser, password = aku.pengen.pw.aja

^ Gambar 6 Memasukkan filter ftp.request.command == USER || ftp.request.command == PASS

7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
Jawab
Wireshark filter expression: frame contains "Real.pdf"

^ Gambar 7.1 Memasukkan filter frame contains "Real.pdf"

^ Gambar 7.2 Klik kanan > Follow > TCP Stream 

^ Gambar 7.3 Tampilan data dalam bentuk ASCII

^ Gambar 7.4 Ubah Data menjadi Raw > Save as > “Real.pdf” > Save

^ Gambar 7.5 Tampilan Isi pdf
8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
Jawab
Wireshark filter expression: ftp.response.code == 150 || ftp.response.code == 226

9. Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
Jawab
Wireshark filter expression: ftp-data.command contains "secret.zip"

^ Gambar 9.1 Memasukkan filter ftp-data.command contains "secret.zip"

^ Gambar 9.2 Klik kanan > Follow > TCP Stream > ASCII <-> Raw > Save as > “secret.zip” > save

^ Gambar 9.3 Membuka file secret.zip

10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
Jawab
wireshark filter expression: ftp-data.command contains “history.txt”

wireshark filter expression: ftp-data.command contains “bukanapaapa.txt”



^ Gambar 10.2 Memasukkan pass “d1b1langbukanapaapajugagapercaya”

^ Gambar 10.3 Tampilan Wanted.pdf yang ada dalam secret.zip
11. Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80! 
Jawab
src port 80

12. Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
Jawab
port 21

13. Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
Jawab
tcp port 443

14. Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
Jawab
dst host kemenag.go.id

15. Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
Jawab
src host <ip address>

