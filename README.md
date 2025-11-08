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
      APP_NAME="MSU Digital"
      APP_URL=http://localhost:8000
      
      DB_CONNECTION=mysql
      DB_HOST=127.0.0.1
      DB_PORT=3306
      DB_DATABASE=digital_quran
      DB_USERNAME=root
      DB_PASSWORD=

      ALQURAN_CLOUD_API_URL=http://api.alquran.cloud/v1
      DEFAULT_TRANSLATION_EDITION=id.indonesian
      QURAN_API_CACHE_DURATION=10080

 # 4. Setup Database & Storage
   1. Jalankan migrasi database
   php artisan migrate --force

   2. Buat symbolic link untuk storage
   php artisan storage:link

# 5. Install & Build Assets
   1. Install NPM dependencies
   npm install

   2. Build assets
   npm run build
    
# 6. Menjalankan Server (Development)
   php artisan serve

# 7. Akses Website
   Buka browser
   Kunjungi: http://127.0.0.1:8000
