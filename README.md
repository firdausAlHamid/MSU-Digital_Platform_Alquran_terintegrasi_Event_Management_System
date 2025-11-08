# MSU-Digital-Platform-terintegrasi-Al-Quran-Event-Management-System
MSU Digital: Platform terintegrasi Al-Quran &amp; Event Management System untuk Masjid Syamsul Ulum. Menggabungkan fitur baca Al-Quran dengan sistem pengelolaan kegiatan masjid. Highlights: event tracking, integrasi kajian-ayat, manajemen jamaah &amp; presensi digital.

# CARA MENJALANKAN WEBSITE PADA LOCAL BROWSER 

# 1. Persiapan Database & XAMPP
   1. Buka XAMPP Control Panel
   2. Start Apache dan MySQL
   3. Buka phpMyAdmin: http://localhost/phpmyadmin
   4. Buat database baru:
     - Nama: digital_quran
     - Collation: utf8mb4_unicode_ci
    
# 2. Clone & Setup Project
      1. Buka Git Bash, clone repository
         git clone https://github.com/firdausAlHamid/TUBES_WAD_2025.git
         cd TUBES_WAD_2025/MSU_DIGITAL_REVISI

      2. Install PHP dependencies
          composer install

      3. Copy .env.example ke .env
          cp .env.example .env

      4. Generate application key
          php artisan key:generate
          
# 3. Konfigurasi .env

# 4. Buka file .env dan sesuaikan:

# 5. Setup Database & Storage
   
# 6. Install & Build Assets
    
# 7. Menjalankan Server (Development)
php artisan serve

# 8. Akses Website
Buka browser
Kunjungi: http://127.0.0.1:8000
