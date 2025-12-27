# Advance-Network-Security-And-Protocols

## Advanced Network Security – ARP & IP Spoofing Analysis

Repository ini berisi laporan dan dokumentasi praktikum mata kuliah **Advanced Network Security and Protocols** yang membahas berbagai teknik serangan jaringan, meliputi **ARP Spoofing, Sniffing, Session Hijacking, dan IP Spoofing**, beserta analisis dampak serta mekanisme penanggulangannya.

---

## KELOMPOK

- **Nur Aliyah Amaliani** – 105841106923  
- **Sukma Wardia Ningsih** – 105841112723  
- **Nur Qamariah Yunus** – 105841104323  

**Program Studi Informatika**  
Fakultas Teknik  
Universitas Muhammadiyah Makassar  
**Tahun 2025**

---

## Tujuan Praktikum

Praktikum ini bertujuan untuk:

- Memahami konsep dan mekanisme kerja serangan jaringan berbasis spoofing  
- Menganalisis kerentanan layanan jaringan terhadap **ARP Spoofing** dan **IP Spoofing**  
- Membandingkan tingkat keamanan layanan **Telnet** dan **SSH**  
- Mengamati dampak serangan terhadap trafik jaringan menggunakan tool monitoring  
- Mengetahui metode mitigasi serangan **ARP Spoofing** dan **IP Spoofing**

---

## Lingkup Praktikum

### 1. ARP Spoofing dan Session Hijacking

Pada bagian ini dilakukan beberapa tahapan berikut:

- Pembuatan topologi jaringan (**Client – Server – Attacker**)  
- Instalasi dan pengujian layanan **Telnet** dan **SSH**  
- Pencatatan **MAC Address** sebelum dan sesudah ARP Spoofing  
- Serangan **Man in The Middle (MITM)** menggunakan tool **hunt**  
- Observasi **Session Hijacking** pada:
  - **Telnet** (berhasil)
  - **SSH** (tidak berhasil karena enkripsi)
- Analisis koneksi menggunakan perintah `netstat -nat`

#### Hasil Utama
- ARP Spoofing berhasil memanipulasi tabel ARP pada client dan server  
- Session hijacking berhasil pada Telnet karena komunikasi tidak terenkripsi  
- Session hijacking gagal pada SSH karena menggunakan enkripsi dan autentikasi  

---

### 2. IP Spoofing

Percobaan IP Spoofing dilakukan menggunakan beberapa metode berikut:

#### a. Ping of Death (PoD) Spoofing
- Mengirim paket ICMP dengan alamat IP sumber palsu  
- Target membalas paket ke alamat IP palsu  

#### b. SYN Flood
- Mengirim paket TCP SYN secara berulang tanpa menyelesaikan handshake  
- Menguras resource pada sistem target  

#### c. LAND Attack
- Alamat IP sumber dan tujuan dibuat sama  
- Target mengirim paket ke dirinya sendiri secara terus-menerus  

#### d. Teardrop / Fragmentation Spoofing
- Manipulasi fragmentasi paket IP yang tidak normal  
- Berpotensi menyebabkan crash atau buffer overflow  

#### Hasil Utama
- IP Spoofing berhasil dilakukan pada berbagai metode  
- Target mengalami peningkatan beban trafik dan pemrosesan paket abnormal  

---

## Tools yang Digunakan

- **Wireshark** – Analisis paket jaringan  
- **Hunt** – ARP Spoofing dan Session Hijacking  
- **EtherApe** – Visualisasi trafik jaringan  
- **Netcat** – Simulasi backdoor  
- **Nmap** – Port scanning  
- **Telnet** dan **SSH** – Uji layanan client-server  

---

## Analisis Keamanan

### Perbandingan Telnet dan SSH

| Aspek | Telnet | SSH |
|------|--------|-----|
| Enkripsi | Tidak ada | Ada |
| Tingkat Keamanan | Rendah | Tinggi |
| Session Hijacking | Berhasil | Gagal |

### Transport Layer yang Digunakan

- **ICMP**  
  Digunakan pada serangan Ping of Death karena bersifat *connectionless* dan mudah dipalsukan.

- **TCP**  
  Digunakan pada SYN Flood dan LAND Attack karena dapat mengeksploitasi proses *three-way handshake*.

---

## Mitigasi Serangan

### Penanggulangan ARP Spoofing
- Static ARP  
- Dynamic ARP Inspection (DAI)  
- Penggunaan protokol terenkripsi seperti **SSH**  

### Penanggulangan IP Spoofing
- Ingress dan Egress Filtering  
- Firewall  
- IDS/IPS  
- TCP SYN Cookies  

---

## Dokumentasi dan Laporan

- 📄 **Laporan Praktikum (PDF)**  
  👉 [Lihat Laporan](ANALISIS_ARP_SPOOFING_TUGAS_ADVANCE_NETWORK_SECURITY_AND_PROTOCOLS.pdf)

- 📸 **Dokumentasi Gambar Praktikum**  
  👉 [Lihat Dokumentasi](Gambar_Dokumentasi)

> Pastikan file laporan dan folder dokumentasi sudah di-push ke repository agar link dapat diakses dengan benar.

---

## Struktur Repository
├── laporan/
│ └── ANALISIS_ARP_IP_SPOOFING.pdf
├── screenshots/
│ ├── arp_spoofing/
│ ├── ip_spoofing/
│ └── etherape/
└── README.md


---

## Kesimpulan
Praktikum ini membuktikan bahwa jaringan yang tidak dilengkapi mekanisme keamanan yang memadai sangat rentan terhadap serangan spoofing. **ARP Spoofing** dan **IP Spoofing** dapat digunakan untuk melakukan penyadapan, session hijacking, hingga *denial of service*. Oleh karena itu, penggunaan protokol aman, filtering paket, serta sistem deteksi intrusi merupakan langkah penting dalam menjaga keamanan jaringan.

