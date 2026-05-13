# Portfolio & Blog

**English** | [Türkçe](#portfolyo-ve-blog)

A modern, full-stack portfolio and blog built with **Next.js 15**, **TypeScript**, **Tailwind CSS**, and **MySQL + Prisma ORM**.

## Features

- **Public site**: Home, About, Blog (list + detail), Projects (list + detail), Contact
- **Admin dashboard**: Secure login, post/project CRUD, rich text editor (Tiptap), categories, tags, messages, site settings
- **SEO**: Dynamic metadata, sitemap, robots.txt
- **Dark mode**: System-aware theme toggle
- **Image uploads**: Authenticated file upload API
- **Contact form**: Database storage + optional email via Nodemailer

## Quick Start

### 1. Install dependencies

```bash
npm install
```

### 2. Configure environment

```bash
cp .env.example .env
```

Edit `.env` with your values:

```env
DATABASE_URL="mysql://user:password@localhost:3306/portfolio_blog"
NEXTAUTH_SECRET="your-random-secret-here"
NEXTAUTH_URL="http://localhost:3000"
ADMIN_EMAIL="admin@example.com"
ADMIN_PASSWORD="your-admin-password"
```

### 3. Set up the database

```bash
npm run db:push
npm run db:seed
```

### 4. Run the development server

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

Admin panel: [http://localhost:3000/admin](http://localhost:3000/admin)

### 5. Build for production

```bash
npm run build
npm run start
```

## Deploy to Netlify

1. Push to GitHub
2. Connect repo on [Netlify](https://netlify.com)
3. Add environment variables in Site Settings
4. Deploy!

## Environment Variables

| Variable | Description |
|---|---|
| `DATABASE_URL` | MySQL connection string |
| `NEXTAUTH_SECRET` | Random secret for NextAuth JWT signing |
| `NEXTAUTH_URL` | Full URL of your deployment |
| `ADMIN_EMAIL` | Admin login email (used by seed) |
| `ADMIN_PASSWORD` | Admin login password (used by seed) |
| `SMTP_HOST` | SMTP server host (optional) |
| `SMTP_PORT` | SMTP server port (optional) |
| `SMTP_USER` | SMTP username (optional) |
| `SMTP_PASS` | SMTP password (optional) |
| `SMTP_FROM` | From email address (optional) |

---

# Portfolyo ve Blog

**Türkçe** | [English](#portfolio--blog)

**Next.js 15**, **TypeScript**, **Tailwind CSS** ve **MySQL + Prisma ORM** ile geliştirilmiş modern, full-stack portfolyo ve blog uygulaması.

## Özellikler

- **Herkese açık site**: Ana sayfa, Hakkımda, Blog (liste + detay), Projeler (liste + detay), İletişim
- **Admin paneli**: Güvenli giriş, yazı/proje CRUD, zengin metin editörü (Tiptap), kategoriler, etiketler, mesajlar, site ayarları
- **SEO**: Dinamik metadata, sitemap, robots.txt
- **Karanlık mod**: Sistem temasına duyarlı tema değiştirme
- **Resim yükleme**: Kimlik doğrulamalı dosya yükleme API'si
- **İletişim formu**: Veritabanı kaydı + isteğe bağlı Nodemailer ile email

## Hızlı Başlangıç

### 1. Bağımlılıkları kur

```bash
npm install
```

### 2. Ortam değişkenlerini ayarla

```bash
cp .env.example .env
```

`.env` dosyasını kendi değerlerinle düzenle:

```env
DATABASE_URL="mysql://kullanici:sifre@localhost:3306/portfolio_blog"
NEXTAUTH_SECRET="rastgele-bir-sifre-buraya"
NEXTAUTH_URL="http://localhost:3000"
ADMIN_EMAIL="admin@example.com"
ADMIN_PASSWORD="admin-sifreniz"
```

### 3. Veritabanını kur

```bash
npm run db:push
npm run db:seed
```

### 4. Geliştirme sunucusunu başlat

```bash
npm run dev
```

[http://localhost:3000](http://localhost:3000) adresini aç

Admin paneli: [http://localhost:3000/admin](http://localhost:3000/admin)

### 5. Production için derle

```bash
npm run build
npm run start
```

## Netlify'e Deploy Etme

1. GitHub'a push yap
2. [Netlify](https://netlify.com)'de repo'yu bağla
3. Site Settings'den ortam değişkenlerini ekle
4. Deploy!

## Ortam Değişkenleri

| Değişken | Açıklama |
|---|---|
| `DATABASE_URL` | MySQL bağlantı string'i |
| `NEXTAUTH_SECRET` | NextAuth JWT imzalama için rastgele gizli anahtar |
| `NEXTAUTH_URL` | Deployment'ın tam URL'si |
| `ADMIN_EMAIL` | Admin giriş email'i (seed için kullanılır) |
| `ADMIN_PASSWORD` | Admin giriş şifresi (seed için kullanılır) |
| `SMTP_HOST` | SMTP sunucu host'u (isteğe bağlı) |
| `SMTP_PORT` | SMTP sunucu port'u (isteğe bağlı) |
| `SMTP_USER` | SMTP kullanıcı adı (isteğe bağlı) |
| `SMTP_PASS` | SMTP şifresi (isteğe bağlı) |
| `SMTP_FROM` | Gönderen email adresi (isteğe bağlı) |

---

## Project Structure / Proje Yapısı

```
src/
├── app/
│   ├── (public)/          # Public pages / Herkese açık sayfalar
│   │   ├── page.tsx       # Home / Ana sayfa
│   │   ├── about/         # About / Hakkımda
│   │   ├── blog/          # Blog list + detail / Blog liste + detay
│   │   ├── projects/      # Projects / Projeler
│   │   └── contact/       # Contact / İletişim
│   ├── admin/             # Admin dashboard (protected) / Admin paneli (korumalı)
│   │   ├── login/         # Login / Giriş
│   │   ├── posts/         # Posts / Yazılar
│   │   ├── projects/      # Projects / Projeler
│   │   ├── categories/    # Categories / Kategoriler
│   │   ├── tags/          # Tags / Etiketler
│   │   ├── messages/      # Messages / Mesajlar
│   │   └── settings/      # Settings / Ayarlar
│   ├── api/               # API routes / API rotaları
│   │   ├── auth/
│   │   ├── contact/
│   │   ├── upload/
│   │   └── admin/
│   ├── sitemap.ts
│   └── robots.ts
├── components/
│   ├── admin/             # Admin UI components
│   ├── contact/
│   ├── layout/            # Navbar, Footer
│   ├── providers/
│   └── ui/
├── lib/
│   ├── auth.ts            # NextAuth config
│   ├── prisma.ts          # Prisma client
│   ├── settings.ts        # Site settings loader
│   └── utils.ts           # Utility functions
└── middleware.ts           # Auth middleware
prisma/
├── schema.prisma
└── seed.ts
```

## Tech Stack / Teknolojiler

- **Framework**: Next.js 15 (App Router)
- **Language**: TypeScript (strict)
- **Styling**: Tailwind CSS + @tailwindcss/typography
- **Database**: MySQL via Prisma ORM
- **Auth**: NextAuth v5 (credentials provider)
- **Editor**: Tiptap (rich text)
- **Email**: Nodemailer
- **Icons**: Lucide React
