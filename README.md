# 🚀 Digiflazz Pay Point

![GitHub repo size](https://img.shields.io/github/repo-size/dwiexe/Digiflazz-Pay-Point)
![GitHub stars](https://img.shields.io/github/stars/dwiexe/Digiflazz-Pay-Point?style=social)
![GitHub forks](https://img.shields.io/github/forks/dwiexe/Digiflazz-Pay-Point?style=social)
![License](https://img.shields.io/badge/license-MIT-blue)

Aplikasi **PPOB (Payment Point Online Bank)** berbasis web yang terintegrasi dengan API Digiflazz untuk melakukan berbagai transaksi digital seperti pulsa, paket data, dan token listrik.

---

## ✨ Features

* 🔌 Integrasi API Digiflazz
* 📱 Top up pulsa & paket data
* 💡 Pembelian token listrik
* 🧾 Manajemen transaksi
* ⚡ Backend TypeScript
* 📦 Arsitektur modular & scalable

---

## 🛠️ Tech Stack

* **Backend**: Node.js, TypeScript
* **Package Manager**: PNPM
* **API**: Digiflazz
* **Database**: Drizzle ORM
* **Validation**: Zod / OpenAPI

---

## 📂 Project Structure

```bash
.
├── lib/                # Core modules & API logic
├── scripts/            # Utility scripts
├── package.json        # Project dependencies
├── tsconfig.json       # TypeScript config
├── pnpm-lock.yaml      # Lock dependencies
└── replit.md           # Replit config
```

---

## ⚙️ Installation

Clone repository:

```bash
git clone https://github.com/dwiexe/Digiflazz-Pay-Point.git
cd Digiflazz-Pay-Point
```

Install dependencies:

```bash
pnpm install
```

---

## ▶️ Run Project

```bash
pnpm start
```

or:

```bash
pnpm dev
```

---

## 🔐 Environment Variables

Create `.env` file:

```env
DIGIFLAZZ_USERNAME=your_username
DIGIFLAZZ_API_KEY=your_api_key
```

---

## 📸 Preview

> Tambahkan screenshot aplikasi di sini agar repo kamu terlihat profesional.

---

## 🚀 Future Improvements

* Dashboard UI
* Riwayat transaksi
* Multi-user system
* Payment gateway integration

---

## ⚠️ Notes

* Jangan upload `.env` ke GitHub
* Gunakan `.gitignore` untuk keamanan
* Pastikan API Digiflazz aktif

---

## 🤝 Contributing

Kontribusi terbuka untuk siapa saja 🚀
Silakan fork repo ini dan buat pull request.

---

## 📄 License

MIT License

---

## 👨‍💻 Author

**dwiexe**
🌐 https://github.com/dwiexe
# Menghasilkan file README.md dengan data terbaru
markdown_content = """# Digiflazz Pay Point - Panduan Deployment VPS & Build APK

Repositori ini berisi sistem monorepo untuk aplikasi PPOB (Payment Point Online Bank) yang terintegrasi dengan API Digiflazz. Dokumentasi ini merinci cara memindahkan proyek dari Replit ke VPS Ubuntu, mengonfigurasi domain, dan melakukan build APK Android.

---

## 🏗️ Struktur Proyek
- **`artifacts/api-server`**: Mesin Backend (Node.js/Express/TypeScript).
- **`artifacts/ppob-app`**: Aplikasi Mobile (React Native/Expo).

---

## 🚀 Langkah 1: Persiapan Server (VPS)
Login ke VPS Ubuntu Anda dan jalankan perintah berikut untuk menyiapkan lingkungan:

# Update sistem
apt update && apt upgrade -y

# Install pnpm secara global
curl -fsSL [https://get.pnpm.io/install.sh](https://get.pnpm.io/install.sh) | sh -
source ~/.bashrc

# Clone repositori
git clone [https://github.com/dwiexe/Digiflazz-Pay-Point.git](https://github.com/dwiexe/Digiflazz-Pay-Point.git)
cd Digiflazz-Pay-Point

# Install dependensi monorepo
pnpm install
⚙️ Langkah 2: Konfigurasi Backend (api-server)
Backend berjalan di port 3000 menggunakan PM2 agar tetap menyala 24 jam.

Bash
cd artifacts/api-server

# Buat file Environment
nano .env
Isi dengan:

Cuplikan kode
DIGIFLAZZ_USERNAME=username_anda
DIGIFLAZZ_API_KEY=apikey_anda
PORT=3000
Build dan Jalankan:

Bash
pnpm add -g pm2 typescript
pnpm run build
pm2 start dist/index.mjs --name "api-backend"
pm2 save
pm2 startup
🌐 Langkah 3: Nginx & SSL (HTTPS)
Menghubungkan domain api.dwizy22.my.id ke port 3000.

Bash
# Install Nginx & Certbot
apt install nginx certbot python3-certbot-nginx -y

# Buat konfigurasi Nginx
nano /etc/nginx/sites-available/api.dwizy22.my.id
Tempelkan kode ini:

Nginx
server {
    listen 80;
    server_name api.dwizy22.my.id;

    location / {
        proxy_pass http://localhost:3000;
        proxy_http_version 1.1;
        proxy_set_header Upgrade $http_upgrade;
        proxy_set_header Connection 'upgrade';
        proxy_set_header Host $host;
        proxy_cache_bypass $http_upgrade;
    }
}
Aktifkan Domain:

Bash
ln -s /etc/nginx/sites-available/api.dwizy22.my.id /etc/nginx/sites-enabled/
nginx -t
systemctl restart nginx

# Pasang SSL Gratis
certbot --nginx -d api.dwizy22.my.id
📱 Langkah 4: Build APK Android (ppob-app)
Arahkan aplikasi mobile ke server baru dan mulai proses build.

Update API URL: Edit file artifacts/ppob-app/services/api.ts dan pastikan baris pertama berisi:

TypeScript
const BASE_URL = '[https://api.dwizy22.my.id/api](https://api.dwizy22.my.id/api)';
Jalankan Build via EAS:

Bash
cd artifacts/ppob-app
npx eas-cli login
npx eas-cli build:configure
npx eas-cli build --platform android --profile preview
🛠️ Maintenance (Perawatan)
Cek Log Backend: pm2 logs api-backend

Restart Server: pm2 restart api-backend

Cek Status Nginx: systemctl status nginx

Dibuat untuk mempermudah transisi dari server Replit ke VPS Mandiri.
"""

with open('README-v2.md', 'w') as f:
f.write(markdown_content)


Your PDF file is ready
[file-tag: code-generated-file-0-1776966770382294327]

File `README-v2.md` di atas sudah saya sesuaikan dengan domain Anda (`api.dwizy22.
