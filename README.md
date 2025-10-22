# **lontongsagu (Apache Answer) : Self-hosted**

<img width="1280" height="720" alt="lontongsagu" src="https://github.com/user-attachments/assets/93ca633c-5398-42e8-bcdd-1a02ea372521" />

| [Sekilas Tentang Apache Answer](#sekilas-tentang-apache-answer) | [Instalasi](#instalasi) | [Konfigurasi](#konfigurasi) | [Cara Pemakaian](#cara-pemakaian) | [Pembahasan](#pembahasan) | [Kesimpulan](#kesimpulan) | [Referensi](#referensi) |
|------------------------------------------------------------------|--------------------------|-----------------------------------------------|-----------------------------------|----------------------------|---------------------------|--------------------------|

## Anggota Kelompok 2_P1

| No | Nama Anggota                       | NIM           |
|----|------------------------------------|---------------|
| 1  | Mutia Saniya Rahma                | G6401231002    |
| 2  | Quina Rizky Dae Yuena Siregar     | G6401231013    |
| 3  | Danella Nur Aisyah Latief         | G6401231041    |
| 4  | Ghanianda Wafiqarifah             | G6401231126    |
| 5  | Winanci Zahrawaini Setiawan       | G6401231158    |


## Sekilas Tentang lontongsagu (Apache Answer)

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

lontongsagu (Apache Answer) adalah platform Q&A (Question and Answer) berbasis open source yang dapat di-host secara mandiri (self-hosted). Aplikasi ini mendukung berbagai fitur interaktif seperti sistem pertanyaan dan jawaban, komentar, voting, serta penggunaan tag untuk mengelompokkan topik. Dengan dukungan fitur tersebut, platform ini sangat cocok digunakan untuk membangun forum diskusi internal suatu organisasi maupun komunitas publik yang lebih luas.

### Fitur utama:
- Posting pertanyaan & jawaban
- Sistem voting (upvote & downvote)
- Tagging untuk pengelompokan topik pertanyaan
- Badges, kumpulan achievement kegiatan user di platform
### Sebagai Admin :
- Mengelola pertanyaan, jawaban, dan komentar
- Menambahkan atau menghapus tag
- Mengatur pengguna (menambah, menonaktifkan akun, atau mengubah peran)
- Melakukan konfigurasi sistem, seperti SMTP atau pengaturan tampilan
### Sebagai User :
- Membuat dan menjawab pertanyaan
- Memberi komentar dan vote
- Mengikuti tag tertentu sesuai minat
- Meng-edit profil pribadi

## Instalasi

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

Kebutuhan Sistem
- Unix, Linux, MacOS atau Windows
- Langkah instalasi dalam CLI
- Docker
- Microsoft Azure
- Apache

### Setup Server 
1. Login Microsoft Azure (https://portal.azure.com/#home)
   
2. Klik Virtual Machines
<img width="1599" height="619" alt="image" src="https://github.com/user-attachments/assets/2365e20c-d3fc-4094-b193-dbdd32735262" />

3. Klik Create
<img width="1598" height="573" alt="image" src="https://github.com/user-attachments/assets/3d9bd87e-d660-435a-aecb-e5745b3de833" />

4. Klik Virtual Machines
<img width="1594" height="741" alt="image" src="https://github.com/user-attachments/assets/a685b377-57b0-4798-aefb-34fe63f64cef" />

5. Setting 
<img width="1328" height="717" alt="image" src="https://github.com/user-attachments/assets/05b0f3d8-9784-41aa-a7ed-eb7df6d623fa" />

Saran: gunakan password jika ingin mudah

seperti contoh di bawah ini

<img width="1019" height="636" alt="image" src="https://github.com/user-attachments/assets/c6211b46-cb33-4b90-a2a9-6073f8220e0e" />


### Proses Instalasi:

1. Login ke server menggunakan SSH
```bash
ssh ondeonde@20.196.129.189
```

2. Memastikan paket sistem yang digunakan up-to-date dan install kebutuhan sistem
```bash
sudo apt update && sudo apt upgrade -y
sudo apt install docker.io docker-compose -y
```

3. Aktifkan Docker service dan jalankan
 ```bash
sudo systemctl enable docker --now
```

4. Mengambil kode Apache Answer dari Github ke VM 
 ```bash
git clone https://github.com/apache/answer.git
cd answer
```

5. Menjalankan Apache Answer di background dan cek status 
```bash
sudo docker-compose up -d
```

6. Verifikasi container Docker yang sedang berjalan
```bash
sudo docker ps
```

7. Kunjungi alamat IP web server kita untuk meneruskan instalasi
Link : https://answer.apache.org/docs/installation
<img width="1593" height="806" alt="image" src="https://github.com/user-attachments/assets/22f6d9fd-be83-44c0-a73d-e0c992e8942a" />

8. Install steps Apache Answer
   
   - Step 1: Choose the language
<img width="939" height="365" alt="image" src="https://github.com/user-attachments/assets/dea3d4d0-ab97-41a6-97d9-8d27c06f8810" />

   - Step 2: Config database
<img width="958" height="553" alt="image" src="https://github.com/user-attachments/assets/46575612-4037-4a83-b352-eacfe7698847" />

   - Step 3: Create configuration file
<img width="934" height="379" alt="image" src="https://github.com/user-attachments/assets/09cf5bb8-94a2-4dfd-aac5-793af7ff5c08" />

   - Step 4: Fill in basic information
<img width="674" height="640" alt="image" src="https://github.com/user-attachments/assets/47b75b89-44c7-4dde-8bf3-4196374ab1e8" />

   - Step 5: Complete
<img width="667" height="308" alt="image" src="https://github.com/user-attachments/assets/7d6e9d15-fa62-48af-9be6-ca94a57487d0" />

### Setup Domain 

Buka www.domainesia.com

<img width="1600" height="1041" alt="image" src="https://github.com/user-attachments/assets/80349d22-834b-49e8-adfb-2b02898f4fa8" />

<img width="1600" height="432" alt="image" src="https://github.com/user-attachments/assets/4e8e8290-d2a9-429a-bb83-5c9647176097" />

### Network Setting

1. Buka Microsoft Azure -> login -> klik server yang telah kamu buat

<img width="1253" height="707" alt="image" src="https://github.com/user-attachments/assets/e017336d-c59a-4ed8-a096-45206bddcbcc" />

2. Pilih Network -> Network Setting
   
<img width="267" height="652" alt="image" src="https://github.com/user-attachments/assets/b3d73177-2431-418d-a51d-1e9b488bca3e" />

3. Create New Port Rule

   <img width="1595" height="642" alt="image" src="https://github.com/user-attachments/assets/11a921ca-9e3c-481b-8bde-c31e1c2f438d" />

4. Pilih Inbound Port Rule

   <img width="1587" height="303" alt="image" src="https://github.com/user-attachments/assets/5b17bb27-e278-4667-be0f-d83f99e167de" />

   Setting : untuk menambahkan http (80) dan https (443)
   
   <img width="579" height="687" alt="image" src="https://github.com/user-attachments/assets/ae204111-6a7d-49a5-95e6-478374f15eec" />
   
   Akan muncul tampilan seperti di bawah ini :
   
   <img width="1250" height="260" alt="image" src="https://github.com/user-attachments/assets/88336abf-6cd0-476b-9748-857b537969ee" />


### Setting HTTP dan HTTPS di Command Prompt

1. Login server 
Masuk ke server VM Azure lewat SSH sebagai user ondeonde
   ```bash
   ssh ondeonde@20.196.129.189
   ```
   masukkan password jika menggunakan password saat membuat server
   
3. Pasang SSL gratis dari Let's Encrypt untuk domain tanya.lontongsagu.web.id dan otomatis konfigurasi SSL di Apache
   ```bash
   sudo apt update
   sudo apt install certbot python3-certbot-nginx   # kalau pakai Nginx
   sudo apt install certbot python3-certbot-apache  # kalau pakai Apache
   ```
   
4. Mengecek proses apa yang sedang memakai port (biasanya Nginx atau Apache)
   
   ```bash
   sudo lsof -i :80  # kalau http
   sudo lsof -i :443 # kalau https
   ```
  
5. Edit konfigurasi VirtualHost SSL untuk menambahkan ProxyPass ke aplikasi di port 9080 agar http (80) dan https (443) bisa di-access
   ```bash
   sudo nano /etc/apache2/sites-enabled/000-default-le-ssl.conf
   ``` 
   edit seperti di bawah ini
   
   <img width="770" height="597" alt="Screenshot 2025-09-26 065601" src="https://github.com/user-attachments/assets/7bbca66c-d66a-43ac-b5f1-21c9992d89a2" />

6. Tes apakah konfigurasi Apache valid setelah semua perubahan
   ```bash
   sudo apache2ctl configtest
   ```
   
7. Tes di Browser
   
http  : http://tanya.lontongsagu.web.id
   
https : https://tanya.lontongsagu.web.id
   
Tanpa semua yang di atas : tanya.lontongsagu.web.id


## Konfigurasi

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

![WhatsApp Image 2025-10-23 at 00 02 10_a75d3c2f](https://github.com/user-attachments/assets/303d6aa7-c18a-495c-885c-8f1cb4b51e85)


  | Variabel         | Nilai Contoh          | Fungsi                                                   |
  |-------------------|-----------------------|-----------------------------------------------------------|
  | SMTP_HOST         | smtp.gmail.com        | Alamat server SMTP Gmail                                 |
  | SMTP_PORT         | 587                   | Port untuk koneksi TLS                                   |
  | SMTP_USERNAME     | email pengirim       | Digunakan untuk autentikasi SMTP                         |
  | SMTP_PASSWORD     | (disembunyikan)      | Password atau App Password untuk login SMTP              |
  | SMTP_FROM         | email pengirim       | Alamat yang tampil sebagai pengirim                      |
  | SMTP_TLS          | true                  | Mengaktifkan enkripsi TLS                                |

Ditambahkan konfigurasi SMTP, memungkinkan aplikasi mengirimkan email secara otomatis menggunakan layanan server email. Dalam konteks ini, SMTP (Simple Mail Transfer Protocol) menjadi penghubung antara server aplikasi dan server email, seperti Gmail.

Variabel SMTP_HOST dan SMTP_PORT menentukan alamat dan jalur komunikasi dengan server email. SMTP_USERNAME dan SMTP_PASSWORD digunakan untuk proses autentikasi agar server mengizinkan pengiriman email. SMTP_FROM menunjukkan alamat email yang akan tampil sebagai pengirim. Sementara itu, SMTP_TLS mengaktifkan lapisan keamanan tambahan sehingga proses pengiriman email lebih aman dan terenkripsi.

Dengan konfigurasi ini, aplikasi dapat mengirimkan notifikasi, verifikasi akun, atau pesan otomatis lainnya tanpa perlu intervensi manual. Selain Gmail, SMTP juga dapat dikonfigurasi dengan penyedia email lainnya sesuai kebutuhan.

## Cara Pemakaian

### Cara Pemakaian Sebagai User

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

1. Akses Halaman Web
   
   Buka domain yang telah dikonfigurasi, contoh:
```bash
https://tanya.lontongsagu.web.id
```

2. Login/Registrasi
   
- Pengguna baru dapat membuat akun melalui email atau login langsung dengan Google / GitHub (jika sudah diaktifkan)
  
Tampilan user sign-in
<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/47b76234-b801-4b18-b278-b111731f4148" />
Tampilan user log-in
<img width="1918" height="830" alt="image" src="https://github.com/user-attachments/assets/4322c203-e651-497e-a1c8-49000ba45561" />

3. Halaman Utama (Dashboard)
- Tampilan User
Setelah login, pengguna akan diarahkan ke halaman utama yang menampilkan daftar pertanyaan terbaru dari komunitas. Di bagian atas terdapat menu navigasi untuk berpindah antara Questions, Tags, Users, dan Badges.
Pengguna bisa membuat pertanyaan baru dengan menekan tombol Create, kemudian mengisi judul, isi pertanyaan, serta menambahkan tag agar mudah ditemukan oleh pengguna lain. 
<img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/f51ee356-7385-48ac-a13b-1a9e506d336e" />

4. Membuat Pertanyaan/Ask a Question
- Klik tombol "Create"

5. Menjawab & Memberi Komentar
- User lain dapat memberikan jawaban dan komentar pada pertanyaan
<img width="1918" height="788" alt="image" src="https://github.com/user-attachments/assets/2d4024d0-8f66-4043-90fc-5fa613531215" />
<img width="1918" height="834" alt="image" src="https://github.com/user-attachments/assets/e63ecd21-d6d7-47ab-9efe-f7314e2a3b0c" />

- Jawaban dapat diberi vote dan melihat jumlah tayangan pertanyaan
<img width="1919" height="831" alt="image" src="https://github.com/user-attachments/assets/cbcd79b4-1f76-4b2f-864a-66107f657a6f" />

6. Tag dan Kategorisasi

Menu Tags berfungsi untuk menampilkan semua kategori topik yang ada di dalam forum.
Setiap pertanyaan dapat memiliki satu atau lebih tag, sehingga pengguna lebih mudah menemukan topik sesuai minat atau bidang keahliannya.
   <img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/5c8dcf70-3f5b-454d-9c79-55e61ef7527e" />

7. Sistem Pengguna dan Peringkat

Melalui menu Users, pengguna dapat melihat daftar anggota komunitas yang terdaftar, lengkap dengan reputasi dan badge yang telah diperoleh.
Semakin aktif seorang pengguna berpartisipasi dalam forum (misalnya dengan menjawab, memberi vote, atau membuat pertanyaan berkualitas), maka reputasi dan penghargaan yang didapatkan akan semakin tinggi.
<img width="1919" height="827" alt="image" src="https://github.com/user-attachments/assets/719a1124-a260-43e0-968a-be8cc5bc948e" />

8. Fitur Badges (Penghargaan/Achievement)

Bagian Badges menampilkan kumpulan penghargaan (achievement) yang diberikan kepada pengguna atas aktivitas tertentu di platform.
Tujuannya adalah untuk memberikan motivasi dan apresiasi kepada pengguna aktif yang berkontribusi positif dalam komunitas.
Beberapa jenis badge yang tersedia antara lain:

- Getting Started : mencakup aktivitas awal pengguna, seperti membuat profil (Autobiographer), mengedit konten (Editor), memberi vote pertama (First Upvote), atau memberi reaksi (First Reaction).

- Community : diberikan bagi pengguna yang membantu menyelesaikan pertanyaan, seperti Solved atau Scholar.

- Posting : penghargaan untuk kualitas pertanyaan dan jawaban, seperti Good Answer, Great Answer, Nice Question, dan Great Question.

- Badge-badge ini muncul otomatis ketika pengguna mencapai kriteria tertentu, dan dapat dilihat melalui ikon trophy di bagian atas halaman.
<img width="1919" height="811" alt="image" src="https://github.com/user-attachments/assets/79b266fa-829f-4276-ac57-c68c6b352a69" />
<img width="1903" height="833" alt="image" src="https://github.com/user-attachments/assets/e6d18c51-807f-4cdf-af85-7874002b892f" />

### Cara Pemakaian Sebagai Admin

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

1. Setelah Login sebagai user, berikut adalah tampilan dashboard Admin

<img width="1919" height="824" alt="image" src="https://github.com/user-attachments/assets/70036fbd-2b84-4cfd-9b15-1cafa146e57b" />

<img width="1919" height="818" alt="image" src="https://github.com/user-attachments/assets/b67b9dc2-e2f1-466b-8ca8-87ebf013eabd" />

2. Menu Contents

Menampilkan post Questions dari users dan admin 
   <img width="1919" height="830" alt="image" src="https://github.com/user-attachments/assets/9ef1a609-f8f4-452d-8aba-1106ab88177d" />
Menampilkan post Answer dari users dan admin
<img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/93456667-45dd-4f18-acd8-2e56ce17b4e3" />

3. Badges Admin
   
Admin dapat melihat dan melakukan aksi (deactivate) dari tiap achivements
   <img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/5289752f-be51-4626-897c-f65bc5fb0bad" />
   <img width="1919" height="829" alt="image" src="https://github.com/user-attachments/assets/3e5abcad-2c59-4f86-9a64-5b5dbf221d0b" />

4. Appearance
   
   Admin dapat mengubah tampilan aplikasi dengan 3 fitur, themes, customize, dan branding
   <img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/4825991e-7ef3-4c70-86ec-2113f2edb915" />
   <img width="1919" height="828" alt="image" src="https://github.com/user-attachments/assets/cd5283a7-71ed-46dd-9c58-126bf6871ed0" />
   <img width="1919" height="833" alt="image" src="https://github.com/user-attachments/assets/e9a7e7ee-66fc-4c8b-9b9d-073f9deed5cb" />

5. Settings dan Plugin Aplikasi

   Admin dapat mengubah, menambahkan plugin dan mengakses data aplikasi
   
   <img width="271" height="426" alt="image" src="https://github.com/user-attachments/assets/498d9767-be44-4fdb-9901-da7fbae6439e" />
 

## Pembahasan

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

Platform lontongsagu (Apache Answer) memberikan solusi praktis untuk membangun sistem tanya jawab seperti forum atau knowledge base internal.
Aplikasi lontongsagu (Apache Answer) memiliki dua peran utama: **Admin** dan **User**.
Admin bertanggung jawab untuk pengelolaan konten dan sistem, sementara user berperan sebagai kontributor dalam forum tanya jawab. 
Pembagian peran ini penting untuk menjaga kualitas diskusi dan mencegah penyalahgunaan sistem.

Sebagai salah satu platform Q&A open source yang banyak digunakan untuk membangun forum tanya jawab mandiri, aplikasi ini menawarkan sejumlah kelebihan, di antaranya:
-  Self-hosted & Open Source : kontrol penuh atas data dan tampilan aplikasi
- Fitur Q&A : lontongsagu (Apache Answer) mempunyai konsep forum tanya jawab modern, dengan sistem pertanyaan, jawaban, komentar, voting, serta tagging topik. Hal ini memudahkan komunitas dalam menemukan solusi secara cepat dan terstruktur.
- Mendukung Integrasi OAuth : lontongsagu telah mendukung integrasi login menggunakan akun eksternal seperti Google dan GitHub, sehingga mempermudah pengguna untuk bergabung tanpa perlu registrasi manual
- Fleksibel : Tampilan Modern dan mudah dikustomisasi untuk menyesuaikan branding atau kebutuhan komunitas tertentu. Desain antarmuka lontongsagu bersih, responsif, dan mudah dipahami pengguna.
- Cocok untuk Komunitas Internal Maupun Publik : Karena fleksibilitasnya, platform ini dapat digunakan untuk berbagai keperluan, mulai dari forum internal perusahaan, komunitas kampus, hingga forum publik yang berskala lebih besar

Sebuah aplikasi pasti juga memiliki kekurangan. Beberapa kekurangan yang dimiliki antara lain:
- Butuh Konfigurasi Server : proses instalasi relatif teknis bagi pemula
- Performa Tergantung Server : jika menggunakan resource terbatas, bisa melambat saat banyak user aktif

### Poin Perbandingan Utama
### lontongsagu Vs Quora Vs Reddit

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)


| Aspek                     | Apache Answer                                      | Quora                                                | Reddit                                                  |
|---------------------------|---------------------------------------------------|------------------------------------------------------|----------------------------------------------------------|
| Model hosting & kontrol   | Self-hosted; mengontrol penuh atas data & tampilan   | Publik; dikontrol oleh platform Quora                | Publik; kontrol terbagi (komunitas + subreddit)          |
| Fokus utama               | Pertanyaan & jawaban (forum Q&A)                   | Q&A formal & mendalam                                | Diskusi komunitas luas & spontan                         |
| Struktur komunitas        | Tag, voting, komentar, moderasi sendiri            | Profil pengguna, jawaban & vote                      | Subreddit/topic, post & komentar, banyak ragam           |
| Kustomisasi & branding    | Sangat fleksibel                                  | Terbatas (standar platform)                          | Terbatas untuk “branding sendiri” forum pribadi         |
| Kecepatan & formalitas    | Menengah (tergantung komunitas)                    | Cenderung lebih formal dan “terstruktur”             | Cepat, informal, sangat aktif                            |
| Cocok untuk               | Komunitas tertutup, internal organisasi            | Publik, profesional, membangun reputasi              | Komunitas minat bebas, diskusi ringan, berbagi opini     |


## Kesimpulan

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

Secara keseluruhan, Apache Answer memberikan pengalaman interaktif dan terstruktur dalam berbagi pengetahuan di komunitas.
Dengan antarmuka yang sederhana, sistem voting, serta fitur badge yang memotivasi partisipasi, aplikasi ini sangat cocok digunakan untuk forum tanya jawab internal organisasi, komunitas kampus, maupun proyek open source.

## Referensi

[Kembali ke atas](#sekilas-tentang-lontongsagu-apache-answer)

- Apache Answer: https://answer.apache.org/
- Repositori GitHub: https://github.com/apache/answer
- Dokumentasi Resmi: https://answer.apache.org/docs/installation
- Instalasi Microsoft Azure: https://azure.microsoft.com/en-us/downloads/
- Reddit (untuk perbandingan): https://redditinc.com/
- Quora (untuk perbandingan): https://id.quora.com/
