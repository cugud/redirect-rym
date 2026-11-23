# redirect-rym

Short link redirect untuk cugud.com, di-deploy ke Vercel.

| Short link | Tujuan |
|---|---|
| https://cugud.com/registrasi-natal-rym-2026 | https://forms.gle/7K13oWQxyyGJb8ym6 |

QR code ada di `qr/` (PNG untuk cetak/medsos, SVG untuk desain, `-logo.png` versi dengan logo RYM di tengah).

## Tambah/ubah link

Edit `redirects` di `vercel.json`, push ke `main`, lalu deploy dengan `npx vercel --prod`
(project Vercel: `cuguds-projects/redirect-rym`). Kalau repo sudah disambungkan di
Vercel → Settings → Git, push ke `main` langsung deploy otomatis.
`permanent: false` (307) supaya tujuan bisa diganti tanpa tersangkut cache browser.
