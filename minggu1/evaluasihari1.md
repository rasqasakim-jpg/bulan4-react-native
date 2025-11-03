# Jawaban Tugas:

## 1. Definisi Mobile App Development
Mobile App Development adalah proses membuat aplikasi yang berjalan di perangkat mobile seperti Android atau iOS. Fokus utamanya ada di pengalaman pengguna (UI/UX), performa di perangkat, dan integrasi dengan fitur hardware (kamera, GPS, sensor, dll).  
Output teknisnya berupa file aplikasi seperti `.apk` (Android) atau `.ipa` (iOS) yang bisa diinstal di perangkat.

## 2. Perbedaan Web Development dan Mobile App Development
- **Target Eksekusi:**  
  Web jalan di browser, sedangkan mobile app jalan langsung di sistem operasi perangkat.
- **Distribusi:**  
  Web bisa langsung diakses lewat URL, mobile app harus lewat store seperti Play Store atau App Store.
- **Akses Hardware:**  
  Mobile app punya akses lebih dalam ke hardware (kamera, GPS, sensor), web terbatas.
  
**Implikasi praktis:** Misalnya, aplikasi yang butuh akses kamera real-time lebih cocok dibuat sebagai mobile app dibanding web.

## 3. Tahapan Discovery & Requirement
Tahap ini untuk memahami tujuan aplikasi, siapa penggunanya, dan fitur apa yang dibutuhkan. Dari sini ditentukan target platform (Android, iOS, atau dua-duanya) dan apakah aplikasi perlu bisa offline.  
Kalau targetnya pengguna lapangan tanpa sinyal stabil, maka fitur offline wajib dipertimbangkan.

## 4. Tahapan Perancangan Arsitektur & Teknologi
Di tahap ini ditentukan struktur teknis aplikasi, seperti pemilihan framework, arsitektur state management, dan navigasi.  
Dalam React Native, hal ini penting karena menentukan cara data dikelola dan bagaimana navigasi antar layar berjalan.  
State management (misalnya Redux, Zustand, Recoil) dan navigasi (misalnya React Navigation) harus dipilih dengan hati-hati supaya aplikasi stabil dan mudah dikembangkan.

## 5. Native vs Hybrid Development
- **Native Development:**  
  Gunakan bahasa asli platform (Kotlin/Java untuk Android, Swift untuk iOS).  
  **Kelebihan:** performa tinggi, akses penuh ke hardware.  
  **Kekurangan:** harus buat dua versi aplikasi kalau mau support dua platform.
  
- **Hybrid Development:**  
  Gunakan satu codebase untuk dua platform, tapi dijalankan lewat webview.  
  **Kelebihan:** hemat waktu dan biaya.  
  **Kekurangan:** performa kadang lebih rendah.  
  Contoh framework selain yang umum: Ionic, Cordova, Flutter (walau Flutter lebih ke cross-platform native).

## 6. Cross-Platform Native Development
Adalah pendekatan di mana satu codebase bisa dikompilasi jadi aplikasi native di banyak platform.  
**Keuntungan:** efisiensi waktu, satu tim bisa handle semua platform.  
**Kekurangan:** kadang fitur hardware tertentu lebih susah diakses dibanding native murni.

## 7. Posisi React Native
React Native ada di tengah-tengah antara native dan hybrid.  
Berbeda dari ReactJS yang untuk web, React Native pakai komponen native (bukan HTML).  
Styling-nya juga beda karena pakai `StyleSheet` mirip CSS tapi dengan properti camelCase.  
Targetnya bukan browser, tapi sistem operasi mobile.

## 8. Tantangan Pengembangan Mobile vs Web
Mobile lebih kompleks karena harus perhatikan ukuran layar, performa, dan hardware.  
Cross-platform seperti React Native membantu karena satu code bisa jalan di Android dan iOS tanpa bikin dari nol dua kali.

## 9. Tahapan Pengujian dan Build, Signing, Release
- **Testing:** pastikan fitur jalan di emulator dan device nyata.  
- **Build:** buat file `.apk` atau `.aab` (Android App Bundle) lewat perintah `npx react-native run-android` atau `gradlew assembleRelease`.  
- **Signing:** tambahkan keystore untuk keamanan dan identitas developer.  
- **Release:** upload ke Play Store atau TestFlight untuk distribusi ke pengguna.

## 10. Kenapa React Native Banyak Dipilih
Karena bisa bikin aplikasi untuk dua platform sekaligus dengan satu codebase, waktu pengembangan jadi lebih cepat.  
Selain itu komunitasnya besar, performanya cukup bagus, dan integrasi dengan native module juga mudah.
