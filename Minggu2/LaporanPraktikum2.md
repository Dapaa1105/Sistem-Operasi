# Laporan Praktikum Sistem Operasi 2

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## Praktikum 2.1 - Identifikasi CPU dan Memori

Kode 1.1 : Melihat informasi CPU

![Minggu2/Image/kode1.1.png](Image/kode1.1.png)

Kode 1.2 : Melihat penggunaan memori

![Minggu2/Image/kode1.2.png](Image/kode1.2.png)

Kode 1.3 : Informasi DMI

![Minggu2/Image/kode1.3.png](Image/kode1.3.png)

#### Latihan 2.1

Catat: (1) jumlah CPU(s), core/thread, (2) total RAM, (3) total swap. Jelaskan perbedaan RAM vs swap dalam 2–3 kalimat.

>Jawaban :
>1. Jumlah CPU(s) : 6
>2. Jumlah Core(s) per socket : 4
>3. Jumlah Thread(s) per core : 1  
>4. Total RAM : 3.7Gi  
>5. Total Swap : 0B  

>Perbedaan RAM vs swap adalah RAM yaitu memori fisik cepat yang digunakan untuk menyimpan data dan program yang sedang aktif sedangkan swap adalah ruang di harddisk yang digunakan sebagai "RAM cadangan" ketika RAM fisik penuh. Swap lebih lambat dari RAM, sehingga penggunaan swap berlebihan dapat memperlambat sistem

## Praktikum 2.2 - Identifikasi Perangkat PCI/USB dan Driver

Kode 1.4 : Daftar perangkat PCI (ringkas)

![Minggu2/Image/kode1.4.png](Image/kode1.4.png)

Kode 1.5: Melihat driver perangkat PCI

![Minggu2/Image/kode1.5.png](Image/kode1.5.png)

Kode 1.6: Mencari info NIC dan drivernya

![Minggu2/Image/kode1.6.png](Image/kode1.6.png)

Kode 1.7: Daftar perangkat USB

![alt text](Image/kode1.7.png)

Kode 1.8: Topologi perangkat USB

![Minggu2/Image/kode1.8.png](Image/kode1.8.png)

#### Latihan 2.2

Temukan 1 perangkat PCI (misal NIC) dan tuliskan: Vendor:Device ID (angka
heksadesimal), nama driver/modul kernel, dan deskripsi singkat fungsinya. 

>Jawaban :  
>1. Perangkat --> Network Interface Controller (NIC)
>2. Vendor:Device ID -->  8086:001e  
>3. Nama driver/modul -->	e1000  
>4. Deskripsi fungsi --> MPerangkat ini adalah kartu jaringan berbasis Intel PRO/1000 yang berfungsi untuk menghubungkan sistem ke jaringan (LAN). Driver e1000 memungkinkan sistem operasi Linux mengenali dan mengelola komunikasi data melalui perangkat tersebut sehingga server dapat mengirim dan menerima paket data melalui jaringan.


## Praktikum 2.3 — Identifikasi Storage dan Filesystem

Kode 1.9: Melihat block device dan filesystem

![Minggu1/Image/kode1.9.png](Image/kode1.9.png)

Kode 1.10: Melihat UUID filesystem

![Minggu1/Image/kode1.10.png](Image/kode1.10.png)

Kode 1.11: Melihat device untuk root filesystem

![Minggu1/Image/kode1.11.png](Image/kode1.11.png)

## Praktikum 2.4 — Melihat Modul Aktif dan Informasinya

Kode 1.13: Cek versi kernel

![alt text](Image/kode1.13.png)

Kode 1.14: Daftar modul aktif

![alt text](Image/kode1.14.png)

Kode 1.15: Detail modul dengan modinfo

![alt text](Image/kode1.15.png)

Kode 1.16: Load modul dan verifikasi

![alt text](Image/kode1.16.png)

Kode 1.17: Cek log kernel terbaru

![alt text](Image/kode1.17.png)


## Praktikum 2.5 — Konfigurasi Auto-load dan Blacklist

