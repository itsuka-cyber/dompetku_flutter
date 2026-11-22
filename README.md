# DompetKu (Flutter)

Versi Flutter dari aplikasi web **DompetKu** (`itsuka-cyber/Dompetku`): pencatat
keuangan pribadi yang berjalan 100% offline. Tampilan, warna, teks, dan alur
dibuat mengikuti versi web.

## Fitur

- Onboarding 3 slide + input nama
- Dashboard: saldo utama, tabungan (tabung / tarik), budget bulanan dengan
  progress bar (merah > 90%, oranye > 75%), donat pengeluaran, goal aktif,
  5 transaksi terakhir
- Tambah transaksi (pengeluaran / pemasukan), kategori, tanggal, catatan,
  buat kategori baru dengan pilihan ikon
- Riwayat transaksi: cari, filter, geser ke kiri untuk hapus (saldo dikembalikan)
- Laporan: ringkasan bulan ini + saving rate, donat per kategori, tren 6 bulan, rincian
- Goals: buat target, tambah dana cepat (+50rb / +100rb), hapus
- Pengaturan: budget, mode gelap, backup / restore (.json), reset
- Data tersimpan lokal; **format backup sama dengan versi web**, jadi file backup
  dari web bisa dipulihkan di sini dan sebaliknya

## Cara build

Butuh Flutter SDK (stable) + Android SDK.

```bash
flutter create --platforms=android --project-name dompetku --org com.dompetku .   # sekali saja, hanya melengkapi file yang hilang
flutter pub get
flutter run                 # jalankan di HP / emulator
flutter build apk --release # hasil: build/app/outputs/flutter-apk/app-release.apk
```

### Tanpa komputer (dari HP)

Upload isi folder ini ke repo GitHub milikmu, lalu buka **Actions → Build APK →
Run workflow**. File APK muncul di bagian *Artifacts*
(`.github/workflows/build-apk.yml`).

## Catatan

- Font Inter disertakan di `assets/fonts` (lisensi SIL OFL 1.1).
- APK release ditandatangani dengan kunci debug agar langsung bisa dipasang.
  Untuk Play Store, buat keystore sendiri.
- Foto transaksi (`imageUrl`) tidak ada UI-nya di versi web, jadi tidak
  diimplementasikan; field-nya tetap ikut tersimpan di backup.
  
