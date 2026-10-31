# Pterodactyl Egg - Next.js App Hosting

Kumpulan Egg Pterodactyl Panel buatan **PterokuDesu** untuk menjalankan dan mendeploy aplikasi **Next.js** secara otomatis dengan dukungan auto-detect package manager, git integration, dan manajemen proses runtime.

📖 **Panduan Penggunaan Lengkap:**  
[Cara Hosting Website Next.js di Panel PterokuDesu](https://www.pterokudesu.com/help/cara-hosting-website-nextjs-di-panel)

---

## 🛠️ Ringkasan Varian Egg

| Varian Egg | File JSON | Fitur Utama |
|---|---|---|
| **Standard** | `egg-next-js.json` | Runner standar dengan binding `0.0.0.0` & auto package manager detection. |
| **PM2 + Live Console** | `egg-next-js-pm2.json` | Menggunakan **PM2**, support **Auto Pull Git** saat restart, zero-downtime, dan live console command execution (beta). |

---

## 🚀 Fitur Utama

- **Auto Package Manager Detection**: Secara otomatis mendeteksi `pnpm-lock.yaml`, `yarn.lock`, atau `package-lock.json` untuk menentukan apakah menggunakan `pnpm`, `yarn`, atau `npm`.
- **Auto Scaffold (`create-next-app`)**: Jika container/folder server kosong dan tidak ada `GIT_URL`, script instalasi akan otomatis membuat project Next.js baru menggunakan versi yang ditentukan di `NEXT_VERSION`.
- **Private & Public Git Clone**: Mendukung auto-clone dari repository publik maupun privat (dengan `USERNAME` + `ACCESS_TOKEN`).
- **Auto-Update (PM2 Version)**: Menarik update terbaru dari repository git setiap kali server dinyalakan ulang jika `AUTO_UPDATE=1`.
- **Flexible Run Modes**: Mendukung mode `start` (Production build) dan mode `dev` (Development hot-reload).

---

## 📋 Variabel Environment

| Variabel | Default | Deskripsi |
|---|---|---|
| `NEXT_VERSION` | `latest` | Versi Next.js yang di-scaffold jika folder kosong (`latest`, `16.0.10`, dll). |
| `NODE_RUN_ENV` | `start` | Runtime mode: `start` (Production) atau `dev` (Development). |
| `PACKAGE_MANAGER`| `auto` | Pilihan package manager: `auto`, `npm`, `pnpm`, atau `yarn`. |
| `GIT_URL` | *(kosong)*| URL repository git untuk di-clone otomatis. |
| `GIT_BRANCH` | *(kosong)*| Nama branch target (contoh: `main`, `master`). |
| `AUTO_UPDATE` | `0` | Set `1` untuk auto `git pull` setiap kali server dinyalakan. |
| `USERNAME` | *(kosong)*| Git Username (diperlukan untuk private repo). |
| `ACCESS_TOKEN` | *(kosong)*| Personal Access Token / PAT (diperlukan untuk private repo). |
| `ENABLE_CONSOLE_CMD` | `0` | *(Varian PM2)* Set `1` untuk mengaktifkan eksekusi perintah terminal via Console panel. |

---

## ⚙️ Cara Import ke Panel

1. Masuk ke **Pterodactyl Admin Panel** -> **Nests** -> **Eggs**.
2. Klik tombol **Import Egg**.
3. Select file `egg-next-js.json` atau `egg-next-js-pm2.json`.
4. Pilih Nest target (misal: *Node.js* atau *Web Hosting*).
5. Simpan dan Egg siap digunakan saat pembuatan Server baru.

---

## 🔗 Dokumentasi & Komunitas
- **Tutorial & FAQ:** [https://www.pterokudesu.com/help/cara-hosting-website-nextjs-di-panel](https://www.pterokudesu.com/help/cara-hosting-website-nextjs-di-panel)
- **Grup Telegram:** [https://zass.in/tele/gc/PterokuDesu]
- **Maintainer:** `support@pterokudesu.com` / **PterokuDesu**
