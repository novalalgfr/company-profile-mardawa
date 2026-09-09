# CONTEXT.md — Company Profile PT Mardawa Intiguna Persada

Dokumen ini adalah acuan tunggal (single source of truth) untuk pengembangan website company profile. Berikan file ini ke AI/developer baru agar tidak perlu penjelasan dari awal.

## 1. Informasi Perusahaan
- **Nama resmi:** PT Mardawa Intiguna Persada
- **Bidang usaha:** IT Consultant
- **Bahasa website:** Bahasa Indonesia (satu bahasa saja)
- **Tagline/Slogan:** _(belum ditentukan — isi saat konten final tersedia)_
- **Visi & Misi:** _(placeholder — isi kemudian)_
- **Sejarah singkat:** _(placeholder — isi kemudian)_

## 2. Tech Stack
- **Framework:** Astro
- **Styling:** Tailwind CSS
- **Sumber konten:** Hardcode langsung di komponen (belum pakai Content Collections atau CMS — bisa dimigrasikan nanti jika dibutuhkan)
- **Interaktivitas:** Statis penuh kecuali ada kebutuhan khusus (form contact, dsb — pakai Astro Island bila perlu)
- **Deployment:** Belum ditentukan (kandidat: Vercel atau Netlify, keduanya native support Astro)

## 3. Branding
- **Logo:** Sudah tersedia, akan disusulkan oleh klien (taruh di `src/assets/logo.*` saat diterima)
- **Brand color:** Sudah tersedia, akan disusulkan oleh klien — akan disandingkan/disesuaikan dengan token warna di bawah begitu diterima
- **Font/Typography:** lihat token desain di bawah

## 3a. Arah Desain — "Modern Tech"
Kesan yang ingin dibangun: konsultan IT yang presisi secara teknis tapi tetap approachable, cocok untuk target klien campuran (enterprise, startup, maupun UKM) — bukan gaya startup kaleng-kalengan, bukan juga korporat kaku.

**Catatan penting:** token di bawah ini adalah default sementara sebelum brand color asli dari klien diterima. Begitu logo & brand color resmi masuk, sesuaikan/gantikan aksen warna di bawah agar selaras dengan identitas resmi perusahaan.

**Warna (base palette sementara):**
| Token | Hex | Peran |
|---|---|---|
| `background` | `#FAF9F6` | Latar utama, off-white hangat (bukan putih polos/cream klise) |
| `text-primary` | `#1C1F26` | Charcoal, warna teks utama & headline |
| `text-secondary` | `#5A6270` | Abu kebiruan untuk teks sekunder/deskripsi |
| `accent` | `#2D5BFF` | Biru elektrik jenuh — dipakai sangat sedikit, hanya di 1-2 titik fokus (CTA utama, highlight kecil), bukan disebar di semua elemen |
| `surface` | `#F0EFEA` | Warna section alternate/card, sedikit lebih gelap dari background |
| `border` | `#DEDCD4` | Garis pembatas tipis (hairline), bukan shadow tebal |

**Tipografi:**
- Headline: sans-serif geometris dengan tracking rapat (kandidat: `General Sans`, `Söhne`, atau fallback `Inter` dengan letter-spacing disesuaikan)
- Body: sans-serif netral, ukuran nyaman baca, line-length < 80 karakter
- Elemen data/teknis kecil (misal versi, tanggal, kode): monospace tipis — dipakai terbatas, bukan untuk label biasa
- Hindari: all-caps untuk label, eyebrow text di atas tiap heading, em-dash berlebihan pada judul

**Layout:**
- Hero: komposisi asimetris/sedikit overlap, bukan center-align standar — headline besar sebagai elemen visual utama
- Section berikutnya: campuran alignment kiri untuk teks panjang, grid untuk services/cards
- Spacing: banyak white space, hindari kartu seragam dengan border-radius & shadow yang sama persis di semua elemen — beri hierarki
- Motion: minim, hanya satu momen reveal yang disengaja (misal saat hero load), hindari fade-in/slide-up otomatis di semua section

**Yang dihindari (agar tidak terasa generic/AI-made):**
- Warna cream #F4F1EA + serif + aksen terracotta (kombinasi paling umum dipakai AI)
- Kartu SaaS seragam dengan shadow abu-abu lembut di semua tempat
- Label "WORD — fragment" dengan em dash, eyebrow ALL CAPS, atau tanda panah "→" di semua tombol/link

## 4. Struktur Halaman

### Home (`/`)
- Hero section (headline, sub-headline, CTA "Konsultasi Sekarang")
- Overview layanan (ringkas, link ke halaman Services)
- Keunggulan/"Kenapa Memilih Kami"
- Statistik singkat (tahun berdiri, jumlah proyek, klien — placeholder angka)
- Testimoni klien (placeholder, boleh dummy dulu)
- Client/partner logos (placeholder/dummy dulu)
- CTA akhir (ajakan kontak)

### About (`/about`)
- Profil perusahaan
- Visi & Misi
- Nilai-nilai perusahaan
- (Opsional) Tim/leadership — placeholder dulu jika belum ada data

### Services (`/services`)
Daftar layanan sementara (draft, silakan disesuaikan nanti):
1. **IT Consulting & Strategy** — pendampingan strategi transformasi digital
2. **Software Development** — pengembangan aplikasi custom (web & mobile)
3. **System Integration** — integrasi sistem dan API antar platform
4. **Cloud Solutions & Migration** — konsultasi dan migrasi infrastruktur ke cloud
5. **IT Infrastructure & Network Consulting** — perencanaan dan optimasi infrastruktur IT
6. **IT Staff Augmentation** — penyediaan tenaga ahli IT untuk proyek klien

Setiap layanan idealnya punya: judul, deskripsi singkat, ikon, dan opsional detail page.

### Portfolio/Case Studies
- **Di-skip untuk versi awal.** Section/halaman ini belum dibuat; bisa ditambahkan di iterasi berikutnya.

### Contact (`/contact`)
- Form kontak (nama, email, pesan) — placeholder, belum terhubung ke backend/email service
- Info kontak (alamat, telepon, email, WA) — **semua placeholder**, isi data asli menyusul
- Google Maps embed — placeholder lokasi

## 5. SEO & Lainnya
- Meta tags dasar (title, description) per halaman — pakai copy generik dulu
- OG image — placeholder, ganti setelah ada aset visual final
- Sitemap — generate otomatis via Astro integration jika diperlukan
- Analytics — belum ditentukan, bisa ditambahkan nanti (Google Analytics/Search Console)

## 6. Status & Item Terbuka (To-Do)
- [ ] Terima logo & brand color dari klien → update `tailwind.config`
- [ ] Finalisasi tagline, visi-misi, sejarah perusahaan
- [ ] Finalisasi daftar layanan (masih draft)
- [ ] Isi data kontak asli (alamat, telepon, email, WA, maps)
- [ ] Tentukan platform deployment
- [ ] (Iterasi berikutnya) Tambahkan halaman Portfolio/Case Studies
- [ ] Tentukan integrasi form contact (misal Resend/Formspree) bila dibutuhkan