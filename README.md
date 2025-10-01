# Apache Answer-Selfhosted

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

. Masuk ke server VM Azure lewat SSH sebagai user ondeonde
```bash
ssh ondeonde@20.196.129.189
```

. Update daftar paket di Ubuntu biar versi software terbaru terdaftar
```bash
sudo apt update
```

. Cek proses apa yang sedang memakai port 80 (biasanya Nginx atau
Apache).
```bash
sudo lsof -i:80
```

Matikan Nginx (karena dia pakai port 80 dan bentrok dengan Apache).
```bash
sudo systemctl stop nginx
```

.Menyalakan Apache supaya bisa ambil alih port 80
```bash
sudo systemctl start apache2
```

.Pasang SSL gratis dari Let's Encrypt untuk domain
tanya.lontongsagu.web.id dan otomatis konfigurasi di Apache
```bash
sudo certbot --apache -d
tanya.lontongsagu.web.id
```

.Edit konfigurasi VirtualHost SSL Apache untuk menambahkan
pengaturan (misalnya proxy ke port 9080)
```bash
sudo nano /etc/apache2/sites-enabled/ee8-
default-le-ssl.conf
```

.Tes apakah konfigurasi Apache valid (cek syntax error)
```bash
sudo apache2ctl configtest
```

.Tes apakah aplikasi kamu di port 9080 memang jalan, dengan request
HTTP header saja.
```bash
curl -I http://localhost:9080
```

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
