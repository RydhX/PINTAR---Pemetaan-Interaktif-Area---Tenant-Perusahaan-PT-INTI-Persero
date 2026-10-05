# CampusMap — WebGIS Tenant Management (Offline SVG)

Versi ini sengaja **tidak menggunakan Leaflet, CDN, API, atau internet**. Semua peta lantai digambar dengan SVG native sehingga file bisa dibuka dari VS Code / Live Server bahkan saat offline.

## Jalankan
1. Extract ZIP.
2. Buka folder di VS Code.
3. Klik kanan `index.html` → Open with Live Server (opsional). Bisa juga double-click `index.html`.

## Fitur
- Denah vector SVG dengan bentuk bangunan tidak sekadar kotak.
- 12 unit dummy pada 1 lantai.
- Klik unit → panel tenant.
- Status pembayaran dan kontrak memengaruhi warna unit.
- Filter, pencarian, daftar unit, dashboard, riwayat pembayaran.
- Zoom +/− dan scroll wheel.
- Tidak membutuhkan koneksi internet.

## Bagian yang nanti diganti untuk data nyata
- `units` di `app.js` → API/database.
- SVG di fungsi `buildSvg()` → SVG hasil tracing denah survey.
- `Unit ID` menjadi kunci relasi antara polygon dan tabel tenant/lease/payment.

## Struktur produksi yang disarankan
SVG polygon → Unit ID → API → PostgreSQL/PostGIS → tenant / contract / payment / documents.