Kode 1.18: Menambahkan modul untuk auto-load (demo)

![alt text](Image/kode1.18.png)

Kode 1.19: Verifikasi modul aktif

![alt text](Image/kode1.19.png)

Kode 1.20: Contoh blacklist modul (jangan diterapkan sembarangan)

![alt text](Image/kode1.20.png)


## Praktikum 2.6 — Mengenali Block vs Character Device

Kode 1.21: Melihat detail device node disk

![alt text](Image/kode1.21.png)

Kode 1.22: Melihat detail device node terminal

![alt text](Image/kode1.22.png)

Kode 1.23: Mapping disk/partisi

![alt text](Image/kode1.23.png)

#### Latihan 2.3

Dari output ls -l, jelaskan perbedaan penanda file untuk block device dan
character device. (Hint: karakter pertama pada permission string)

>Jawaban :  
Dari output ls -l, perbedaannya terletak pada karakter pertama dari string permission  
>1. Block device → karakter pertama b  
Contoh: /dev/sda  
Fungsi: akses data per blok (hardisk, SSD)  
>2. Character device → karakter pertama c  
Contoh: /dev/tty  
Fungsi: akses data per karakter (terminal, keyboard)


## Praktikum 2.7 — Melihat Informasi udev

Kode 1.24: Melihat atribut udev untuk disk

![alt text](Image/kode1.24.png)

Kode 1.25: Monitor event udev (opsional)

![alt text](Image/kode1.25.png)


## Praktikum 2.8 — Membuat Workspace Praktikum

Kode 1.26: Membuat workspace praktikum

![alt text](Image/kode1.26.png)

Kode 1.27: Membuat file contoh

![alt text](Image/kode1.27.png)

Kode 1.28: Mengisi file log contoh

![alt text](Image/kode1.28.png)

Kode 1.29: Membaca file dengan less

![alt text](Image/kode1.29.png)


## Praktikum 2.9 — Pencarian Pola dengan grep

Kode 1.30: grep sederhana

![alt text](Image/kode1.30.png)

Kode 1.31: grep case-insensitive

![alt text](Image/kode1.31.png)

Kode 1.32: grep dengan nomor baris

![alt text](Image/kode1.32.png)

Kode 1.33: grep invert match

![alt text](Image/kode1.33.png)

### Latihan 2.4

Gunakan grep untuk menampilkan hanya baris yang mengandung INFO atau WARN dari data.log. (Hint: gunakan grep -E dengan pola alternatif)

>Jawaban : 
![alt text](Image/kode1.33(latihan2.4).png)


## Praktikum 2.10 — Substitusi dengan sed (Aman di File Latihan)

Kode 1.34: Membuat file config latihan

![alt text](Image/kode1.34.png)

Kode 1.35: sed substitusi tanpa in-place

![alt text](Image/kode1.35.png)

Kode 1.36: sed in-place

![alt text](Image/kode1.36.png)

Kode 1.37: sed global replacement

![alt text](Image/kode1.37.png)


## Praktikum 2.11 — Ekstraksi Kolom dengan awk

Kode 1.38: Output df -h

![alt text](Image/kode1.38.png)

Kode 1.39: awk print kolom tertentu

![alt text](Image/kode1.39.png)

Kode 1.40: awk filter berdasarkan kondisi

![alt text](Image/kode1.40.png)


## Praktikum 2.12 — Melihat Proses dengan ps

Kode 1.41: ps aux

![alt text](Image/kode1.41.png)

Kode 1.42: Filter proses dengan grep

![alt text](Image/kode1.42.png)


## Praktikum 2.13 — Monitoring Real-time dengan top

Kode 1.43: Menjalankan top

![alt text](Image/kode1.43.png)


## Praktikum 2.14 — Menghentikan Proses dengan kill

Kode 1.44: Membuat proses dummy

![alt text](Image/kode1.44.png)

Kode 1.45: Mencari PID sleep

![alt text](Image/kode1.45.png)

Kode 1.46: Mengirim SIGTERM

![alt text](Image/kode1.46.png)

