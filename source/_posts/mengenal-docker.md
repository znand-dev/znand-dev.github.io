title: 'Mengenal Docker: Panduan Lengkap dari Nol'
author: Januar Ismunandar
date: 2025-06-16 10:25:00
tags:
  - Container
  - DevOps
  - Virtualization
  - Kubernetes
  - Deployment
  - CI/CD
cover: /img/banner_docker.png
top_img: /img/default.png
---
# 🚢 Mengenal Docker: Panduan Lengkap dari Nol 

Halo sobat DevOps, Dev dan SysAdmin! 👩‍💻  
Di artikel ini, kita bakal bahas tuntas **apa itu Docker**, **kenapa harus pakai Docker**, dan **gimana cara mulai pake Docker**.  

---

## 📦 Apa Itu Docker?

**Docker** adalah platform open-source yang memungkinkan kita untuk membungkus aplikasi dan semua dependensinya ke dalam sebuah _container_.  
Container itu ibarat "mini-VM" yang super ringan, cepat, dan konsisten dijalankan di berbagai environment.

> 🔥 *"Build once, run anywhere!"* 🔥

---

## ⚡ Kenapa Harus Pakai Docker?

Beberapa alasan kenapa Docker itu wajib dicoba:

- ✅ **Portabilitas:** Aplikasi bisa jalan di laptop, server, atau cloud dengan setup yang sama.
- ✅ **Isolasi:** Tiap container berjalan terpisah. No more konflik dependency antar aplikasi.
- ✅ **Efisiensi:** Lebih ringan dan cepat dibanding VM.
- ✅ **CI/CD Ready:** Sangat cocok untuk deployment otomatis dan DevOps workflow.

---

## ⚔️ Perbandingan Docker vs Alternatifnya

| Teknologi     | Kelebihan Utama                                           | Kekurangan                                           | Cocok Untuk                            |
|---------------|------------------------------------------------------------|------------------------------------------------------|----------------------------------------|
| **Docker**    | Ekosistem luas, dokumentasi lengkap, dukungan komunitas besar | Butuh daemon (dockerd), kadang berat di resource    | Developer, CI/CD, project individual   |
| **Podman**    | Tidak butuh daemon, rootless (lebih secure), CLI mirip Docker | Kurang banyak image dibanding Docker Hub            | Server production, secure containers   |
| **containerd**| Lightweight, runtime resmi Kubernetes                     | Kurang friendly untuk dev langsung                  | Kubernetes runtime, integrasi CRI      |
| **CRI-O**     | Native Kubernetes container runtime                        | Fungsionalitas terbatas, hanya untuk Kubernetes     | Cluster Kubernetes, enterprise         |
| **LXC / LXD** | Mirip VM, bisa jalankan full OS                           | Konfigurasi lebih kompleks                          | Virtualisasi ringan, testing OS        |
| **RKT** (deprecated) | Security by design, systemd integration        | Sudah tidak dikembangkan                             | Sistem lama berbasis CoreOS            |

> 🔥 **Note:** Docker sekarang tidak menjadi runtime default di Kubernetes, digantikan oleh containerd/CRI-O sejak Kubernetes 1.20+

---

## 🧱 Arsitektur Docker: Gambaran Besar yang Perlu Lo Pahami

![Docker Architecture](/img/docker_arch2.gif)

Docker memiliki 3 komponen utama yang bekerja sama membentuk ekosistem containerisasi modern:

---

### 🧑‍💻 1. Client

🔹 Tempat lo menjalankan perintah Docker seperti:

- `docker build`
- `docker pull`
- `docker run`
- `docker push`

🔹 Client bisa berupa:

- **CLI** (Command Line Interface)
- **Remote API**

---

### 🖥️ 2. Docker Host (Docker Daemon)

💥 Di sinilah "mesin" utama Docker berada:

- **Docker Daemon (`dockerd`)** menerima perintah dari client.
- Melakukan build image dari Dockerfile.
- Menjalankan container dari image.
- Berkomunikasi dengan registry untuk pull/push image.
- Menyimpan container & image secara lokal.

---

### 📦 3. Registry

