# Advance-Network-Security-And-Protocols
Advanced Network Security – ARP & IP Spoofing Analysis

Repository ini berisi laporan dan dokumentasi praktikum mata kuliah Advanced Network Security and Protocols yang membahas berbagai teknik serangan jaringan, meliputi ARP Spoofing, Sniffing, Session Hijacking, dan IP Spoofing, beserta analisis dampak dan mekanisme penanggulangannya.

👩‍🎓 Penyusun

Nur Aliyah Amaliani – 105841106923

Sukma Wardia Ningsih – 105841112723

Nur Qamariah Yunus – 105841104323

Program Studi Informatika
Fakultas Teknik
Universitas Muhammadiyah Makassar
Tahun 2025

📌 Tujuan Praktikum

Praktikum ini bertujuan untuk:

Memahami konsep dan mekanisme kerja serangan jaringan berbasis spoofing

Menganalisis kerentanan layanan jaringan terhadap ARP dan IP Spoofing

Membandingkan layanan Telnet dan SSH dari sisi keamanan

Mengamati dampak serangan terhadap trafik jaringan menggunakan tool monitoring

Mengetahui metode mitigasi serangan ARP Spoofing dan IP Spoofing

🧪 Lingkup Praktikum
1. ARP Spoofing & Session Hijacking

Pada bagian ini dilakukan:

Pembuatan topologi jaringan (Client – Server – Attacker)

Instalasi dan pengujian layanan Telnet dan SSH

Pencatatan MAC Address sebelum dan sesudah ARP Spoofing

Serangan Man in The Middle (MITM) menggunakan tool hunt

Observasi Session Hijacking pada:

Telnet (berhasil)

SSH (tidak berhasil karena enkripsi)

Analisis koneksi menggunakan netstat -nat

📌 Hasil utama:

ARP Spoofing berhasil memanipulasi tabel ARP client dan server

Session hijacking berhasil pada Telnet karena komunikasi tidak terenkripsi

Session hijacking gagal pada SSH karena penggunaan enkripsi dan autentikasi

2. IP Spoofing

Percobaan IP Spoofing dilakukan menggunakan beberapa metode berikut:

a. Ping of Death (PoD) Spoofing

Mengirim paket ICMP dengan IP sumber palsu

Target membalas ke alamat IP palsu

b. SYN Flood

Mengirim paket TCP SYN berulang tanpa menyelesaikan handshake

Menguras resource target

c. LAND Attack

IP sumber dan tujuan dibuat sama

Target mengirim paket ke dirinya sendiri secara terus-menerus

d. Teardrop / Fragmentation Spoofing

Manipulasi fragmentasi paket IP

Berpotensi menyebabkan crash atau buffer overflow

📌 Hasil utama:

IP Spoofing berhasil dilakukan pada berbagai metode

Target mengalami peningkatan beban trafik dan pemrosesan paket abnormal

🔍 Tools yang Digunakan

Wireshark – Analisis paket jaringan

Hunt – ARP Spoofing & Session Hijacking

EtherApe – Visualisasi trafik jaringan

Netcat – Simulasi backdoor

Nmap – Port scanning

Telnet & SSH – Uji layanan client-server

🛡️ Analisis Keamanan
Perbandingan Telnet vs SSH
Aspek	Telnet	SSH
Enkripsi	Tidak ada	Ada
Keamanan	Rendah	Tinggi
Session Hijacking	Berhasil	Gagal
Transport Layer yang Digunakan

ICMP: Digunakan pada PoD karena bersifat connectionless dan mudah dipalsukan

TCP: Digunakan pada SYN Flood dan LAND Attack karena dapat mengeksploitasi proses handshake

🔐 Mitigasi Serangan
Penanggulangan ARP Spoofing

Static ARP

Dynamic ARP Inspection (DAI)

Penggunaan protokol terenkripsi (SSH)

Penanggulangan IP Spoofing

Ingress & Egress Filtering

Firewall

IDS/IPS

TCP SYN Cookies

📂 Struktur Repository (Contoh)
.
├── laporan/
│   └── ANALISIS_ARP_IP_SPOOFING.pdf
├── screenshots/
│   ├── arp_spoofing/
│   ├── ip_spoofing/
│   └── etherape/
└── README.md

📄 Kesimpulan

Praktikum ini membuktikan bahwa jaringan tanpa mekanisme keamanan yang memadai sangat rentan terhadap serangan spoofing. ARP Spoofing dan IP Spoofing dapat digunakan untuk melakukan penyadapan, hijacking, hingga denial of service. Penggunaan protokol aman, filtering paket, dan sistem deteksi intrusi menjadi langkah penting dalam menjaga keamanan jaringan.
