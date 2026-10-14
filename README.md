# AI Study Memory — Galaxy Edition

Aplikasi hafalan untuk ujian sekolah (offline-first) dengan AI tutor opsional.

## Dapatkan APK lewat GitHub (tanpa Android Studio)
1. Buat repo BARU di GitHub (jangan pakai repo aplikasi lain).
2. Upload semua file di folder ini ke repo (index.html, semua .png, package.json, capacitor.config.json).
3. Buat file `.github/workflows/build-apk.yml` (isinya sama dengan `build-apk.yml`).
4. Buka tab Actions > Build APK, tunggu centang hijau (5-8 menit).
5. Unduh `AIStudyMemory-apk` di bagian Artifacts, ekstrak, pasang APK-nya.

ID paket aplikasi: `com.aistudymemory.app` (berbeda dari aplikasi lain), jadi terpasang sebagai aplikasi terpisah.
APK yang dibuat adalah debug (untuk dipasang langsung, bukan Play Store).

## Fitur impor file dan pengingat (versi 1.1)
- **DOCX**: dibaca langsung. Tabel dua kolom jadi pasangan `istilah | pengertian`, judul (Heading) Word jadi bab.
- **PDF**: teks dibaca dengan pdf.js. PDF hasil pindai otomatis dibaca dengan OCR (maks 15 halaman).
- **Foto**: dibaca dengan OCR Tesseract (bahasa Indonesia + Inggris), offline di dalam APK. Hasil OCR bisa salah baca, jadi periksa dulu.
- Pustaka PDF/OCR diunduh GitHub saat build lewat `npm install` dan disalin ke `www/vendor` (lihat langkah "Siapkan pustaka impor"). Kalau satu file tidak ketemu, build tetap jalan tapi log menulis "PERINGATAN" dan fitur itu tidak aktif. Cek log langkah itu.
- APK jadi lebih besar (puluhan MB) karena membawa data OCR.
- **Pengingat**: dijadwalkan lewat notifikasi Android (plugin local-notifications), jadi bisa berbunyi saat aplikasi ditutup. Pesannya tetap sama setiap hari. Waktu bisa meleset beberapa menit, dan hemat baterai yang ketat bisa menundanya. Berikan izin notifikasi saat diminta.
- Versi web hanya mendukung DOCX; PDF, OCR, dan notifikasi latar belakang hanya ada di APK.
- File (PDF, DOCX, foto, TXT) juga bisa dilampirkan di AI Tutor (maks 12000 karakter dikirim) dan di Buat dengan AI (maks 6000 karakter).
