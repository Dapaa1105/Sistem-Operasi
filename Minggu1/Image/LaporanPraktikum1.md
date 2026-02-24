# Laporan Praktikum 1

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## 1.10 LATIHAN

### 1.10.1 Latihan Konseptual

#### Latihan 1.1

Jelaskan 5 fungsi utama sistem operasi dengan contoh konkret dari minimal 2
OS berbeda (Windows, macOS, atau Linux).

>Jawaban :  
Sistem operasi modern memiliki lima fungsi utama:
>1. Manajemen Proses (Process Management)
<b>Fungsi:</b>  
• Mengatur jalannya program yang sedang aktif (proses), termasuk menjalankan, menghentikan, dan membagi waktu CPU supaya semua aplikasi bisa berjalan dengan lancar.  
<b>Contoh implementasi :</b>  
• Windows: Membuka Task Manager (Ctrl + Shift + Esc) untuk melihat aplikasi yang sedang berjalan dan mengakhiri proses yang “Not Responding”.
• Linux: Bisa memakai perintah top atau htop di Terminal untuk melihat proses yang aktif dan menghentikannya dengan kill.
>
>2. Manajemen Memori (Memory Management)   
<b>Fungsi: </b>  
• Mengatur jalannya program yang sedang aktif (proses), termasuk menjalankan, menghentikan, dan membagi waktu CPU supaya semua aplikasi bisa berjalan dengan lancar.
<b>Contoh :</b>  
• macOS: Bisa  membuka activity Monitor → Memory untuk melihat penggunaan RAM dan memory pressure.
• Windows: Di Task Manager bagian Performance → Memory, bisa melihat berapa RAM yang sedang dipakai.
>
>3. Manajemen File (File Management)   
<b>Fungsi:</b>  
• Mengatur penyimpanan data seperti membuat, membaca, menghapus, dan mengelola folder/file.
<b>Contoh:</b>  
• Windows: Menggunakan File Explorer untuk mengatur folder dan file.  
• macOS: Menggunakan Finder untuk mengelola file. 
• Linux: Bisa pakai File Manager atau perintah terminal seperti ls, mkdir, rm.
>
>4. Manajemen Perangkat Keras (Device Management)
<b>Fungsi:</b>  
• Mengatur komunikasi antara hardware (keyboard, mouse, printer, dll) dengan software melalui driver.  
<b>Contoh:</b>  
• Windows: Ada Device Manager untuk melihat dan mengatur driver perangkat.
• Ubuntu: Banyak driver otomatis terpasang, dan bisa dicek lewat perintah seperti lsusb atau lspci.
>5. Manajemen Keamanan (Security Management)
<b>Fungsi:</b>  
• Melindungi sistem dari akses tidak sah dan malware, serta mengatur hak akses pengguna.
<b>Contoh: </b>   
• Windows: Ada Windows Defender dan sistem login dengan password atau PIN.
• Linux: Ada sistem permission (rwx) dan penggunaan sudo untuk akses administrator.
• macOS: Ada fitur Gatekeeper dan proteksi aplikasi dari sumber tak dikenal.


#### Latihan 1.2

Kapan sebaiknya menggunakan Windows vs Linux vs macOS?  
Analisis berdasarkan use case: gaming, development, server, creative work, dan enterprise.

>Jawaban :  
>1. Gaming
Untuk kebutuhan gaming, Microsoft Windows adalah pilihan paling ideal karena mayoritas game AAA dikembangkan dan dioptimalkan pertama kali untuk Windows. Dukungan driver kartu grafis dari NVIDIA dan AMD juga paling stabil di platform ini, sehingga performa dan kompatibilitas lebih terjamin. Platform distribusi seperti Steam dan Epic Games Store juga berjalan paling optimal di Windows. Linux sebenarnya sudah berkembang dengan teknologi seperti Proton, namun belum semua game kompatibel sempurna, sedangkan macOS memiliki keterbatasan besar dalam ketersediaan game.
>
>2. Software Development
Dalam pengembangan perangkat lunak, Linux seperti Ubuntu sangat cocok terutama untuk web development, backend, dan DevOps karena banyak server produksi menggunakan Linux sehingga lingkungan pengembangannya konsisten. Sistem berbasis Unix memudahkan penggunaan tools seperti Git, Docker, dan berbagai bahasa pemrograman. Sementara itu, macOS juga populer di kalangan developer karena stabil dan berbasis Unix, serta menjadi satu-satunya sistem resmi untuk pengembangan aplikasi iOS. Windows tetap relevan, terutama untuk pengembangan aplikasi berbasis .NET dan kebutuhan enterprise, apalagi dengan adanya WSL yang memungkinkan lingkungan Linux berjalan di dalam Windows.
>
>3. Creative Work 
Dalam bidang kreatif seperti desain grafis, video editing, dan produksi musik, macOS sering menjadi pilihan utama karena stabilitas sistem dan optimalisasi antara hardware dan software yang sangat baik. Banyak profesional kreatif menggunakan aplikasi eksklusif seperti Final Cut Pro dan Logic Pro yang hanya tersedia di macOS. Namun, Windows juga sangat kuat untuk pekerjaan kreatif, terutama dengan hardware high-end dan dukungan software seperti Adobe Creative Cloud dan aplikasi 3D rendering. Linux kurang umum digunakan di bidang ini karena banyak software kreatif populer tidak tersedia secara native.
>
>4.Enterprise
Untuk lingkungan enterprise atau perkantoran skala besar, Microsoft Windows paling banyak digunakan karena integrasinya dengan Active Directory, Microsoft Office, serta kemudahan manajemen jaringan dan perangkat dalam skala organisasi. Windows mendukung berbagai aplikasi bisnis yang menjadi standar perusahaan. Linux lebih sering digunakan di sisi server enterprise daripada desktop pengguna, sedangkan macOS biasanya dipakai di perusahaan kreatif, startup teknologi, atau lingkungan kerja yang membutuhkan integrasi dengan ekosistem Apple.
>
>5. Server   
Untuk kebutuhan server dan infrastruktur, Linux merupakan standar industri karena stabil, ringan, aman, dan tidak memerlukan biaya lisensi mahal. Distribusi seperti Ubuntu Server banyak digunakan untuk web server, database server, dan cloud infrastructure. Fleksibilitas serta kemudahan konfigurasi membuat Linux unggul dalam skala kecil hingga data center besar. Windows Server biasanya digunakan di lingkungan enterprise yang bergantung pada Active Directory dan ekosistem Microsoft, sedangkan macOS hampir tidak pernah digunakan sebagai server produksi utama.

