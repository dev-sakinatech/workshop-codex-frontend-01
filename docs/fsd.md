# Analisis & Rancangan Fitur eSamsat Maluku Utara

## Ringkasan
Aplikasi eSamsat Maluku Utara memusatkan penetapan, penagihan, dan pembayaran pajak kendaraan bermotor untuk pemilik kendaraan, petugas loket, serta admin pendapatan daerah. Prototype difokuskan pada alur utama: registrasi kendaraan, penetapan pajak, penagihan, dan pembayaran digital dengan monitoring kinerja.

## Tujuan Produk
- Mempercepat proses penetapan PKB/BBNKB dan penagihan secara digital.
- Menyediakan kanal pembayaran non-tunai yang aman dan terintegrasi.
- Mengurangi antrean fisik dengan layanan mandiri dan notifikasi status real-time.
- Mempermudah pelaporan dan monitoring bagi Badan Pendapatan Daerah (Bapenda).

## Aktor Utama
- **Wajib Pajak**: Pemilik kendaraan yang membayar pajak tahunan/BBN.
- **Petugas Bapenda**: Memverifikasi data, menetapkan tagihan, dan mengesahkan pembayaran.
- **Admin Sistem**: Mengelola master data, kanal pembayaran, peran pengguna, dan pelaporan.

## Batasan & Asumsi
- Integrasi dengan Samsat pusat & kepolisian untuk verifikasi STNK menggunakan API simulasi.
- Kanal pembayaran: QRIS, virtual account bank daerah, dan kartu debit di loket.
- Notifikasi dikirim via email/SMS gateway; prototype menggunakan placeholder.
- Data pengguna diautentikasi via OAuth sederhana; role-based access di prototipe disimulasikan.

## Rancangan Fitur Inti
1. **Autentikasi & Profil**
   - Login/registrasi wajib pajak, reset PIN, update kontak.
   - Manajemen peran admin/petugas.
2. **Registrasi & Validasi Kendaraan**
   - Pencarian data STNK/Nopol, unggah dokumen, validasi VIN.
   - Verifikasi petugas terhadap dokumen digital.
3. **Penetapan Pajak**
   - Perhitungan PKB, BBNKB, denda, dan diskon insentif.
   - Penetapan masa berlaku dan penerbitan NPPKB (nomor penetapan pajak).
4. **Penagihan & Notifikasi**
   - Pembuatan tagihan, kode bayar, dan jadwal jatuh tempo.
   - Pengingat otomatis via SMS/email dan status real-time.
5. **Pembayaran Digital**
   - QRIS, VA bank daerah, dan konfirmasi pembayaran loket.
   - Validasi bukti bayar dan penerbitan e-TBPKP & e-Pengesahan.
6. **Monitoring & Pelaporan**
   - Dashboard penerimaan, aging tagihan, dan performa kanal bayar.
   - Ekspor laporan harian/bulanan (CSV/PDF dummy di prototipe).
7. **Layanan Pendukung**
   - Helpdesk & FAQ, pengaduan online, riwayat transaksi.
   - Notifikasi perpanjangan STNK, reminder pajak, dan push updates.

## Alur Pengguna Utama
1. **Wajib Pajak** mendaftar, menautkan kendaraan via pencarian Nopol, mengunggah dokumen, lalu menerima hasil verifikasi.
2. **Petugas** menghitung PKB/BBNKB, menetapkan tagihan, dan menerbitkan kode bayar.
3. **Wajib Pajak** membayar via QRIS/VA, mengunggah bukti (opsional), dan menerima e-TBPKP & e-Pengesahan.
4. **Admin** memonitor dashboard penerimaan, aging tagihan, dan menarik laporan.

## Kebutuhan Non-Fungsional (Prototype)
- UI responsif dengan akses desktop dan mobile ringan.
- Navigasi sidebar untuk seluruh fitur.
- State dummy; tidak ada koneksi backend nyata.
- Komponen reusable (card, tabel ringkas, alert status) untuk mempercepat iterasi.
