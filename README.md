# Latihan Soal Biokim 2G

Flashcard latihan soal Responsi Biokim & Gizi, dibuat dari `Soal_Latihan_buatan_AI_Persiapan_Responsi_Biokim_Gizi_v2.xlsx`.

## Menjalankan

Situs ini statis (HTML/CSS/JS murni, tanpa build step). Cara pakai:

1. Buka `index.html` langsung di browser, **atau**
2. Deploy ke GitHub Pages: push folder ini ke repo, aktifkan Pages dari branch `main` (root).

## Fitur

- Semua 80 soal (40 Soal Overview, 20 Soal Kasus Hitung, 20 Soal Kasus Lanjutan) ditampilkan sebagai flashcard.
- Filter kelompok soal: **Semua**, **Soal Overview**, **Soal Kasus Hitung**, **Soal Kasus Lanjutan**.
- Tombol **Acak Soal** untuk mengacak urutan.
- Tombol **Tandai sudah dicek** di tiap kartu untuk progress tracking.
- **Mode Biasa**: ketuk kartu untuk langsung melihat jawaban.
- **Mode Tentamen**: jawaban tersembunyi — muncul tombol "Tampilkan Jawaban" yang harus diklik secara sadar setelah mencoba menjawab sendiri. Mode ini otomatis kembali ke Biasa saat halaman di-reload.
- Progress disimpan di `sessionStorage` (hilang saat tab ditutup).
- Sekitar separuh soal kasus hitung/lanjutan tidak mencantumkan nilai Faktor Stres secara eksplisit — peserta harus menentukan sendiri dari **Tabel Referensi** yang ditampilkan di bawah soal terkait.

## Struktur file

```
index.html           # markup + styling + logic UI
questions_data.js    # 80 soal dalam format window.QUESTIONS = [...] (digenerate dari xlsx)
build_data.py        # script python untuk regenerate questions_data.js dari xlsx baru
README.md            # dokumentasi ini
```

## Regenerate soal dari Excel baru

```bash
pip install openpyxl
python build_data.py
```

Pastikan file xlsx ada di folder yang sama dengan `build_data.py`, lalu jalankan perintah di atas. Output `questions_data.js` akan otomatis ter-update.

## Sumber data

Soal diambil dari tiga sheet pada file Excel:
- `Soal Overview (40)`
- `Soal Kasus Hitung (20)`
- `Soal Kasus Lanjutan (20)`

> **Dotleav's note\*:** Latihan soal ini dibuat berdasarkan OV, Laporan praktikum dan juga AI. Soal bertujuan untuk dijadikan alat latihan dan tidak menjamin Responsi akan sama persis.
