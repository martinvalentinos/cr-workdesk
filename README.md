# CR Workdesk • TSEL — GitHub Pages

Dashboard Change Request dengan tampilan **Overview, CR Register, Follow-ups, dan Reconciliation**.

## Status
- Versi GitHub Pages memakai **bootstrap nol record**; tidak ada data perusahaan dalam repo atau artefak deploy.
- **Impor Excel** membaca XLSX secara lokal di browser, tanpa mengunggah file ke GitHub. Perubahan pada mode manual berada di memori halaman dan hilang ketika reload; ekspor CSV sebagai cadangan.
- **Microsoft Graph live read/write belum aktif atau diverifikasi.** Membutuhkan Entra SPA, persetujuan organisasi, koneksi workbook dan uji sinkronisasi aman.
- Website CR Workdesk yang sudah dipublikasikan sebelumnya tidak diubah.

## Tes lokal
Prasyarat: Node.js 22 dan Python 3.

```sh
npm test
npm run serve
```

Buka http://localhost:8080.

## GitHub Pages
Buka **Settings → Pages → Build and deployment → Source: GitHub Actions** bila diperlukan. Workflow `pages.yml` menjalankan tes dan membuat `dist/data.js` dengan nol record sebelum deploy. URL setelah sukses:

https://martinvalentinos.github.io/cr-workdesk/

## Keamanan
Repository ini **Public**. Dilarang menambahkan XLSX, CSV asli, snapshot, data CR internal, token, client secret, atau URL SharePoint perusahaan. `.gitignore` dan CI hanya kontrol dasar. Hosting GitHub Pages bersifat publik dan tidak menggantikan kebijakan akses internal. Graph disetel nonaktif sampai otorisasi perusahaan.

Basis UI dan model berasal dari dashboard CR yang telah dipakai pada proyek `rzqllh/cr-projects`, tanpa menyertakan dataset atau konfigurasi tenant.
