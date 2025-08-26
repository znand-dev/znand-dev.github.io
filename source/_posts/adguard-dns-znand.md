title: '💡DNS-over-HTTPS (Advanced AdBlocker)'
date: 2025-05-24 08:31:49
cover: /img/diagram_adguard01.png
top_img: /img/default.png
tags: [Networking, Server, DNS]
---
## 👋🏻Welcome!

![AdGuard: Local DNS Resolver with upstream DNS servers through DNS over HTTPS ( DoH )](/img/diagram_adguard01.png)

Selamat datang [Znand's Blog](https://znand.my.id/)! Disini saya akan share DoH (DNS over HTTPS) yang sudah dikonfigurasi sebelumnya. Jika kamu mengalami masalah saat menggunakan DNS ini, kamu bisa melaporkan langsung ke saya via [Telegram](https://t.me/nandzie) atau lihat di [troubleshooting](https://adguard.com/en/support.html).

   Sebelumnya, AdGuard DNS merupakan layanan Public DNS gratis yang disediakan oleh AdGuard. Bagi saya, DNS ini sangat berguna sekali karena dapat menyediakan fitur:

- 🧱 Pemblokiran iklan & tracker =>	Gak perlu adblock di browser, langsung blok dari DNS
- 🔐 Perlindungan privasi	=> Mencegah pelacakan dari pihak ketiga
- ⚠️ Filter malware/phishing => Menghindari situs berbahaya sejak awal
- 🧒 Mode Keluarga (Family Mode) => Blokir konten dewasa + aktifkan Safe Search
- 🌐 Support DoH/DoT/DoQ => Aman & terenkripsi, gak bisa disadap ISP

Dijamin full filtering Ads, Trackers, Malware, Phising dan Konten dewasa karena sudah saya config semua filteringnya.

Silahkan setting di router, laptop, hp dll :

### Hostname only (Port 443)
```
dns.znand.my.id
```
### DNS-over-HTTPS
```
https://dns.znand.my.id/dns-query
```
### DNS-over-TLS                          
```
tls://dns.znand.my.id
```

### Statistic & Live Monitoring
- [DNS Stats](https://stats.znand.my.id/public-dashboards/a0b05deb37464a17b01cbc69eb65ac5a?orgId=1&refresh=5s)

### 🛠️Tools
- [Find & Check IP](https://whoer.net/)
- [DNSCheckTools](https://dnscheck.tools/)

Ada yang mau ditanyain? Komen aja dibawah ya.
