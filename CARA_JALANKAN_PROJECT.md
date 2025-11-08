# 🚀 Cara Jalankan Project MSU Digital Platform (Untuk Pemula)

## 📋 Persiapan Awal

### 1. Install Software yang Dibutuhkan
- **XAMPP** (untuk PHP & MySQL) - Download di https://www.apachefriends.org
- **Composer** (untuk manage package PHP) - Download di https://getcomposer.org
- **Git Bash** (sudah terinstall kalau ada Git) - Download di https://git-scm.com
- **Node.js** (untuk compile asset) - Download di https://nodejs.org

---

## 🔧 Langkah-Langkah Menjalankan Project

### **STEP 1: Buka Git Bash**
1. Klik kanan di folder project ini
2. Pilih **"Git Bash Here"**
3. Atau buka Git Bash, lalu ketik:
   ```bash
   cd "e:/MASJID SYAMSUL ULUM/MSU-Digital_Platform_Alquran_terintegrasi_Event_Management_System/MSU_DIGITAL_REVISI"
   ```

---

### **STEP 2: Install Dependencies PHP**
Jalankan perintah ini di Git Bash:
```bash
composer install
```

**Tunggu sampai selesai** (proses download package PHP)

---

### **STEP 3: Copy File Environment**
```bash
cp .env.example .env
```

Perintah ini akan membuat file `.env` dari template `.env.example`

---

### **STEP 4: Generate Application Key**
```bash
php artisan key:generate
```

Ini akan membuat encryption key untuk aplikasi Laravel

---

### **STEP 5: Setting Database**

#### A. Buka XAMPP Control Panel
- Start **Apache**
- Start **MySQL**

#### B. Buat Database
1. Buka browser, ketik: `http://localhost/phpmyadmin`
2. Klik tab **"Database"**
3. Buat database baru dengan nama: **`msu_digital`** (atau nama lain sesuai keinginan)
4. Klik **"Create"**

#### C. Edit File .env
Buka file `.env` di folder project, lalu edit bagian database:
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=msu_digital
DB_USERNAME=root
DB_PASSWORD=
```

**Catatan:**
- `DB_DATABASE` = nama database yang tadi dibuat
- `DB_USERNAME` = biasanya `root`
- `DB_PASSWORD` = kosongkan kalau pakai XAMPP default

---

### **STEP 6: Jalankan Migration Database**
Kembali ke Git Bash, jalankan:
```bash
php artisan migrate
```

Ini akan membuat semua tabel di database

**OPTIONAL - Isi Data Dummy:**
```bash
php artisan db:seed
```

---

### **STEP 7: Install Dependencies Frontend (Node.js)**
```bash
npm install
```

Tunggu sampai selesai download package JavaScript

---

### **STEP 8: Compile Asset Frontend**
```bash
npm run dev
```

Atau kalau mau build untuk production:
```bash
npm run build
```

---

### **STEP 9: Jalankan Server Laravel**
```bash
php artisan serve
```

**Output yang muncul:**
```
Starting Laravel development server: http://127.0.0.1:8000
```

---

### **STEP 10: Buka di Browser**
1. Buka browser (Chrome/Firefox/Edge)
2. Ketik di address bar: **`http://127.0.0.1:8000`** atau **`http://localhost:8000`**
3. Project sudah jalan! 🎉

---

## 🛑 Cara Matikan Server

### Opsi 1: Tekan di Git Bash
```
Ctrl + C
```

### Opsi 2: Tutup Git Bash
Langsung close window Git Bash yang running server

---

## 🔄 Cara Jalankan Lagi (Setelah Komputer Restart)

1. **Buka XAMPP** → Start Apache & MySQL
2. **Buka Git Bash** di folder project
3. **Jalankan server:**
   ```bash
   php artisan serve
   ```
4. **Buka browser:** `http://localhost:8000`

---

## ⚠️ Troubleshooting (Kalau Ada Error)

### Error: "composer: command not found"
**Solusi:** Install Composer dulu → https://getcomposer.org

### Error: "npm: command not found"
**Solusi:** Install Node.js dulu → https://nodejs.org

### Error: "SQLSTATE[HY000] [1049] Unknown database"
**Solusi:** 
1. Pastikan XAMPP MySQL sudah running
2. Cek nama database di `.env` sudah benar
3. Pastikan database sudah dibuat di phpMyAdmin

### Error: "Address already in use"
**Solusi:** Port 8000 sudah dipakai, gunakan port lain:
```bash
php artisan serve --port=8001
```

### Error: "No application encryption key has been specified"
**Solusi:** Jalankan:
```bash
php artisan key:generate
```

---

## 📝 Perintah Penting Lainnya

### Clear Cache
```bash
php artisan cache:clear
php artisan config:clear
php artisan route:clear
php artisan view:clear
```

### Lihat Semua Route
```bash
php artisan route:list
```

### Buat Migration Baru
```bash
php artisan make:migration nama_migration
```

### Buat Controller Baru
```bash
php artisan make:controller NamaController
```

### Buat Model Baru
```bash
php artisan make:model NamaModel
```

---

## 📞 Butuh Bantuan?

Kalau ada error atau bingung, cek:
1. File log error di: `storage/logs/laravel.log`
2. Pastikan semua software sudah terinstall
3. Pastikan XAMPP MySQL & Apache sudah running

---

**Selamat Coding! 🚀**
