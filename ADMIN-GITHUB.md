# Atlantica Classic V3 Exynos — Web Editor + GitHub Publish

Perubahan utama:
- Ranking, Latest News, Server Information, Download Client, dan Manual Patch sekarang memakai `data/site-data.js` sebagai sumber data publik.
- Data tidak lagi bergantung pada `localStorage` untuk data yang tampil ke semua pengunjung.
- Di mode Admin ada tombol **Publish ke GitHub**.
- Publish langsung meng-commit `data/site-data.js` ke repository GitHub.
- Token GitHub hanya dipakai di browser/session dan tidak ditulis ke source website.

## Cara pakai

1. Upload/replace seluruh isi folder `V3-main` ke repository GitHub `V3`.
2. Buka website GitHub Pages.
3. Klik ikon gembok di kanan bawah lalu masukkan PIN admin yang sudah digunakan sebelumnya.
4. Edit Ranking / News / Server Information / Download / Patch.
5. Di bagian Ranking klik **Publish ke GitHub**.
6. Isi GitHub Fine-grained Token jika belum ada.
7. Klik **Publish**.
8. Setelah commit selesai, tunggu GitHub Pages selesai deploy lalu refresh website.

## Token GitHub

Gunakan **Fine-grained Personal Access Token** dan batasi hanya ke repository `V3`.
Permission yang diperlukan:
- Repository access: hanya `V3`
- Contents: Read and write

Jangan memasukkan token GitHub ke dalam file HTML/JS. Token dimasukkan hanya pada popup Publish.

## File penting

`data/site-data.js` adalah database konten website versi statis. Jika file ini berubah melalui tombol Publish, semua pengunjung akan membaca data yang sama setelah GitHub Pages memperbarui deployment.

`index.html` tetap menjadi halaman utama.
