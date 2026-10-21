# Flash Sitasi — TikTok AI Admin

Repository ini **terpisah sepenuhnya** dari `rickv-max/Flash-Sitasi`.

Backend untuk membuat draft balasan TikTok dengan Google Gemini. Tahap awal aman: **tidak mengirim balasan otomatis ke TikTok**. Semua API key disimpan di Vercel Environment Variables, tidak di GitHub.

## Endpoint
- `GET /api/health` — status layanan.
- `POST /api/preview` — menyusun draft Gemini dari teks komentar; autentikasi `x-admin-secret`.
- `POST /api/process-comment` — sengaja dinonaktifkan hingga izin API komentar TikTok resmi diperoleh dan keamanan webhook siap.

## Konfigurasi
Tambahkan `ADMIN_SECRET`, `GEMINI_API_KEY`, dan opsional `GEMINI_MODEL` melalui Vercel Project Settings → Environment Variables. Tidak perlu menaruh password atau API key di kode sumber. Setelah deploy, akses `/api/health` untuk tes.

Akun TikTok Business terverifikasi tidak otomatis memberikan akses TikTok Developer API. Balasan live membutuhkan aplikasi dengan izin API komentar, webhook bertanda tangan, batas frekuensi, deduplikasi, dan audit yang telah diuji.