🔁 Tempat untuk menyimpan dan mengambil image Docker.

- **Public registry**: Docker Hub, GitHub Container Registry.
- **Private registry**: Bisa dibangun sendiri di perusahaan.

---

### 🔄 Alur Proses:

```bash
docker build  -> Dockerfile diubah jadi image (⬅️ Build)
docker push   -> Image dikirim ke Registry (⬆️ Push)
docker pull   -> Ambil image dari Registry (⬇️ Pull)
docker run    -> Jalankan container dari image (▶️ Run)
```

---

### 🧊 Kesimpulan:
> **Docker mempermudah proses pengembangan, testing, dan deployment aplikasi dengan container yang ringan dan konsisten.**

---

## 🔧 Install Docker (Linux / Windows / Mac)

### 💻 Ubuntu / Debian
```bash
sudo apt update
sudo apt install docker.io -y
sudo systemctl enable --now docker
```

### 🪟 Windows / 🍎 Mac
Download langsung dari sini: [https://www.docker.com/products/docker-desktop](https://www.docker.com/products/docker-desktop)

> Jangan lupa aktifin WSL2 (untuk Windows) biar lancar guys!

---

## 🚀 Perintah Docker Dasar

| Perintah                       | Fungsi                                      |
|-------------------------------|---------------------------------------------|
| `docker version`              | Cek versi Docker                            |
| `docker ps`                   | Lihat container yang sedang jalan           |
| `docker images`               | Daftar image yang dimiliki                  |
| `docker pull nginx`           | Download image dari Docker Hub             |
| `docker run -d -p 8080:80 nginx` | Jalankan container nginx di port 8080 |
| `docker stop <id>`            | Hentikan container                          |
| `docker rm <id>`              | Hapus container                             |
| `docker rmi <image>`          | Hapus image                                 |

---

## 📁 Dockerfile: Resep Bikin Image Sendiri

Contoh Dockerfile sederhana:
```Dockerfile
# Gunakan image dasar
FROM python:3.11-slim

# Set working directory
WORKDIR /app

# Copy semua file ke dalam container
COPY . .

# Install dependency
RUN pip install -r requirements.txt

# Jalankan aplikasi
CMD ["python", "app.py"]
```

Build image:
```bash
docker build -t myapp:latest .
```

---

## 🔥 Docker Compose: Multi-Container Made Easy

Contoh `docker-compose.yml`:
```yaml
version: "3"
services:
  web:
    image: nginx
    ports:
      - "8080:80"
  redis:
    image: redis
```

Jalankan dengan:
```bash
docker-compose up -d
```

---

## 🌐 Docker Hub dan Private Registry

- Docker Hub: [https://hub.docker.com](https://hub.docker.com)
- Push image:
```bash
docker tag myapp yourname/myapp
docker push yourname/myapp
```

---

## 📊 Monitoring dan Tips Pro

- Gunakan `docker stats` buat cek penggunaan resource.
- Gunakan tools kayak **Portainer**, **Watchtower**, dan **Grafana + Prometheus** buat monitoring lebih advanced.
- Jangan lupa tambahkan `.dockerignore` agar build lebih cepat dan ringan.

---

## 🧠 Tips Profesional

- Selalu gunakan tag image versi (`myapp:1.0.1`) daripada `latest`.
- Audit image dengan tools seperti `trivy` atau `docker scan`.
- Simpan file konfigurasi environment di `.env` dan jangan upload ke repo publik.

---

## 🔚 Penutup

Docker itu bagaikan senjata rahasia di dunia modern DevOps dan cloud.  
Belajar sekali, manfaatnya bisa dipakai seumur hidup karier lo! 🔥

> Kalau ada pertanyaan, tulis di kolom komentar blog ini ya all! 🙌  
> Jangan lupa follow blog ini buat update konten keren lainnya, terima kasih.

---
Source: [Medium](https://medium.com/@saddy.devs/understanding-docker-architecture-934ecd042b5f)
🛠 Ditulis oleh: [znand-dev](https://github.com/znand-dev)  
📅 Update terakhir: 2025-06-16

