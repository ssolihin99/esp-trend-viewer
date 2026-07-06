# ESP Trend Viewer (standalone)

Aplikasi mandiri untuk menampilkan grafik interaktif parameter ESP dari CSV. Terpisah dari app diagnosa — hanya membaca & memvisualkan data, tanpa signature matching.

## Isi
- `index.html` — satu file mandiri (semua logika & alias di-embed, tanpa file config eksternal)

## Fitur
- Baca CSV **SCADA-flat** dan **Starview** (deteksi format otomatis)
- Pengenalan kolom otomatis (PIP, Intake Pressure, Amps, dst) + buang embel satuan `(psi)(Raw)`
- Grafik interaktif: **zoom** (scroll/drag/pinch), **pan**, **tooltip nilai asli**, **toggle series** via legenda
- **Semua parameter** CSV ditampilkan (dinormalisasi min–max untuk perbandingan bentuk)
- Tabel statistik per parameter (n, min, max, avg, last, Δ%)
- Ekspor grafik ke **PNG**
- Dwibahasa EN/ID

## Cara jalan
- GitHub Pages / Netlify: unggah `index.html`, langsung jalan.
- Lokal: `python -m http.server` lalu buka localhost (butuh internet untuk library CDN: Chart.js, zoom plugin, PapaParse).

## Catatan
Mandiri penuh — alias & aturan format di-hardcode di dalam `index.html`. Bila format/alias baru perlu ditambah, edit bagian `ALIASES` / `BLOCKLIST` di file ini (terpisah dari app diagnosa).
