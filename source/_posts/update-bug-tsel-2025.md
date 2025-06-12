title: "⚙️📲Update Bug Telkomsel 2025 (SSL/SNI Only)"
cover: /img/banner_bugisp2.png
top_img: /img/default.png
tags:
  - Tunneling
  - ISP
  - Inject
date: 2025-05-29 21:49:49
---
Halo semuanya! Kali ini saya akan membagikan bug telkomsel 2025, beberapa waktu lalu saya sudah membagikan bug operator XL Axiata, namun karena tidak semua TKP, bug tersebut support. Kali ini saya bagikan Bug Telkomsel yang mungkin work di TKP kalian. Dan paket yang paling sering digunakan untuk inject adalah kuota Ilmupedia. Berikut saya share bugnya:

### SSL/SNI 
```
ruangguru.com:443
104.18.53.42:443
stripchat.page:443
104.17.3.81:443
api.midtrans.com:443
104.22.20.245:443
edu.ruangguru.com:443
pemira.unnes.ac.id:443
ar-raniry.ac.id:443
```

### Payload

```
GET / HTTP/1.1[crlf]Host: [host][crlf]Connection: Upgrade[crlf]Content-Lenght: FACEBOOK Loly Hunter[crlf]User-Agent: [ua][crlf]Upgrade: websocket[crlf][crlf]
```

```
GET /cdn-cgi/trace HTTP/1.1[crlf]Host: isibugnya.com[crlf][crlf]GET-WSS / HTTP/1.1[crlf]Host: [host][crlf]User-Agent: [ua][crlf]Upgrade: Websocket[crlf][crlf]
```