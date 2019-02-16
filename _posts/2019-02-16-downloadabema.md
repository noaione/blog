---
layout: post
title: "Ripping: Download Abema.TV Video"
date:   2019-02-16
excerpt: "One of the best Japanese VOD Website"
tag:
- fansub 
- blog
- ripping
comments: true
feature: https://blog.n4o.xyz/blog/assets/img/abemadl/thumb.png
---

*Disponsori oleh NoAiOne*

Yang dibutuhin:
- PC
- Python 3+
- FFMpeg (Opsional)
- VPN/Proxy Jepang

**Install Python3.6 terlebih dahulu: [Tutorial](https://xo.tc/installing-python-36-on-windows.html)**

**Download FFMpeg Static dan taruh file `ffmpeg.exe` ke `C:\Windows`**

## Langkah-Langkah 

Setelah beres install Python3.6, buka CMD dan arahkan ke folder favorit

{% capture images %}
	https://blog.n4o.xyz/blog/assets/img/abemadl/01.png
{% endcapture %}
{% include gallery images=images caption="" cols=1 %}

Ketik `pip install yuu -U` dan tunggu

{% capture images %}
	https://blog.n4o.xyz/blog/assets/img/abemadl/02.png
{% endcapture %}
{% include gallery images=images caption="" cols=1 %}

Jika error `requests` not found atau yang sebagainya, ketik ini terlebih dahulu: `pip install requests[socks] tqdm pycryptodome m3u8`

Baru `pip install yuu -U`

Setelah beres install yuu, silakan coba ketik `yuu -h` kira-kira muncul seperti ini

{% capture images %}
	https://blog.n4o.xyz/blog/assets/img/abemadl/03.png
{% endcapture %}
{% include gallery images=images caption="" cols=1 %}

Aktifkan VPN Jepang atau gunakan proxy IP/URL, beberapa yang free bisa ditemukan di sini: [spys](http://spys.one/free-proxy-list/JP/).

Disarankan memakai Proxy HTTPS (kalau pake proxy). Kalau menggunakan VPN, bisa langsung mulai

```bash
usage: yuu [-h] [--proxies PROXY]
           [--resolution {180p,240p,360p,480p,720p,1080p}] [--output OUTPUT]
           [--version] [--verbose]
           input

A simple AbemaTV video downloader

positional arguments:
  input                 AbemaTV url site or m3u8

optional arguments:
  -h, --help            show this help message and exit
  --proxies PROXY, -p PROXY
                        Use http(s)/socks5 proxies (please add `socks5://` if
                        you use socks5)
  --resolution {180p,240p,360p,480p,720p,1080p}, -r {180p,240p,360p,480p,720p,1080p}
                        Resolution (Default: 1080p)
  --output OUTPUT, -o OUTPUT
                        Output filename
  --version, -V         show program's version number and exit
  --verbose, -v         Enable verbose

Created by NoAiOne - Version 0.1.4.1
```

Command paling cepat adalah `yuu "url"` seperti `yuu https://abema.tv/video/episode/54-25_s1_p1` yaitu download Yagate Kimi ni Naru episode 1.
Kalau mau pake proxy tinggal tambahkan `yuu -p ip:port https://abema.tv/video/episode/54-25_s1_p1`, kalau pake VPN atau tinggal di Jepang gausah.

Kalau mau override output, tinggal tambahkan `-o output.ts`

Kalau mau ganti resolusi, gunakan `-r` seperti `-r 720p` (Resolusi yang tersedia: 180p, 240p, 360p, 480p, 720p, 1080p)

Jika error `requests.exceptions.ProxyError` coba ganti VPN/Proxynya, atau error lain seperti `IndexError`.

{% capture images %}
	https://blog.n4o.xyz/blog/assets/img/abemadl/04a.png
	https://blog.n4o.xyz/blog/assets/img/abemadl/04b.png
	https://blog.n4o.xyz/blog/assets/img/abemadl/04c.png
{% endcapture %}
{% include gallery images=images caption="Proses download, beres download, dan hasil download" cols=3 %}

File sudah bisa di mux ke .mkv menggunakan mkvtoolnix atau ffmpeg.

Kalau error saat mux, buka CMD dan arahkan ke folder sebelumya (atau Shift+Right Click foldernya)

Lalu ketik ini: `ffmpeg -i input.ts -map 0:0 -map 0:1 -c copy output-fix.ts`, `input.ts` diubah sesuai file yang ada dan `output-fix.ts` bebas namanya mau apa, setelah itu baru di mux.

{% capture images %}
	https://blog.n4o.xyz/blog/assets/img/abemadl/05a.png
	https://blog.n4o.xyz/blog/assets/img/abemadl/05b.png
	https://blog.n4o.xyz/blog/assets/img/abemadl/05c.png
{% endcapture %}
{% include gallery images=images caption="Command, output, dan hasil yang sudah bener" cols=3 %}

*Silakan di coba*

## Note:

Silakan lapor masalah (menggunakan bahasa inggris) melalui: [GitHub Issue](https://github.com/noaione/yuu/issues)

Dan kalau bisa PR ya :))

**Video yang jadi contoh di pos**: Yagate Kimi ni Naru Episode 01

**Video yang jadi contoh di gambar**: 1-Page no Koi Trailer