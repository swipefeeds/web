# SwipeFeed Website

Website statis resmi SwipeFeed dengan empat halaman:
- `index.html` — Home
- `privacy.html` — Privacy Policy
- `terms.html` — Terms of Service
- `contact.html` — Contact

## Fitur
- Bahasa Indonesia dan English (pilihan bahasa disimpan di browser).
- Logo menggunakan aset asli dari project Android SwipeFeed.
- Privacy Policy dan Terms of Service dimuat dari empat file teks asli di folder `content/` tanpa mengubah isi dokumennya.
- Kontak menggunakan `mailto:swipefeed.support@gmail.com`.
- Tombol Google Play disiapkan sebagai placeholder nonaktif sampai URL listing tersedia.
- HTML, CSS, dan JavaScript tanpa framework, build command, database, atau backend.

## Deploy melalui GitHub dan Cloudflare Pages

1. Buat repository GitHub baru, misalnya `swipefeed-website`.
2. Upload seluruh isi folder ini ke root repository (pastikan `index.html` berada di root).
3. Masuk ke Cloudflare Dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
4. Pilih repository `swipefeed-website`.
5. Pada pengaturan build:
   - Framework preset: **None**
   - Build command: **kosongkan**
   - Build output directory: `/` atau `.` (root repository)
6. Deploy. Cloudflare Pages akan menyajikan website statis dan melakukan deployment ulang setiap ada push ke branch yang terhubung.
7. Tambahkan domain `swipefeed.app` pada menu **Custom domains** Cloudflare Pages jika domain tersebut sudah dikelola di akun Cloudflare yang sama.

## Apakah Cloudflare Worker diperlukan?

Tidak untuk versi website ini. Semua halaman bersifat statis dan kontak langsung membuka aplikasi email melalui `mailto:`. Cloudflare Pages sudah cukup untuk hosting, HTTPS, dan deployment otomatis dari GitHub. Worker baru diperlukan jika kelak website membutuhkan endpoint/API, formulir kontak yang diproses di server, atau fungsi dinamis lain.

## Mengisi link Google Play nanti

Cari `disabled-link` di `index.html`. Setelah URL listing tersedia, ganti `href="#download"` pada kedua tombol Google Play dengan URL listing resmi, lalu hapus atribut `aria-disabled="true"` dan class `disabled-link`.

## Catatan

- File kebijakan di `content/` disalin langsung dari `app/src/main/assets/` pada project Android yang diberikan.
- Tanggal pembaruan dokumen mengikuti isi sumber: 14 November 2026.
- Google Fonts digunakan untuk tipografi; jika tidak tersedia, website tetap menggunakan fallback sans-serif.
