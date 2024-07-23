
## Panduan Instalasi Xdebug

**Untuk Windows**
1. Unduh Xdebug
- Kunjungi situs web Xdebug di [xdebug.org](https://xdebug.org/docs/install).
- Pilih versi Xdebug yang sesuai dengan versi PHP yang digunakan. Dapat memeriksa versi PHP dengan menjalankan perintah ```php -v``` di Command Prompt. 

2. Menambahkan Xdebug ke PHP
Ekstrak file .dll yang diunduh dan tempatkan di direktori ext yang ada di dalam direktori instalasi PHP, misalnya ```C:\php\ext```.

Buka file ```php.ini```, yang biasanya terletak di direktori instalasi PHP.

Tambahkan baris berikut di bagian akhir file php.ini:
```
zend_extension = "c:\php\ext\xdebug.dll"
xdebug.mode = debug
xdebug.start_with_request = yes
```

Sesuaikan path zend_extension dengan lokasi sebenarnya di mana file Xdebug .dll berada.

3. Restart Apache
- Restart server Apache untuk memuat konfigurasi baru. Ini dapat dilakukan melalui XAMPP 
- Control Panel dengan menghentikan dan memulai ulang Apache, atau melalui Command Prompt.

**Untuk macOS**
1. Instal Xdebug dengan PECL
- Buka Terminal.
- Install Xdebug menggunakan PECL dengan menjalankan perintah:
```
sudo pecl install xdebug
```
Pastikan PECL sudah terinstal di sistemnya. Jika belum, bisa menginstalnya dengan [Homebrew](https://brew.sh/):
```
brew install php@8.0
brew link --overwrite --dry-run php@8.0
```
Ganti dengan versi PHP yang digunakan.

2. Konfigurasi Xdebug di php.ini
- Cari lokasi file php.ini dengan menjalankan ```php --ini``` di Terminal.
- Buka file ```php.ini``` tersebut dengan editor teks.
- Tambahkan baris berikut di bagian akhir file:
```
zend_extension="xdebug.so"
xdebug.mode = debug
xdebug.start_with_request = yes
```

****Verifikasi Instalasi****

Untuk memverifikasi bahwa Xdebug telah terinstal dan dikonfigurasi dengan benar, jalankan perintah ini di Terminal atau Command Prompt:
```
php -m
```
