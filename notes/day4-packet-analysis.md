# Day 4: Packet Analysis Fundamentals

## Konsep Dasar
**Packet Analysis** (atau Packet Sniffing) adalah proses mencegat, menangkap, dan menganalisis lalu lintas data (*traffic*) yang melintasi jaringan. Setiap data yang dikirim melalui jaringan (seperti membuka web, mengirim email, atau Ping) dipecah menjadi bagian-bagian kecil yang disebut paket.

Seorang Security Analyst menggunakan teknik ini untuk:
- Memeriksa apakah ada data sensitif yang dikirim dalam bentuk *plaintext* (tidak terenkripsi).
- Mendeteksi anomali atau serangan jaringan.
- Melakukan *troubleshooting* konektivitas.

## PCAP (Packet Capture)
PCAP adalah ekstensi file standar industri yang digunakan untuk menyimpan rekaman lalu lintas jaringan. File `.pcap` ini berisi raw data yang nantinya dapat dianalisis secara visual menggunakan alat bantu seperti Wireshark.

## tcpdump vs Wireshark
- **tcpdump**: Berbasis *Command Line Interface* (CLI). Ringan, cepat, dan menjadi standar wajib karena sebagian besar server *production* berbasis Linux *headless* (tanpa GUI).
- **Wireshark**: Berbasis *Graphical User Interface* (GUI). Sangat baik untuk analisis mendalam dengan fitur visualisasi dan *filtering* yang komprehensif, tetapi tidak bisa dijalankan di server *headless*.

## Cheat Sheet tcpdump Dasar
- `sudo`: Wajib digunakan karena membaca *traffic* memerlukan hak akses *root* (*Promiscuous Mode*).
- `-i [interface]`: Menentukan *Network Interface* yang ingin dipantau (contoh: `eth0`).
- `-c [angka]`: Membatasi jumlah paket yang ditangkap (contoh: `-c 5`).
- `-w [nama_file.pcap]`: Menyimpan hasil tangkapan ke dalam file.
- `-n`: Mencegah *reverse DNS lookup* (tidak mengubah IP menjadi *hostname*), sangat berguna untuk mempercepat proses *sniffing* dan mengurangi beban server.
