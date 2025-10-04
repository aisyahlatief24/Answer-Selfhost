Apache Answer-Selfhosted

<img width="1280" height="720" alt="lontongsagu" src="https://github.com/user-attachments/assets/93ca633c-5398-42e8-bcdd-1a02ea372521" />

## Sekilas Tentang Apache Answer

Apache Answer adalah aplikasi Q&A (Question and Answer platform) mirip dengan Stack Overflow namun bersifat self-hosted.
Aplikasi ini mendukung sistem pertanyaan, jawaban, komentar, voting, dan tag sehingga cocok digunakan untuk membangun forum diskusi internal maupun komunitas publik.

Fitur utama:
- Posting pertanyaan & jawaban
- Sistem voting (upvote & downvote)
- Tagging untuk pengelompokan topik
- Login via email maupun integrasi OAuth (Google, GitHub, dsb)
- Panel admin untuk mengatur user & konten

## Instalasi

Kebutuhan Sistem
- Unix, Linux, MacOS atau Windows. 
- Langkah instalasi dalam CLI.
- Docker
- Microsoft Azure
- Apache
- Ram minimal 

Setup Server 
1. Login Microsoft Azure (https://portal.azure.com/#home)
   
3. klik Virtual Machines
<img width="1599" height="619" alt="image" src="https://github.com/user-attachments/assets/2365e20c-d3fc-4094-b193-dbdd32735262" />

4. klik Create
<img width="1598" height="573" alt="image" src="https://github.com/user-attachments/assets/3d9bd87e-d660-435a-aecb-e5745b3de833" />

5. klik virtual Machines
<img width="1594" height="741" alt="image" src="https://github.com/user-attachments/assets/a685b377-57b0-4798-aefb-34fe63f64cef" />

6. setting 
<img width="1328" height="717" alt="image" src="https://github.com/user-attachments/assets/05b0f3d8-9784-41aa-a7ed-eb7df6d623fa" />

saran : gunakan password jika ingin mudah

seperti dibawah ini

<img width="1019" height="636" alt="image" src="https://github.com/user-attachments/assets/c6211b46-cb33-4b90-a2a9-6073f8220e0e" />







Proses Instalasi:

1. Login kedalam server menggunakan SSH.
   
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

4. Mengambil kode Apche Answer dari Github ke VM 
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
7. Kunjungi alamat IP web server kita untuk meneruskan instalasi.
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

Setup Domain 

Buka www.domainesia.com

<img width="1600" height="1041" alt="image" src="https://github.com/user-attachments/assets/80349d22-834b-49e8-adfb-2b02898f4fa8" />

<img width="1600" height="432" alt="image" src="https://github.com/user-attachments/assets/4e8e8290-d2a9-429a-bb83-5c9647176097" />

Network Setting
1. Buka Microsoft Azure -> login -> klik aerver yang telah kamu buat

<img width="1253" height="707" alt="image" src="https://github.com/user-attachments/assets/e017336d-c59a-4ed8-a096-45206bddcbcc" />

2. Pilih Network -> Network Setting
   
<img width="267" height="652" alt="image" src="https://github.com/user-attachments/assets/b3d73177-2431-418d-a51d-1e9b488bca3e" />

3. Create New Port Rule

   <img width="1595" height="642" alt="image" src="https://github.com/user-attachments/assets/11a921ca-9e3c-481b-8bde-c31e1c2f438d" />

4. Pilih Inbound Port Rule

   <img width="1587" height="303" alt="image" src="https://github.com/user-attachments/assets/5b17bb27-e278-4667-be0f-d83f99e167de" />

   setting : untuk menambahkan http (80) dan https (443)
   
   <img width="579" height="687" alt="image" src="https://github.com/user-attachments/assets/ae204111-6a7d-49a5-95e6-478374f15eec" />
   
   akan muncul tampilan seperti dibawah ini :
   
   <img width="1250" height="260" alt="image" src="https://github.com/user-attachments/assets/88336abf-6cd0-476b-9748-857b537969ee" />


setting HTTP dan HTTPS di Commend Prompt

1. login server 
Masuk ke server VM Azure lewat SSH sebagai user ondeonde.
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
4. Mengecek proses apa yang sedang memakai port  (biasanya Nginx atau Apache).
   
   ```bash
   sudo lsof -i :80  # kalau http
   sudo lsof -i :443 # kalau https
   ```
  
5. Edit konfigurasi VirtualHost SSL untuk menambahkan ProxyPass ke aplikasi di port 9080 agar http(80) dan https(443) bisa di access.
   ```bash
   sudo nano /etc/apache2/sites-enabled/000-default-le-ssl.conf
   ``` 
   edit seperti dibawah ini
   
   <img width="770" height="597" alt="Screenshot 2025-09-26 065601" src="https://github.com/user-attachments/assets/7bbca66c-d66a-43ac-b5f1-21c9992d89a2" />

6. Tes apakah konfigurasi Apache valid setelah semua perubahan.
   ```bash
   sudo apache2ctl configtest
   ```
7. test  di Browaer
   http  : http://tanya.lontongsagu.web.id 
   https : https://tanya.lontongsagu.web.id
   tanpa semua yang diatas : tanya.lontongsagu.web.id


## Konfigurasi (opsional)

Setting server tambahan yang diperlukan untuk meningkatkan fungsi dan kinerja aplikasi, misalnya:
- batas upload file
- batas memori
- dll

Plugin untuk fungsi tambahan
- login dengan Google/Facebook
- editor Markdown
- dll


##  Maintenance (opsional)

Setting tambahan untuk maintenance secara periodik, misalnya:
- buat backup database tiap pekan
- hapus direktori sampah tiap hari
- dll


## Otomatisasi (opsional)

Skrip shell untuk otomatisasi instalasi, konfigurasi, dan maintenance.


## Cara Pemakaian

- Tampilan aplikasi web
- Fungsi-fungsi utama
- Isi dengan data real/dummy (jangan kosongan) dan sertakan beberapa screenshot


## Pembahasan

- Pendapat anda tentang aplikasi web ini
    - kelebihan
    - kekurangan
- Bandingkan dengan aplikasi web lain yang sejenis


## Referensi

Cantumkan tiap sumber informasi yang anda pakai.
