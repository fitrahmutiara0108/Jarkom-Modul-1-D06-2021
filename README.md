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
## Soal 7
## Soal 8
## Soal 9
## Soal 10
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
