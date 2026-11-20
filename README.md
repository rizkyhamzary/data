# 🎨 Validator Kualitas Desain Konten Instagram

Web tool untuk validasi manual kualitas desain konten Instagram berdasarkan rubrik penilaian 4 indikator (Keseimbangan, Kesatuan, Tipografi, Warna).

## 📋 Deskripsi Penelitian

**Judul:** Klasifikasi Kualitas Desain Konten Instagram Menggunakan Metode CNN  
**Rubrik:** Penilaian empiris berbasis 4 indikator desain (skor 1–5 tiap indikator)  
**Dataset:** 232 citra Instagram (Organisasi & UMKM)

## 🚀 Cara Menggunakan

### Akses Web
Buka: **https://[username].github.io/[repo-name]/**

> Bagikan link di atas kepada validator Anda.

### Langkah Penilaian
1. Buka web — citra tampil otomatis satu per satu
2. Baca **Rubrik** (klik untuk buka/tutup) di panel kanan
3. Klik skor **1–5** untuk 4 indikator:
   - **Keseimbangan** — distribusi elemen
   - **Kesatuan** — keterpaduan gaya & warna
   - **Tipografi** — keterbacaan huruf
   - **Warna** — kontras & palet
4. Tambahkan Catatan (opsional)
5. Klik **💾 Simpan & Lanjut** → otomatis pindah ke citra berikutnya
6. Setelah selesai, klik **⬇ Ekspor CSV Hasil Validasi**

### Keyboard Shortcuts
| Tombol | Fungsi |
|--------|--------|
| `→` / `D` | Citra berikutnya |
| `←` / `A` | Citra sebelumnya |
| `Enter` / `S` | Simpan & lanjut |
| Klik gambar | Zoom in/out |

## 📁 Struktur File

```
data/
├── index.html        ← Web validator (buka di browser)
├── data.js           ← Daftar 232 citra (auto-generated)
├── README.md
└── images/           ← 232 citra .jpg
    ├── organisasi_*.jpg
    └── umkm_*.jpg
```

## 📊 Format Output CSV

CSV yang diekspor mengikuti format **FORM PENILAIAN KUALITAS DESAIN KONTEN INSTAGRAM** dengan kolom:

```
No | ID Citra | Nama File | Keseimbangan | Kesatuan | Tipografi | Warna | Skor Akhir | Label | Catatan
```

**Batas Label:**
- 🟢 **Baik**: Skor ≥ 3.75
- 🟡 **Sedang**: Skor 2.35 – 3.74
- 🔴 **Kurang baik**: Skor < 2.35

## 💾 Penyimpanan Data

- Hasil penilaian **tersimpan otomatis di localStorage browser**
- Tidak akan hilang meski halaman di-refresh
- Ekspor CSV kapan saja, termasuk penilaian parsial
- Tombol **Reset** untuk menghapus semua data penilaian

## 🌐 Deploy ke GitHub Pages

1. Upload semua file ini ke GitHub repository
2. Aktifkan **GitHub Pages** → Settings → Pages → Source: `main` / `root`
3. Bagikan link `https://[username].github.io/[repo-name]/` ke validator

> **Catatan:** Karena citra disimpan lokal di folder `images/`, pastikan folder `images/` juga di-push ke GitHub (perhatikan batas ukuran 100MB per file, total repo 1GB).

## ⚙️ Teknis

- **Pure HTML/CSS/JS** — tanpa framework, tanpa server
- **GitHub Pages compatible** — static site
- **Offline capable** setelah halaman dimuat
- Data tersimpan di **localStorage** per browser/perangkat validator
