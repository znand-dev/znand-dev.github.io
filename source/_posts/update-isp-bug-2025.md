title: '⚙️📲Update Bug XL Axiata 2025 (Proxy & SSL/SNI)'
date: 2025-05-27 20:49:49
cover: /img/bg4.jpg
top_img: /img/default.png
tags: [Tunneling, ISP, Inject]
---

# 👋🏻Welcome!

Selamat datang kembali di [Znand's Blog](https://znand.my.id/)!. Kali ini saya akan share beberapa bug operator XL Axiata. XL Axiata merupakan salah satu dari sekian banyak ISP yang kuotanya bisa diinject. Kuota paling populer yang biasa di inject di ISP ini adalah XL Unlimited Turbo Super, XL Unlimited Turbo Video dan XL Edukasi. Walaupun paket unlimited nya masih mempunyai limit sekitar 200GB, tapi cukup okelah ya untuk pemakaian bulanan.

## XL Unlimited Turbo Video

### Proxy
```
quiz.vidio.com
quiz.int.vidio.com
quiz.staging.vidio.com
img.email3.vidio.com
172.67.5.14
104.22.5.240
104.16.17.120
162.159.128.7
```

### SSL/SNI
```
static-web.prod.vidiocdn.com
sb.scorecardresearch.com
token-media-vidio-com.akamaized.net
```

### Payload
```
GET / HTTP/1.1[crlf]Host: [host][crlf]Connection: Keep-Alive[crlf]User-Agent: [ua][crlf]Upgrade: websocket[crlf][crlf]
```

```
CONNECT /cdn-cgi/trace HTTP/1.1[crlf]Host: quiz.staging.vidio.com[crlf][crlf]GET-RAY / HTTP/1.1[crlf]Host: [host][crlf]Connection: Upgrade[crlf]User-Agent: [ua][crlf]Upgrade: websocket[crlf][crlf]
```

### Proxy New
```
personalization.vidio.com
shop.line.me
shop.vivo.com
s20.tiktokcdn.com
Nontontv.vidio.com
```

## XL Unlimited Turbo Super

### SSL/SNI

```
investor.fb.com
ava.game.naver.com
df.game.naver.com
account.pmang.game.naver.com
bbsdata.df.game.naver.com
care.pmang.game.naver.com
gamebulletin.nexon.game.naver.com 
plus-store.naver.com
z9star.game.naver.com 
```

### Payload (Enhanced)
```
PATCH http://[host] HTTP/1.1[crlf]Host: ava.game.naver.com:[crlf]Upgrade: websocket[crlf][crlf]UPDATE m.tiktok.com:/cdn-cgi/trace HTTP/1.1[crlf]Host: [host][crlf]Content-Length: 9999999[crlf]Upgrade: websocket[crlf][crlf]
```

## XL Edukasi

### Proxy
```
chat.sociomile.com
support.udemy.com
skillacademy.com
104.17.3.81
```

### SSL/SNI
```
vn-oc.ruangguru.com
id-oc.ruangguru.com
```

### Payload
```
GET / HTTP/1.1[crlf]Host: [host][crlf]Connection: Keep-Alive[crlf]User-Agent: [ua][crlf]Upgrade: websocket[crlf][crlf]
```

```
GET /cdn-cgi/trace HTTP/1.1[crlf]Host: support.udemy.com[crlf]Expect: 100-continue[crlf][crlf][split][crlf][crlf]GET- / HTTP/1.1[crlf]Host: [host_port][crlf]Connection: Upgrade[crlf]Upgrade: Websocket[crlf][crlf]
```