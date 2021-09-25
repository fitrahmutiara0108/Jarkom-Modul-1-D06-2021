# Jarkom-Modul-1-D06-2021
Anggota :
- Fitrah Mutiara 05111940000126
- Ahdan Amanullah Irfan Muzhaffar 05111940000197
- Dewi Mardani 05111940000225

## Soal 1
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"! 
Jawaban: Kita bisa melakukan `Follow TCP stream` pada salah satu paket dan ditemukan bahwa ichimarumaru.tech menggunakan webserver nginx

![image](https://user-images.githubusercontent.com/58657135/134433247-df639a02-11f8-4c9d-bd76-245e68429efb.png)

atau kita bisa liat langsung dari website nya sendiri:

![image](https://user-images.githubusercontent.com/58657135/134433547-f24913db-c160-4040-85f1-ee8fb6c04132.png)
## Soal 2
Temukan paket dari web-web yang menggunakan basic authentication method!

Jawaban: Salah satu contoh web yang menggunakan basic authentication method adalah basic.ichimarumaru.tech (bisa dilihat pada gambar dibawah). Jika kita liat deskripsi dari suatu paket (dengan menggunakan filter `http.authbasic`) kita dapat menemukan paket yang menggunakan Basic Authentication Method.

![image](https://user-images.githubusercontent.com/58657135/134433798-4d6cdd92-f01d-47a8-95d0-57287e8fa3f7.png)
## Soal 3
Ikuti perintah di basic.ichimarumaru.tech! Username dan password bisa didapatkan dari file .pcapng!

Jawaban: Karena basic.ichimarumaru.tech menggunakan Basic Authenthication Method maka kita bisa menggunakan filter `http.authbasic` dan bisa mendapatkan isi Credentials yang dibutuhkan.

![image](https://user-images.githubusercontent.com/58657135/134434142-9ab2f306-2aab-4899-b400-660e3dbe5f48.png)

Lalu saat kita login dengan menggunakan User dan Password yang telah didapatkan (User:`kuncimenujulautan`, Pass:`tQKEJFbgNGC1NCZlWAOjhyCOm6o3xEbPkJhTciZN`) kita disuruh untuk memasukkan konfigurasi pengkabelan T568A:

![image](https://user-images.githubusercontent.com/58657135/134434411-59a7f851-db78-4cfa-b7be-7e66307bf28f.png)
## Soal 4
Temukan paket mysql yang mengandung perintah query select!

Jawaban: Kita bisa menggunakan filter `mysql.query` yang mengandung kata `select` atau `SELECT` karena query select bisa ditemukan dituliskan menggunakan huruf kecil semua atau kapital semua sehingga agar menampilkan paket yang menggunakan query select maka kita menggunakan filter `mysql.query contains "select" || mysql.query contains "SELECT"`

![image](https://user-images.githubusercontent.com/58657135/134434916-0927948c-cf84-4582-ad6f-38e8a4e58c21.png)
## Soal 5
Login ke portal.ichimarumaru.tech kemudian ikuti perintahnya! Username dan password bisa didapat dari query insert pada table users dari file .pcap!

Jawaban : Untuk mencari User dan Password dari web portal.ichimarumaru.tech kita bisa menggunakan filter `mysql.query` dan mencari paket dengan query `insert`:

![image](https://user-images.githubusercontent.com/58657135/134435069-3d2829f6-3488-404b-8258-ff925bbadf92.png)

didapatkan bahwa Username: `akakanomi` dan Password: `pemisah4lautan` 

Lalu kita disuruh untuk memasukkan konfigurasi pengkabelan T568B:

![image](https://user-images.githubusercontent.com/58657135/134435184-523625ed-2e60-4f6d-8e02-8b7e24c1d9ae.png)
## Soal 6
Cari username dan password ketika melakukan login ke FTP Server!

Jawaban : 
1. Untuk mendapatkan username, kita dapat mengisi display filter dengan `ftp contains "user"` dan didapatkan bahwa usernamenya adalah `secretuser `
<img width="942" alt="gambar1" src="https://user-images.githubusercontent.com/73428220/134766335-f3890a68-5876-4d5d-a1d1-bdd2498bc641.png">
<img width="732" alt="gambar1" src="https://user-images.githubusercontent.com/73428220/134766373-833fddf8-a7de-4608-bc6f-31fbb7eec92f.png">

2. Untuk mendapatkan password, kita dapat melakukan filter dengan `ftp contains "PASS"` dan didapatkan bahwa passwordnya adalah `aku.pengen.pw.aja `
 <img width="943" alt="gambar2" src="https://user-images.githubusercontent.com/73428220/134766260-57458c36-e7c5-4ad7-8142-b5133eed47d9.png">
<img width="702" alt="gambar2" src="https://user-images.githubusercontent.com/73428220/134766272-e769e634-6266-4cdf-a214-2c74445574cf.png">

## Soal 7
Ada 500 file zip yang disimpan ke FTP Server dengan nama 0.zip, 1.zip, 2.zip, ..., 499.zip. Simpan dan Buka file pdf tersebut. (Hint = nama pdf-nya "Real.pdf")

Jawaban :
1. Untuk dapat menemukan file, kita dapat mengisi display filter dengan `tcp contains "Real.pdf"` sesuai dengan hint yang telah diberitahu soal
<img width="943" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766617-1a0a941e-e814-42f9-a742-95db33f9b12a.png">
2. Klik kanan pada baris pertama -> klik follow -> TCP STREAM
<img width="956" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766642-152cde46-7b1b-4632-9f81-fa914944ef9b.png">
3. Ubah tampilan data dari ASCII  menjadi RAW 
- Saat masih dalam bentuk ASCII :
<img width="943" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766678-507da4a2-1146-4403-9b86-faa837ecf3d7.png">
- Setelah diubah ke dalam bentuk RAW :
<img width="951" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766727-75910ef0-23a6-4a45-8d7d-988a2b3a8f63.png">
4. Save file ke dalam documents komputer dengan format Real.zip 
<img width="470" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766774-3831c3ad-94a0-477a-8d09-56eb3981f7c4.png">
6. Extract kemudian buka file Real.zip yang telah disimpan tadi di dalam documents
<img width="587" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766798-c479afd8-0557-4acf-a43b-cf12a08585dc.png">
8. Maka file Real.pdf akan muncul dan berikut merupakan hasilnya
<img width="547" alt="gambar3" src="https://user-images.githubusercontent.com/73428220/134766824-8cd64ec9-1089-485d-a80a-b679ee9c318c.png">


## Soal 8
Cari paket yang menunjukan pengambilan file dari FTP tersebut!(Soal Bonus)

Jawaban :
1. Untuk mendapatkan upload file ke FTP server kita dapat menjalankan mengisi display filter dengan `ftp contains "STOR"`
2. Keluaran yang dihasilkan adalah sebagai berikut
<img width="940" alt="gambar6" src="https://user-images.githubusercontent.com/73428220/134767746-2b3c5833-260a-46c6-aefd-e37bc08055a1.png">

## Soal 9
Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!

Jawaban :
1. Untuk dapat menemukan file, kita dapat mengisi display filter dengan `ftp-data.command contains "secret.zip"`
<img width="924" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134766971-40499ec0-7b83-4147-9ad5-6196eecc1eae.png">
2. Klik kanan pada baris pertama -> klik follow -> TCP STREAM
<img width="935" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134766999-5a8c9bff-8337-4756-88fe-76cc9fe11c68.png">
3. Ubah tampilan data dari ASCII menjadi RAW
- Saat masih dalam bentuk ASCII :
<img width="958" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134767035-aba189a9-8e81-4d07-8aaa-ce48d28cf837.png">
- Setelah diubah ke dalam bentuk RAW :
<img width="954" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134767048-4909b218-48e2-483c-96a5-172ba600d1b9.png">
4. Save file ke dalam documents komputer dengan format secret.zip
<img width="469" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134767070-b2b74588-6d63-46c1-84e2-bc6c7b73889a.png">
6. Buka file secret.zip yang telah disimpan tadi di dalam documents, maka akan keluar tampilan sebagai berikut
<img width="248" alt="gambar4" src="https://user-images.githubusercontent.com/73428220/134767130-6b72eb87-e899-479f-9828-c06c8bd3cdd7.png">

## Soal 10
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!

Jawaban : 
1. Untuk dapat menemukan file, kita dapat mengisi display filter dengan `ftp-data.command contains "history.txt"`
<img width="947" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767383-b893117e-b16e-46cc-909e-f44e8566fa69.png">
2. Klik kanan pada baris -> klik follow -> TCP STREAM
<img width="900" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767491-3add329c-77cf-4cce-97c8-0be22df88568.png">
3. Akan muncul tampilan sebagai berikut, dan pada tampilan ini terdapat hint bahwa key="$(tail -1 bukanapaapa.txt)"
<img width="396" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767444-11e66086-61b9-44ab-873e-47bd6eecba05.png">
4. Filter kembali untuk mendapatkan file bukanapaapa.txt dengan `ftp-data.command contains "bukanapaapa.txt"`
<img width="678" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767550-f8ba4fab-085a-4a89-ba83-d6a1ee89d6a0.png">
6. Klik kanan pada baris -> klik follow -> TCP STREAM
<img width="948" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767536-6500a1ba-335a-40ba-ab39-4843a0244b58.png">
7. Maka akan muncul password untuk membuka folder yaitu d1b1langbukanapaapajugagapercaya
<img width="321" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767565-a5d2afd7-5c89-4ab4-a883-f4c6aa3c4862.png">
8. Ketika berhasil membuka folder maka didapatkan isi file sebagai berikut
<img width="239" alt="gambar5" src="https://user-images.githubusercontent.com/73428220/134767607-4658c937-e6b3-48fa-b505-8ab17bbf9602.png">

## Soal 11
Filter sehingga wireshark hanya mengambil paket yang berasal dari port 80!
dengan menggunakan `src port 80`
![image](https://user-images.githubusercontent.com/81247727/134287746-842c7cea-e19a-48b7-9030-5b949942f1b4.png)
## Soal 12
Filter sehingga wireshark hanya mengambil paket yang mengandung port 21!
- dengan menggunakan `port 21`
![image](https://user-images.githubusercontent.com/81247727/134287766-323fcf01-94dd-46d7-ab4a-26e020208aaa.png)
- setelah dicoba menggunakan `ftp localhost` pada windows powershell, muncul seperti ini:
![image](https://user-images.githubusercontent.com/81247727/134287845-92511731-c8ce-47ad-939d-ef94e0e6f57e.png)
## Soal 13
Filter sehingga wireshark hanya menampilkan paket yang menuju port 443!
dengan menggunakan `dst port 443`
![image](https://user-images.githubusercontent.com/81247727/134287871-5de946b5-ad3e-4853-82f1-dd87e06465b3.png)
## Soal 14
Filter sehingga wireshark hanya mengambil paket yang tujuannya ke kemenag.go.id!
dengan menggunakan `host kemenag.go.id`
![image](https://user-images.githubusercontent.com/81247727/134287894-740a8be9-c897-4d1a-81cc-6e57260dd230.png)
## Soal 15
Filter sehingga wireshark hanya mengambil paket yang berasal dari ip kalian!
dengan menggunakan `scr host 192.168.65.188`
cek ip address melalui command prompt : ipconfig
![image](https://user-images.githubusercontent.com/81247727/134287923-7847b121-436a-456c-868e-c1e029895412.png)

## Kendala yang dialami
1. Koneksi internet kurang mendukung
2. Ketika mencoba filter, paket terkadang tidak muncul
