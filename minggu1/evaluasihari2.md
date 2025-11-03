# JAWABAN TUGAS:

---

## 1. Konsep dasar React Native
React Native itu framework buat bikin aplikasi mobile cross-platform (Android dan iOS) pakai JavaScript dan React.  
Bedanya sama React web adalah:  
- React web render ke DOM (HTML, CSS).  
- React Native render ke komponen native (View, Text, dll) lewat bridge ke sistem operasi.  

Jadi walau kodenya sama-sama pakai React, hasil akhirnya beda. Di React Native gak ada `<div>` atau `<span>`, tapi pakainya `<View>` dan `<Text>`.

**Tentang New Architecture (React Native v0.80)**  
Versi baru ini pakai sistem yang namanya *Fabric* dan *TurboModules* buat ganti cara komunikasi antara JavaScript dan native.  
Kalau dulu pakai “bridge” yang lambat karena harus serialisasi data, sekarang udah langsung sinkron pakai JSI (JavaScript Interface).  
Efeknya performa jadi lebih cepat dan interaksi UI lebih responsif.

---

## 2. Perbandingan React Native CLI dan Expo
- **React Native CLI:**  
  Arsitekturnya lebih terbuka, bisa akses langsung ke native code (Android/iOS folder).  
  Build dilakukan lewat Gradle (Android) dan Xcode (iOS).  
  **Kelebihan:** bisa integrasi library native custom.  
  **Kekurangan:** setup awal agak ribet.

- **Expo:**  
  Lebih simpel karena sudah bundling banyak library bawaan. Build bisa dilakukan lewat `expo build` tanpa Xcode/Android Studio.  
  **Kelebihan:** setup cepat, cocok buat pemula atau prototyping.  
  **Kekurangan:** gak semua native module bisa diakses langsung (tergantung dukungan Expo SDK).

**Contoh skenario:**  
Kalau aku bikin aplikasi sederhana kayak katalog produk atau todo list → pakai Expo biar cepat jalan.  
Tapi kalau proyek besar yang butuh akses native (misal Bluetooth, background service) → pilih React Native CLI.

---

## 3. Setup environment Android
Di setup React Native, ada beberapa komponen penting:

- **SDK Platforms (android-35):**  
  Isinya API level yang dipakai buat compile dan jalanin app. Kalau gak ada, build gagal karena target SDK gak ketemu.
- **Build Tools (35.0.0):**  
  Dipakai Gradle buat compile dan generate file APK/AAB. Tanpa ini, proses build bakal error di bagian `aapt` atau `dx`.
- **Platform Tools:**  
  Isinya tools kayak `adb` buat komunikasi antara komputer dan device/emulator.  
  Kalau gak ada ini, `npx react-native run-android` gak bisa connect ke emulator.

Jadi kalau satu aja gak ada, misalnya Build Tools-nya belum diinstall, nanti error kayak `Failed to find Build Tools revision 35.0.0` muncul di VS Code.

---

## 4. Prasyarat setup React Native CLI v0.80
Beberapa tools penting yang wajib ada:

- **Node.js:** buat jalanin environment JavaScript (React Native pakai JS di sisi logic-nya).  
- **Watchman:** bantu React Native mendeteksi perubahan file dan reload otomatis saat coding.  
- **Yarn:** package manager yang lebih cepat dan stabil dari npm, dipakai buat install dependency.

Semua ini dibutuhkan supaya JavaScript code bisa nyambung dan dijalankan di native runtime melalui Metro bundler.

---

## 5. Struktur folder utama proyek React Native CLI
Struktur umumnya kayak gini:

myApp/

├── android/ # berisi kode native Android (Gradle, manifest, java)

├── ios/ # berisi kode native iOS (project Xcode)

├── app.json

├── App.js # entry point utama aplikasi

├── index.js # register komponen utama ke AppRegistry

├── metro.config.js # konfigurasi Metro bundler

├── package.json

└── node_modules/

**Penjelasan singkat:**
- `android/` dan `ios/` → bagian native, beda platform.  
- `App.js` → tempat logic utama aplikasi, mirip `App.jsx` di React web.  
- `metro.config.js` → ngatur bundler yang nge-link antara JS dengan native.  

Struktur ini memudahkan pengembangan *cross-platform*, karena kamu bisa coding di file JS yang sama dan build ke dua platform lewat folder native yang udah disiapin. Di VS Code juga enak buat navigasi karena struktur jelas dan modular.



