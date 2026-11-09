# Dashboard Kinerja Sederhana

Contoh praktik mata kuliah **Teknologi Kinerja** (S1 Teknologi Pendidikan UNESA): mengukur kinerja tim **sales** (capaian revenue) dan **IT support** (tiket selesai tepat waktu), lalu menampilkannya sebagai dashboard di browser.

> Semua angka adalah **data contoh (dummy)**, bukan data perusahaan sebenarnya.

## Isi folder

```
dashboard-kinerja/
├── index.html                         ← dashboard (buka di browser)
├── README.md
└── data/
    ├── sales.csv                      ← data sales: nama, target, aktual
    ├── tiket.csv                      ← data tiket: no_tiket, teknisi, prioritas, waktu_selesai_jam
    └── Latihan_Pengukuran_Kinerja.xlsx ← versi Excel (rumus yang sama)
```

## Menu dashboard

| Menu | Isi |
|---|---|
| **Ringkasan** | Kartu KPI utama + temuan otomatis (siapa yang di bawah target) |
| **Sales** | Kartu per sales, grafik perbandingan, dan tabel *Data Penjualan dari ERP* |
| **IT Support** | Kartu per teknisi, grafik perbandingan, dan tabel *Data Tiket dari Sistem Helpdesk* (bisa difilter) |

## Aturan kinerja yang dipakai

| KPI | Rumus | Target |
|---|---|---|
| Capaian revenue | aktual ÷ target | 100% |
| Status sales | ≥100% Tercapai · 90–99% Perlu perhatian · <90% Perlu intervensi | – |
| Batas SLA tiket | Tinggi 4 jam · Sedang 8 jam · Rendah 24 jam | – |
| Tiket tepat waktu | jumlah tiket selesai ≤ batas SLA ÷ jumlah tiket | 90% |

Rumus ini sama persis di Excel dan di `index.html` (bagian `ATURAN KINERJA`).

## Cara membuka dashboard

**Cara 1: GitHub Pages (paling mudah, bisa dibuka dari HP)**
1. Upload folder ini ke repository GitHub.
2. Buka **Settings → Pages**, pilih *Branch: main*, folder */ (root)*, lalu **Save**.
3. Tunggu ±1 menit, dashboard bisa dibuka di `https://<username>.github.io/<nama-repo>/`.

**Cara 2: Di laptop**
- Buka terminal di folder ini, jalankan `python -m http.server`, lalu buka `http://localhost:8000`.
- Atau klik dua kali `index.html`, lalu pilih file `sales.csv` dan `tiket.csv` saat diminta.

## Cara mengubah data

1. Edit `data/sales.csv` atau `data/tiket.csv` (bisa dengan Excel, Google Sheets, atau Notepad).
   Kalau mengedit di file Excel, simpan ulang sheet-nya sebagai CSV dengan nama kolom yang sama.
2. Simpan, lalu muat ulang dashboard. Angka, grafik, dan status ikut berubah.

## Latihan untuk mahasiswa

1. Ubah waktu selesai 2 tiket Citra yang terlambat supaya tepat waktu. Berapa persen tepat waktunya sekarang?
2. Tambahkan satu sales baru di `sales.csv`. Apakah capaian tim naik atau turun?
3. Pilih satu gap kinerja, tentukan penyebabnya (model Gilbert) dan usulkan intervensinya.

## Pengembangan berikutnya

Excel → **dashboard HTML (repo ini)** → aplikasi web/mobile dengan database, login per pengguna, dan input data langsung dari lapangan.
