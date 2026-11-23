# redirect-rym

Short link redirect untuk cugud.com, di-deploy ke Vercel.

| Short link | Tujuan |
|---|---|
| https://cugud.com/registrasi-natal-rym-2026 | https://forms.gle/7K13oWQxyyGJb8ym6 |

QR code ada di `qr/` (PNG untuk cetak/medsos, SVG untuk desain).

## Tambah/ubah link

Edit `redirects` di `vercel.json`, lalu push ke `main`. Vercel deploy otomatis.
`permanent: false` (307) supaya tujuan bisa diganti tanpa tersangkut cache browser.
