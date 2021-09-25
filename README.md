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

##### 6. Cari username dan password ketika melakukan login ke FTP Server!
Jawab
> Wireshark filter expression: ftp.request.command == USER || ftp.request.command == PASS

<img src="https://user-images.githubusercontent.com/73422724/134753178-685f0c79-c349-4ff3-ab2c-ab1020369de0.png" width="500">
^ Gambar 6 Memasukkan filter ftp.request.command == USER || ftp.request.command == PASS

Didapat : username = secretuser, password = aku.pengen.pw.aja


##### 7. Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")
Jawab
> Wireshark filter expression: frame contains "Real.pdf"

<img src="https://user-images.githubusercontent.com/73422724/134753191-9c326aa9-0a3c-4f84-94da-bb5dff48124a.png" width="500">
^ Gambar 7.1 Memasukkan filter frame contains "Real.pdf"

<img src="https://user-images.githubusercontent.com/73422724/134753197-cffc5e4a-05f1-4a7a-810a-df94de2c2980.png" width="500">
^ Gambar 7.2 Klik kanan > Follow > TCP Stream

<img src="https://user-images.githubusercontent.com/73422724/134753202-df6a598d-748c-44ce-bdbd-c8fd72ff8cb1.png" width="500">
^ Gambar 7.3 Tampilan data dalam bentuk ASCII

<img src="https://user-images.githubusercontent.com/73422724/134753270-edd54329-75ea-4b0b-84d6-b7dd29a08bf4.png" width="500">
^ Gambar 7.4 Ubah Data menjadi Raw > Save as > “Real.pdf” > Save

<img src="https://user-images.githubusercontent.com/73422724/134753238-096cfb43-3d9f-4605-98a1-a94697767503.png" width="500">
^ Gambar 7.5 Tampilan Isi pdf

##### 8. Cari paket yang menunjukan pengambilan file dari FTP tersebut!
Jawab
> Wireshark filter expression: ftp.response.code == 150 || ftp.response.code == 226

<img src="https://user-images.githubusercontent.com/73422724/134753586-8924ac48-99b3-471f-be0e-4b6a57918fa5.png" width="500">
^ Gambar 8 Memasukkan filter frame contains "ftp.response.code == 150 || ftp.response.code == 226"

##### 9. Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
Jawab
> Wireshark filter expression: ftp-data.command contains "secret.zip"

<img src="https://user-images.githubusercontent.com/73422724/134753841-8a20c4aa-8a18-499b-a6d7-84ae2ae90bde.png" width="500">
^ Gambar 9.1 Memasukkan filter ftp-data.command contains "secret.zip"

<img src="https://user-images.githubusercontent.com/73422724/134753855-860a5a1a-28ad-49cb-bccd-108822401467.png" width="500">
^ Gambar 9.2 Klik kanan > Follow > TCP Stream > ASCII <-> Raw > Save as > “secret.zip” > save

<img src="https://user-images.githubusercontent.com/73422724/134753892-6986d995-c96b-43af-8575-b0ba39db4e39.png" width="500">
^ Gambar 9.3 Membuka file secret.zip

##### 10. Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
Jawab
> wireshark filter expression: ftp-data.command contains “history.txt”

<img src="https://user-images.githubusercontent.com/73422724/134753969-73167e6e-136a-4a25-a978-acb775e47ec3.png">
^ Gambar 10.1 Memasukkan filter ftp-data.command contains “history.txt”

> wireshark filter expression: ftp-data.command contains “bukanapaapa.txt”

Didapat password : d1b1langbukanapaapajugagapercaya

<img src="https://user-images.githubusercontent.com/73422724/134753901-a7bd9e22-7b71-4f09-9147-71329d21d2b7.png" width="500">
^ Gambar 10.2 Memasukkan pass “d1b1langbukanapaapajugagapercaya”

<img src="https://user-images.githubusercontent.com/73422724/134753904-b6992a14-7df1-4f54-b807-f196fc81aa8e.png" width="500">
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