### 1.10.2 Latihan Praktikal

#### Latihan 1.3

Install Ubuntu Server 22.04 LTS di VirtualBox dengan langkah berikut:
1. Download Ubuntu Server ISO dari website resmi
2. Create VM baru di VirtualBox (RAM: 2GB, Disk: 25GB)
3. Install dengan automatic partitioning (guided)
4. Buat user account dengan password yang kuat
5. Reboot dan login ke sistem
6. Dokumentasikan proses instalasi dengan screenshot key step

>Jawaban :  
>1. Step 1  
![alt text](Image/VB1.png)
>2. Step 2  
![alt text](Image/VB2.png)
>3. Step 3  
![alt text](Image/VB3.png)
>4. Step 4  
![alt text](Image/VB4.png)
>5. Step 5  
![alt text](Image/VB5.png)
>6. Step 6  
![alt text](Image/VB6.png)
>7. Step 7  
![alt text](Iage/VB7.png)
>8. Step 8   
![alt text](Image/VB8.png)
>9. Step 9   
![alt text](Image/Ubuntu1.png)
>10. Step 10   
![alt text](Image/Ubuntu2.png)
>11. Step 11   
![alt text](Image/Ubuntu3.png)
>12. Step 12   
![alt text](Image/Ubuntu4.png)
>13. Step 13  
![alt text](Image/Ubuntu5.png)
>14. Step 14  
![alt text](Image/Ubuntu6.png)
>15. Step 15  
![alt text](Image/Ubuntu7.png)
>16. Step 16  
![alt text](Image/Ubuntu8.png)

#### Latihan 1.4

Setelah instalasi Ubuntu Server, lakukan tasks berikut:
1. Update package list: sudo apt update
2. Upgrade packages: sudo apt upgrade
3. Install neofetch: sudo apt install neofetch
4. Jalankan neofetch dan screenshot hasilnya
5. Check disk usage dengan df -h
6. Check memory dengan free -h
7. Dokumentasikan output dari setiap command

>Jawaban :  
>1. Step 1  
![alt text](Image/Update1.png)
>2. Step 2  
![alt text](Image/Update2.png)
>3. Step 3  
![alt text](Image/Update3.png)
>4. Step 4  
![alt text](Image/Update4.png)
>5. Step 5  
![alt text](Image/Update5.png)
>6. Step 6   
![alt text](Image/Update6.png)
>7. Step 7  
![alt text](Image/Update7.png)

#### Latihan 1.5

Eksplorasi sistem yang baru diinstall:
1. Tampilkan informasi OS: cat /etc/os-release
2. Tampilkan versi kernel: uname -r
3. List partisi: lsblk
4. Check network connectivity: ping -c 4 google.com
5. Install dan jalankan htop untuk melihat resource usage
6. Buat laporan singkat tentang konfigurasi sistem Anda

>Jawaban :   
>
><b>LAPORAN KONFIGURASI SISTEM UBUNTU SERVER</b>
>
>Hostname: VirtualBox 1.2
>
><b>A. SPESIFIKASI SISTEM</b>  
>Sistem Operasi: Ubuntu 24.04.4 LTS x86_64
>
>Kernel Linux: 6.8.0-101-generic
>
>Arsitektur: 64-bit (x86_64)
>
>Uptime: 1 min
>
><b>B. KONFIGURASI HARDWARE</b>  
>Processor: 13th Gen Intel i5-13450HX, jumlah core : 4
>
>RAM Total: 3.7 GB
>
>Penggunaan RAM saat ini: 11.5%
>
>Disk Total: 24.4G
>
>Penggunaan Disk: 5% dari partisi root (/)
>
>Partisi: Konfigurasi LVM dengan partisi terpisah untuk /boot
>
><b>C. KONEKTIVITAS JARINGAN</b>  
>Interface jaringan: enp0s3
>
>Alamat IP: 10.0.2.15
>
><b>D. LAYANAN DAN PROSES</b>  
>Jumlah proses berjalan: 142 proses
>
>Proses dengan penggunaan CPU tertinggi: kworker/1:1-events
>
>Proses dengan penggunaan memori tertinggi: sbin/multipathd -d -s
>
>Package manager: APT dengan repository Ubuntu 24.04
>
><b>E. APLIKASI TERINSTAL</b>  
>Neofetch: Untuk menampilkan informasi sistem
>
>htop: Monitor proses interaktif
>
>Lainnya: Paket dasar Ubuntu Server
>
><b>F. KESIMPULAN</b>  
>Instalasi Ubuntu Server telah selesai dan sistem berjalan secara normal tanpa kendala. Seluruh perangkat keras berhasil dikenali dengan baik, koneksi jaringan aktif dan stabil, serta penggunaan sumber daya masih sangat memadai untuk operasional server dasar. Dengan kondisi ini, sistem sudah layak dan siap dimanfaatkan untuk berbagai kebutuhan seperti web server, database server, maupun pengembangan aplikasi.
