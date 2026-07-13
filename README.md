# KARSA-UMKM
### Sistem Informasi Mapping UMKM Kabupaten Rembang
**KARSA** — *Katalog Usaha Rembang: Sebaran & Analitik*

> Bagian dari kegiatan **Sensus Ekonomi 2026 (SE2026)**
> BPS Kabupaten Rembang, Jawa Tengah

🌐 **Live:** [wongrembang.github.io/karsa](https://wongrembang.github.io/karsa)

---

## Tentang

SIMAK-UMKM adalah platform visualisasi dan analitik berbasis web untuk data direktori UMKM Kabupaten Rembang hasil scraping Google Maps dalam rangka persiapan SE2026. Platform ini berjalan sepenuhnya di browser — tidak ada server backend, tidak ada data yang dikirim ke luar.

Data dibangun melalui pipeline **KARSA**:
1. **Scraping** Google Maps → 6.438 usaha (14 kecamatan × 14 kategori)
2. **Filter wilayah** → 6.028 data valid Kabupaten Rembang
3. **Klasifikasi KBLI 2025** → 3 layer (Keyword 84% · Fuzzy 0.2% · Claude AI 15.8%)

---

## Fitur

| Fitur | Deskripsi |
|---|---|
| 📊 Dashboard | Statistik ringkasan, distribusi per kecamatan, komposisi KBLI, top 10 kode KBLI |
| 📋 Data UMKM | Tabel 6.028 usaha dengan filter kecamatan, kategori KBLI, layer klasifikasi, pencarian teks |
| 🗺️ Peta Sebaran | Leaflet.js + OpenStreetMap — titik koordinat dari URL Google Maps, popup info, filter interaktif |
| ⬇️ Export CSV | Download data hasil filter sebagai file CSV |
| 🗑️ Hapus Titik | Sembunyikan titik outlier dari peta (tersimpan di browser, tidak mengubah data asli) |

---

## Cara Pakai

1. Buka [wongrembang.github.io/karsa](https://wongrembang.github.io/karsa)
2. Upload file `karsa_umkm_rembang.csv` via drag & drop atau klik tombol upload
3. Data langsung diproses di browser — tidak ada koneksi server

> **Privasi:** Data tidak dikirim ke mana pun. Semua pemrosesan terjadi secara lokal di browser pengguna.

---

## Struktur Kolom CSV

| Kolom | Keterangan |
|---|---|
| `No` | Nomor urut |
| `Nama Usaha` | Nama usaha/bisnis |
| `Kategori` | Kategori pencarian scraping |
| `Alamat` | Alamat lengkap dari Google Maps |
| `No Telepon` | Nomor telepon (jika tersedia) |
| `Rating` | Rating Google Maps |
| `Jumlah Review` | Jumlah ulasan |
| `Google Maps Link` | URL Google Maps |
| `Keyword Pencarian` | Kata kunci yang digunakan saat scraping |
| `Tanggal Scraping` | Tanggal data diambil |
| `Kode KBLI` | Kode KBLI 2025 hasil klasifikasi |
| `Nama KBLI` | Nama lengkap KBLI |
| `Kategori KBLI` | Kategori lapangan usaha (A–S) |
| `Layer Klasifikasi` | L1 Keyword / L2 Fuzzy / L3 Claude AI |

---

## Teknologi

- **Frontend:** HTML5 + Vanilla JS (single-file, no build tools)
- **Peta:** [Leaflet.js](https://leafletjs.com/) + OpenStreetMap / CartoDB Dark
- **Grafik:** [Chart.js](https://www.chartjs.org/)
- **Parsing CSV:** [PapaParse](https://www.papaparse.com/)
- **Klasifikasi KBLI:** Claude API (claude-sonnet-4-6) — Anthropic

---

## Deploy Lokal

```bash
git clone https://github.com/wongrembang/karsa
cd karsa
python -m http.server 8080
# Buka http://localhost:8080
```

---

## Kredit

**M@I-2026** — pencari surga

---

*Data UMKM bersumber dari Google Maps dan hanya digunakan untuk keperluan statistik SE2026. Tidak untuk tujuan komersial.*
