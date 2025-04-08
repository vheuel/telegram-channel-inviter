
# Skrip Telegram Channel Inviter

Skrip ini dirancang untuk mengundang pengguna ke dalam sebuah channel Telegram. Skrip ini menggunakan library **Telethon**, yang memungkinkan Anda untuk berinteraksi dengan Telegram API dan mengotomatisasi proses pengundangan pengguna dari file CSV ke dalam sebuah channel Telegram yang ditentukan.

## Cara Kerja Skrip

1. **Kredensial API dan Nomor Telepon:**
   Skrip ini membutuhkan **API ID**, **API hash**, dan **nomor telepon** yang terhubung dengan akun Telegram untuk otentikasi dan menghubungkan ke Telegram API. Kredensial ini didapat dengan membuat aplikasi di [my.telegram.org](https://my.telegram.org).

2. **Pengaturan Sesi:**
   Skrip membuat sesi untuk menjaga koneksi dan menghindari perlu login setiap kali skrip dijalankan. Sesi ini dibuat menggunakan kredensial API yang diberikan.

3. **Autentikasi:**
   Jika klien belum terautentikasi, skrip akan mengirimkan kode verifikasi ke nomor telepon yang diberikan. Pengguna harus memasukkan kode yang diterima melalui SMS untuk mengautentikasi akun Telegram dan melanjutkan penggunaan skrip.

4. **Membaca Data Pengguna dari File CSV:**
   Skrip ini membaca file **CSV** yang berisi data pengguna yang akan diundang ke channel. Data ini meliputi username, ID pengguna, dan nama lengkap pengguna.

5. **Rentang Pengguna yang Akan Diundang:**
   Pengguna dapat menentukan rentang urutan pengguna yang akan diundang ke channel. Misalnya, hanya pengguna dari urutan ke-10 hingga ke-50 yang akan diundang.

6. **Mengundang Pengguna ke Channel:**
   Skrip ini mengundang pengguna yang username-nya terdaftar dalam file CSV ke dalam channel yang ditentukan. Setiap kali mengundang pengguna, skrip akan menunggu secara acak antara 60 hingga 130 detik untuk menghindari deteksi sebagai aktivitas spam oleh Telegram.

7. **Menangani Error:**
   Skrip ini dilengkapi dengan penanganan kesalahan yang memungkinkan untuk mengatasi beberapa situasi seperti:
   - **Flood Error (PeerFloodError)**: Jika terlalu banyak undangan yang dikirim dalam waktu singkat, Telegram akan memberi peringatan dan skrip akan berhenti sejenak selama 10 menit.
   - **Pengaturan Privasi Pengguna (UserPrivacyRestrictedError)**: Jika pengaturan privasi pengguna tidak mengizinkan orang lain untuk mengundangnya, skrip akan melewati pengguna tersebut.
   - **Kesalahan Tak Terduga**: Jika ada kesalahan lain, skrip akan mencetak pesan kesalahan dan melanjutkan ke pengguna berikutnya.

8. **Menutup Koneksi:**
   Setelah proses pengundangan selesai, skrip akan memutuskan koneksi dengan Telegram untuk mengakhiri sesi.

## Persyaratan

1. **Telethon Library**: Skrip ini menggunakan library Telethon untuk berinteraksi dengan API Telegram. Anda dapat menginstalnya menggunakan pip:
   ```bash
   pip install telethon

2. File CSV: jalankan file untuk scrapper untuk mengambil data dari sebuah channel
   ```bash
   python scrapper.py

   
3. sr. no., username, user id, name, Status

Pastikan Anda mengganti data pada file CSV dengan informasi pengguna yang sesuai.


3. Kredensial API Telegram: Anda harus mendapatkan API ID dan API hash dari my.telegram.org.


4. Nomor Telepon: Gunakan nomor telepon yang terdaftar pada akun Telegram Anda untuk autentikasi.



Cara Menggunakan Skrip

1. Gantilah api_id, api_hash, dan phone pada skrip dengan kredensial API Telegram dan nomor telepon yang Anda gunakan.


2. Siapkan file CSV yang berisi data pengguna yang ingin diundang ke channel Anda.


3. Jalankan skrip dengan perintah berikut:

python <nama_file_skrip>.py


4. Masukkan rentang urutan pengguna yang ingin diundang ketika diminta oleh skrip.


5. Skrip akan mengundang pengguna sesuai dengan rentang yang Anda tentukan dan menunggu selama beberapa detik di antara setiap undangan untuk menghindari pembatasan dari Telegram.



Catatan Penting

Pengguna yang diundang tidak akan otomatis bergabung ke channel. Mereka akan menerima notifikasi undangan dan harus menyetujui undangan dengan mengklik tombol "Join".

Skrip ini harus digunakan dengan hati-hati. Pengundangan dalam jumlah besar dalam waktu singkat dapat menyebabkan batasan spam dari Telegram. Pastikan untuk memberikan jeda waktu yang cukup antara pengundangan.

Pastikan juga bahwa username pengguna di file CSV tersedia, karena jika tidak, skrip akan melewatkan pengguna tersebut.


---

Penjelasan ini meliputi cara kerja skrip secara keseluruhan, persyaratan yang diperlukan, dan instruksi penggunaan skrip secara rinci.

