# SWA Pertanian + Strato Art Studio — Business Manager

Satu frontend untuk dua entity dengan database Google Sheets yang berbeda.

## Entity
- SWA Pertanian → Apps Script SWA
- Strato Art Studio → Apps Script Strato

Switch entity di dropdown kanan atas. API URL dan logo berubah otomatis.

## Apps Script
Kedua spreadsheet harus memakai struktur: INVOICE, INVOICE_DETAIL, CUSTOMER, SETTINGS. Backend POS/ERP yang disertakan juga otomatis membuat PAYMENT, PRODUCT, STOCK_MOVEMENT bila belum ada.

### SWA
Gunakan Code.gs yang sekarang sudah terpasang pada deployment SWA.

### Strato
Replace Code.gs Strato dengan `Code.gs` dari paket ini, lalu deploy sebagai Web App (Execute as Me, akses sesuai kebutuhan). Ini menyamakan API Strato dengan API ERP SWA.

## Frontend
Upload seluruh isi folder ke GitHub Pages, termasuk `assets/StratoArtStudio.svg`.


## V3 — PWA Android + Product Picker
- Aplikasi dapat di-install sebagai PWA di Android/Chrome melalui tombol `Install App` atau menu browser.
- Manifest: `manifest.webmanifest`
- Service worker: `sw.js`
- Icon PWA: `icons/icon-192.png`, `icons/icon-512.png`
- Form invoice sekarang membaca master `PRODUCT`: pilih produk dari database, harga jual otomatis terisi, dan `productId` ikut disimpan untuk perhitungan HPP/margin.
- Deploy frontend melalui HTTPS (misalnya GitHub Pages) agar fitur install PWA aktif.

## V4 — Responsive Mobile App UI

Versi ini mempertahankan layout desktop Business Manager dan menambahkan layout mobile khusus untuk Android/PWA.

### Desktop
- Sidebar dan topbar tetap seperti Business Manager desktop.
- Tabel, form, POS dan modal tetap menggunakan layout lebar.

### Mobile / Android
- Bottom navigation: Home, POS, Invoice, Stok, Lainnya.
- Dashboard berubah menjadi card-based mobile layout.
- KPI menjadi touch-friendly cards.
- POS memakai grid produk 2 kolom dan checkout yang lebih mudah dijangkau.
- Data table berubah menjadi list/card agar tidak perlu horizontal scrolling.
- Modal form menjadi bottom sheet/full-width.
- Menu Lainnya berisi Produk, Customer, Pembayaran, Pembelian dan Laporan.
- Ikon aplikasi menggunakan logo Strato Art Studio.
- PWA tetap menggunakan `manifest.webmanifest` dan `sw.js`.

Backend, Google Sheets dan Apps Script tidak diubah oleh layout responsive ini.