Kode 1.47: Verifikasi proses sudah berhenti

![alt text](Image/kode1.47.png)

Kode 1.48: Mengirim SIGKILL (opsional)

![alt text](Image/kode1.48.png)


## Praktikum 2.15 — Cek Disk, Load, dan Service

Kode 1.49: Cek kapasitas disk

![alt text](Image/kode1.49.png)

Kode 1.50: Cek ukuran direktori (contoh /var)

![alt text](Image/kode1.50.png)

Kode 1.51: Cek load average

![alt text](Image/kode1.51.png)

Kode 1.52: Service yang gagal

![alt text](Image/kode1.52.png)

Kode 1.53: Log error terbaru

![alt text](Image/kode1.53.png)


## Praktikum 2.16 — Monitoring Port dan Koneksi (Network Basics)

Kode 1.54: Cek IP address

![alt text](Image/kode1.54.png)

Kode 1.55: Cek routing

![alt text](Image/kode1.55.png)

Kode 1.56: Cek port listening

![alt text](Image/kode1.56.png)

### Latihan 2.5

Pilih satu port yang listening dari output ss -tulpn(misal port 22), lalu tuliskan service/proses yang membukanya. Jelaskan kegunaan port tersebut secara singkat.

>Jawaban :  
Port 53  
Port 53 digunakan untuk layanan DNS (Domain Name System). Service systemd-resolve berfungsi menangani resolusi nama domain menjadi alamat IP. Artinya, ketika server melakukan permintaan seperti mengakses google.com, service ini yang menerjemahkan nama domain tersebut menjadi alamat IP agar bisa terhubung ke server tujuan.

# Latihan

## Latihan 2.A
Jalankan lspci -nnk. Pilih 1 perangkat PCI dan tuliskan: nama perangkat, ID vendor:device, dan kernel driver in use.
>Jawaban :  
Nama Perangkat: Intel Corporation 82540EM Gigabit Ethernet Controller
Vendor:Device ID: 8086:100e
Kernel Driver in Use: e1000

## Latihan 2.B
Tentukan device root filesystem dengan findmnt /. Lalu cocokkan dengan lsblk -f dan tuliskan tipe filesystem serta UUID-nya.
>Jawaban :  
Device root filesystem: /dev/sda2
Tipe file
UUID: 3fd833a5-8c55-4efb-9863-08b9980471c8

## Latihan 2.C
Buat file server.log berisi minimal 10 baris dengan variasi kata: INFO, WARN, ERROR. Gunakan grep untuk menampilkan hanya baris ERROR.
>Jawaban :  
![alt text](Image/kodelatihan2c.png)

## Latihan 2.D
Gunakan sed untuk mengganti semua kata server menjadi node pada file latihan. Tunjukkan sebelum dan sesudah.
>Jawaban :  
![alt text](Image/kodelatihan2d.png)

## Latihan 2.E
Gunakan df -h lalu awk untuk menampilkan filesystem yang penggunaan disk di atas 70%.
>Jawaban :   
![alt text](Image/kodelatihan2e.png) 


## Latihan 2.F
Jalankan sleep 600 &. Temukan PID-nya dengan ps. Hentikan dengan SIGTERM. Jelaskan beda SIGTERM vs SIGKILL.
>Jawaban :  
![alt text](Image/kodelatihan2f.png)  
>SIGTERM adalah signal untuk menghentikan proses secara normal dan memberi kesempatan proses untuk melakukan cleanup sebelum berhenti. Sedangkan SIGKILL adalah signal untuk menghentikan proses secara paksa tanpa memberi kesempatan cleanup dan tidak bisa ditolak oleh proses. SIGTERM lebih aman digunakan, sedangkan SIGKILL digunakan jika proses tidak merespon SIGTERM.

## Latihan 2.G
Gunakan systemctl –failed. Jika tidak ada yang gagal, pilih satu service aktif (misal ssh) dan tampilkan status serta 30 baris log terakhirnya.
>Jawaban :  
ssh  
![alt text](Image/kodelatihan2g(ssh).png)
