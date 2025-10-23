# 🛰️ ETSIOT

Proyek **ETSIOT** adalah sistem **IoT (Internet of Things)** berbasis **Rust** yang terdiri dari dua modul utama:

1. **streamdht** — membaca dan mengirim data sensor DHT (seperti suhu dan kelembapan).  
2. **ota2** — simulasi sistem **OTA (Over-The-Air Update)** untuk pembaruan firmware perangkat IoT.

---

# 📂 Struktur Folder
ETSIOT/
├── streamdht/
│ ├── Cargo.toml
│ └── src/
│ └── main.rs
└── ota2/
├── Cargo.toml
└── src/
└── main.rs

Setiap folder (`streamdht` dan `ota2`) merupakan proyek Rust yang berdiri sendiri dan dapat dijalankan secara terpisah.

# ⚙️ Instalasi & Persiapan

## 1️⃣ Instal Rust
Jalankan perintah berikut di terminal Ubuntu:

```bash
sudo apt update
sudo apt install curl -y
curl https://sh.rustup.rs -sSf | sh
source $HOME/.cargo/env

Cek versi untuk memastikan Rust terpasang dengan benar:
rustc --version
cargo --version

### 2️⃣ Clone Repositori
git clone https://github.com/Valzzsxs/ETSIOT.git
cd ETSIOT

# 🚀 Menjalankan Proyek

## 🔹 Menjalankan Modul OTA
Masuk ke direktori ota2 dan jalankan:
cd ota2
cargo run

## 🔹 Menjalankan Modul Stream DHT
Masuk ke direktori streamdht dan jalankan:
cd streamdht
cargo run

Untuk performa lebih baik, gunakan mode rilis:
cargo run --release

# 💡 Catatan untuk Pengguna ESP32

Jika proyek ini digunakan untuk ESP32, kamu perlu menyiapkan ESP-IDF environment terlebih dahulu.

## Instalasi ESP-IDF
sudo apt install git wget flex bison gperf python3 python3-pip cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0
git clone -b v5.1.1 --recursive https://github.com/espressif/esp-idf.git
cd esp-idf
./install.sh
. ./export.sh

Setelah itu, kembali ke direktori proyek dan lakukan build:
cargo build

## Flash ke Board ESP32S3 (opsional)
Jika ingin upload firmware ke ESP32S3:
cargo install espflash
espflash /dev/ttyUSB0 target/xtensa-esp32-*/release/ota2

# 🧩 Catatan Tambahan

-streamdht dapat dijalankan di PC Ubuntu untuk simulasi sensor.
-ota2 dapat digunakan untuk mensimulasikan atau menguji sistem pembaruan OTA.
-Keduanya ditulis dalam bahasa Rust dan dapat dikembangkan lebih lanjut untuk sistem IoT nyata berbasis ESP32.

# 📜 Lisensi

Proyek ini tidak memiliki lisensi resmi.
Jika ingin menggunakan atau memodifikasi, harap hubungi pemilik repositori (Rival & Ali).
