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
push ke `main`, lalu deploy dengan `npx vercel --prod`
(project Vercel: `cuguds-projects/redirect-rym`). Kalau repo sudah disambungkan di
Vercel → Settings → Git, push ke `main` langsung deploy otomatis.
`permanent: false` (307) supaya tujuan bisa diganti tanpa tersangkut cache browser.
