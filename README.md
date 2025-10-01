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
Setup Server 
1. Login Microsoft Azure (https://portal.azure.com/#home)
2. klik Virtual Machines
<img width="1599" height="619" alt="image" src="https://github.com/user-attachments/assets/2365e20c-d3fc-4094-b193-dbdd32735262" />
3. klik Create
<img width="1598" height="573" alt="image" src="https://github.com/user-attachments/assets/3d9bd87e-d660-435a-aecb-e5745b3de833" />
4. klik virtual Machines
<img width="1594" height="741" alt="image" src="https://github.com/user-attachments/assets/a685b377-57b0-4798-aefb-34fe63f64cef" />
5. setting 
<img width="1328" height="717" alt="image" src="https://github.com/user-attachments/assets/05b0f3d8-9784-41aa-a7ed-eb7df6d623fa" />
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
gjh
- Pendapat anda tentang aplikasi web ini
    - kelebihan
    - kekurangan
- Bandingkan dengan aplikasi web lain yang sejenis


## Referensi

Cantumkan tiap sumber informasi yang anda pakai.
