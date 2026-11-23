# redirect-rym

Short link redirect untuk cugud.com, di-deploy ke Vercel.

| Short link | Tujuan |
|---|---|
| https://cugud.com/registrasi-natal-rym-2026 | https://forms.gle/7K13oWQxyyGJb8ym6 |

QR code ada di `qr/` (PNG untuk cetak/medsos, SVG untuk desain, `-logo.png` versi dengan logo RYM di tengah).

## Cara kerja

Short link bukan redirect server (307), tapi halaman HTML (`registrasi-natal-rym-2026.html`,
`cleanUrls` di `vercel.json`) berisi meta Open Graph + auto-redirect (meta refresh + JS).
Dengan begitu preview saat dibagikan (WhatsApp dll) memakai judul, deskripsi dan
gambar `og/registrasi-natal-rym-2026.jpg`, bukan preview Google Forms.

## Tambah/ubah link

Salin `registrasi-natal-rym-2026.html` jadi `<slug>.html`, ganti URL tujuan dan tag OG,
lalu `git push`. Vercel (`cuguds-projects/redirect-rym`) tersambung ke fork
`septalonika/redirect-rym` (akun GitHub yang dipakai login Vercel) dan deploy otomatis
setiap push ke `main` di fork itu. Remote `origin` di clone lokal diatur push ke dua
repo sekaligus (`cugud/redirect-rym` dan fork), jadi satu `git push` cukup.
`permanent: false` (307) supaya tujuan bisa diganti tanpa tersangkut cache browser.
