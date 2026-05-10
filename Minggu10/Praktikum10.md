# Laporan Praktikum 10

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## PRAKTIKUM

## Praktikum 10.1

### Langkah 1
Input
```bash
free -h
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       408Mi       3.3Gi       1.0Mi       278Mi       3.3Gi
Swap:             0B          0B          0B
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 2
Input
```bash
cat /proc/meminfo | head -n 20
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ cat /proc/meminfo | head -n 20
MemTotal:        3910968 kB
MemFree:         3427188 kB
MemAvailable:    3492456 kB
Buffers:           18316 kB
Cached:           250308 kB
SwapCached:            0 kB
Active:           253592 kB
Inactive:          48344 kB
Active(anon):      43120 kB
Inactive(anon):        0 kB
Active(file):     210472 kB
Inactive(file):    48344 kB
Unevictable:       27316 kB
Mlocked:           27316 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Zswap:                 0 kB
Zswapped:              0 kB
Dirty:                68 kB
Writeback:             0 kB
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Hitung persentase memori tersedia: available / total × 100%. Jika hasilnya di bawah 10%, sistem mulai kekurangan memori.
2. Pada baris Swap, apakah kolom used bernilai 0? Jika lebih dari 0, kernel sudah pernah memindahkan data ke disk karena RAM tidak cukup.
3. Perhatikan field Cached dan Buffers di /proc/meminfo. Nilai ini sesuai
dengan kolom buff/cache pada free -h.

Jawaban :  
1. Persentase Memori Tersedia: Available/Total * 100% = $$ 3.492.456/3.910.968 * 100% = 89,3
2. Nilai Used: 0. Namun, perlu dicatat bahwa SwapTotal juga 0 kB. Artinya, sistem tidak memiliki area Swap. Jika RAM penuh, sistem tidak bisa memindahkan data ke disk dan berisiko mematikan proses secara paksa (OOM Killer).
3. Ya, sesuai. Nilai Buffers (18 MB) dan Cached (250 MB) jika dijumlahkan akan membentuk kolom buff/cache pada perintah free -h. Ini adalah memori yang digunakan untuk mengoptimalkan sistem namun bisa diambil kembali kapan saja oleh aplikasi.


## Praktikum 10.2

### Langkah 1
Input
```bash
vmstat 1 5
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ vmstat 1 5
procs -----------memory---------- ---swap-- -----io---- -system-- -------cpu-------
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st gu
 1  0      0 3372312  19016 305232    0    0   643    85 1356    0  0  5 94  0  0  0
 0  0      0 3372312  19016 305232    0    0     0     0 1292  150  0  5 95  0  0  0
 0  0      0 3372312  19016 305324    0    0     0     0 1219  163  0  5 95  0  0  0
 0  0      0 3372312  19016 305324    0    0     0     0 1198  111  0  6 94  0  0  0
 0  0      0 3372312  19016 305324    0    0     0     0 1189   78  0  6 94  0  0  0
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Amati nilai si dan so pada kelima baris. Pada sistem normal dengan RAM cukup, kedua nilai ini selalu 0.
2. Jika nilai si atau so sesekali muncul lebih dari 0, artinya pernah ada aktivitas swap. Ini masih wajar jika tidak terus-menerus.
3. Jika si dan so terus-menerus lebih dari 0, sistem dalam kondisi memory pressure serius — performa turun drastis karena akses disk jauh lebih lambat dari RAM.
4. Perhatikan juga kolom free (RAM kosong) dan buff (buffer) untuk memahami kondisi keseluruhan RAM saat itu.

Jawaban :   
1. Kondisi: Keduanya bernilai 0 di semua baris. Ini mengonfirmasi bahwa sistem berjalan normal dengan RAM yang sangat mencukupi, sehingga tidak ada data yang perlu ditukar (swapping) ke disk.
2. Karena nilai tetap 0, sistem saat ini tidak mengalami aktivitas swap sama sekali. Jika nantinya muncul angka kecil sesekali, itu biasanya hanya kernel yang memindahkan data pasif untuk mengoptimalkan RAM. 
3. Sistem tidak mengalami memory pressure. Karena si (swap-in) dan so (swap-out) konsisten di angka 0, performa sistem tetap terjaga karena seluruh operasional data masih ditangani langsung oleh RAM tanpa hambatan akses disk.
4. Free: Berada di angka ~3,3 GB. Ini menunjukkan sisa RAM yang benar-benar kosong masih sangat besar. Buff: Stabil di angka ~19 MB. Ini adalah porsi kecil RAM yang digunakan untuk temporary storage blok disk mentah (raw disk blocks).

## Praktikum 10.3

### Langkah 1
Input
```bash
sudo fallocate -l 512M /swapfile-Minggu10
ls -lh /swapfile-Minggu10
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ sudo fallocate -l 512M /swapfile-Minggu10
[sudo] password for dafanr11:
dafanr11@Ubuntu-Server-New:~$ ls -lh /swapfile-Minggu10
-rw-r--r-- 1 root root 512M May 10 05:54 /swapfile-Minggu10
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 2
Input
```bash
sudo chmod 600 /swapfile-Minggu10
ls -lh /swapfile-Minggu10
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ sudo chmod 600 /swapfile-Minggu10
dafanr11@Ubuntu-Server-New:~$ ls -lh /swapfile-Minggu10
-rw------- 1 root root 512M May 10 05:54 /swapfile-Minggu10
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 3
Input
```bash
sudo mkswap /swapfile-Minggu10
sudo swapon /swapfile-Minggu10
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ sudo mkswap /swapfile-Minggu10
Setting up swapspace version 1, size = 512 MiB (536866816 bytes)
no label, UUID=36ef312a-3591-4c53-bb6f-1dc9a135f4bb
dafanr11@Ubuntu-Server-New:~$ sudo swapon /swapfile-Minggu10
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 4
Input
```bash
swapon --show
free -h
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ swapon --show
NAME               TYPE SIZE USED PRIO
/swapfile-Minggu10 file 512M   0B   -2
dafanr11@Ubuntu-Server-New:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       423Mi       3.2Gi       1.0Mi       319Mi       3.3Gi
Swap:          511Mi          0B       511Mi
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 5
Input
```bash
cat /proc/sys/vm/swappiness
sudo sysctl vm.swappiness=10
cat /proc/sys/vm/swappiness
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ cat /proc/sys/vm/swappiness
60
dafanr11@Ubuntu-Server-New:~$ sudo sysctl vm.swappiness=10
vm.swappiness = 10
dafanr11@Ubuntu-Server-New:~$ cat /proc/sys/vm/swappiness
10
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Berapa nilai swappiness default? Apa artinya bagi perilaku kernel dalam menggunakan swap?
2. Setelah diubah ke 10, konfirmasi nilai berubah pada output cat kedua. Apa dampak nilai 10 terhadap penggunaan swap dibanding nilai 60?
3. Apakah entri /swapfile-week10 muncul di swapon –show? Jika tidak, pastikan Langkah 2 (chmod 600) sudah dijalankan sebelum Langkah 3.

Jawaban :  
1. Nilai Default: Berdasarkan output nilainya adalah 60 yang artinya kernel cukup agresif dalam memindahkan data yang jarang digunakan dari RAM ke Swap. Ini bertujuan agar RAM tetap memiliki ruang kosong untuk cache sistem, namun bisa menyebabkan sedikit peningkatan aktivitas disk.
2. Konfirmasi: Ya, nilai telah berhasil berubah menjadi 10 (terlihat pada perintah cat terakhir). Dampak: Dengan nilai 10, kernel akan meminimalkan penggunaan swap. Kernel hanya akan menggunakan swap jika RAM benar-benar hampir habis. Ini biasanya meningkatkan responsivitas sistem karena data lebih lama berada di RAM yang jauh lebih cepat daripada disk.
3. Ya sudah muncul dengan ukuran 512M. 

## Praktikum 10.4

### Langkah 1
Input
```bash
ps aux --sort=-%mem | head
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux --sort=-%mem | head
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1082  0.9  1.1 617888 44068 ?        Ssl  05:43   0:10 /usr/libexec/fwupd/fwupd
root         390  0.1  0.6 288988 27324 ?        SLsl 05:41   0:02 /sbin/multipathd -d -s
root         688  0.0  0.5 109640 23072 ?        Ssl  05:41   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         338  0.0  0.4  50472 16296 ?        S<s  05:41   0:00 /usr/lib/systemd/systemd-journald
root         654  0.0  0.3 468972 13532 ?        Ssl  05:41   0:00 /usr/libexec/udisks2/udisksd
root           1  0.1  0.3  22032 13212 ?        Ss   05:41   0:01 /sbin/init splash noprompt noshell automatic-ubiquity
root         709  0.0  0.3 392100 13096 ?        Ssl  05:41   0:00 /usr/sbin/ModemManager
systemd+     465  0.0  0.3  21584 13048 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd-resolved
dafanr11     956  0.0  0.2  20272 11428 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd --user
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 2
Input
```bash
top
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ top
top - 06:03:09 up 21 min,  2 users,  load average: 0.00, 0.01, 0.00
Tasks: 136 total,   1 running, 135 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.1 us,  0.5 sy,  0.0 ni, 95.1 id,  0.1 wa,  0.0 hi,  4.2 si,  0.0 st
MiB Mem :   3819.3 total,   3291.7 free,    423.5 used,    320.1 buff/cache
MiB Swap:    512.0 total,    512.0 free,      0.0 used.   3395.8 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
     92 root      20   0       0      0      0 I   1.3   0.0   0:03.90 kworker/3:1-events
    390 root      rt   0  288988  27324   8760 S   0.7   0.7   0:02.27 multipathd
     42 root      20   0       0      0      0 I   0.3   0.0   0:00.25 kworker/u12:0-events_unbound
   1176 dafanr11  20   0   11936   5956   3732 R   0.3   0.2   0:00.30 top
      1 root      20   0   22032  13212   9540 S   0.0   0.3   0:01.30 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.03 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
      9 root      20   0       0      0      0 I   0.0   0.0   0:00.04 kworker/0:1-cgroup_free
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/u8:0-ipv6_addrconf
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.56 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.10 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.50 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.03 ksoftirqd/1
     26 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/1:0H-kblockd
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.50 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.30 ksoftirqd/2
     31 root      20   0       0      0      0 I   0.0   0.0   0:04.61 kworker/2:0-events
     32 root       0 -20       0      0      0 I   0.0   0.0   0:00.04 kworker/2:0H-kblockd
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
```

### Analisis
1. Proses apa yang berada di urutan pertama? Catat nilai %MEM dan RSS-nya.
2. Konversikan RSS dari KB ke MB (bagi 1024). Misalnya, RSS=524288 berarti proses menggunakan 512 MB RAM. Apakah wajar untuk jenis program tersebut?
3. Mengapa VSZ selalu lebih besar dari RSS pada proses yang sama?
4. Apakah urutan proses di ps konsisten dengan tampilan top saat diurutkan berdasarkan %MEM?

Jawaban :  
1. Berdasarkan output ps aux --sort=-%mem | head: COMMAND: /usr/libexec/fwupd/fwupd %MEM: 1.1% RSS: 44.068 (dalam unit Kilobytes)
2. 44.068 / 1024 = 43,03 MB Analisis: Sangat wajar. fwupd adalah Firmware Update Daemon. Untuk sebuah layanan latar belakang (background service) di Ubuntu yang bertugas menangani pembaruan perangkat keras, penggunaan RAM sekitar 43 MB tergolong normal dan efisien.
3. VSZ (Virtual Memory Size) mencakup seluruh memori yang dapat diakses oleh proses, termasuk shared libraries, memori yang di-swap, dan memori yang sudah dialokasikan tapi belum digunakan. RSS (Resident Set Size) hanya menghitung memori fisik (RAM) yang benar-benar sedang digunakan dan berada di RAM saat ini.
4. Ya, konsisten. Di ps, proses tertinggi adalah fwupd (1.1%) diikuti multipathd (0.6%). Di top, jika melihat kolom %MEM, multipathd muncul di atas dengan 0.7%. Angka ini sedikit berubah dari 0.6% di ps (yang dijalankan beberapa detik sebelumnya) karena top bersifat real-time. Meskipun fwupd tidak terlihat di baris teratas tampilan top, hal itu karena top yang di tampilkan diurutkan berdasarkan %CPU (bukan %MEM). Namun, nilai persentasenya tetap berada dalam rentang yang serupa.
 

## Praktikum 10.5

### Langkah 1
Input
```bash
nano monitor-memori.sh
#!/bin/bash
set -euo pipefail

THRESHOLD=20

echo "=== Monitor Memori ==="
date
echo

free -h

echo

AVAIL=$(free | awk '/Mem/ {printf "%d", $7/$2*100}')
if [ "$AVAIL" -lt "$THRESHOLD" ]; then
    echo "PERINGATAN: Memori tersedia hanya ${AVAIL}%"
else
    echo "Status: Memori tersedia ${AVAIL}% (normal)"
fi

echo
echo "--- 5 Proses Memori Tertinggi ---"
ps aux --sort=-%mem | head -n 6 | tail -n 5
```

### Langkah 2
Input
```bash
chmod +x monitor-memori.sh
bash monitor-memori.sh
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ chmod +x monitor-memori.sh
dafanr11@Ubuntu-Server-New:~$ bash monitor-memori.sh
=== Monitor Memori ===
Sun May 10 06:10:42 AM UTC 2026

               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       423Mi       3.2Gi       1.0Mi       321Mi       3.3Gi
Swap:          511Mi          0B       511Mi

Status: Memori tersedia 88% (normal)

--- 5 Proses Memori Tertinggi ---
root        1082  0.6  1.1 617888 44068 ?        Ssl  05:43   0:11 /usr/libexec/fwupd/fwupd
root         390  0.1  0.6 288988 27324 ?        SLsl 05:41   0:02 /sbin/multipathd -d -s
root         688  0.0  0.5 109640 23072 ?        Ssl  05:41   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         338  0.0  0.4  50472 16300 ?        S<s  05:41   0:00 /usr/lib/systemd/systemd-journald
root         654  0.0  0.3 468972 13532 ?        Ssl  05:41   0:00 /usr/libexec/udisks2/udisksd
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Variabel THRESHOLD=20 menetapkan batas persentase. Perintah free | awk ’/Mem/ {printf "%d", $7/$2*100}’ mengambil kolom ke-7 (available) dibagi kolom ke-2 (total) dari baris Mem, lalu dikalikan 100 untuk menghasilkan persentase bilangan bulat.
2. Kondisi if [ "$AVAIL" -lt "$THRESHOLD" ] bernilai benar jika persentase memori tersedia di bawah 20.
3. Ubah THRESHOLD menjadi 90 dan jalankan ulang. Apa yang berubah pada output? Mengapa demikian?

Jawaban :  
3. Jika mengubah THRESHOLD=90 dan menjalankan ulang script:
Apa yang berubah? Pesan status kemungkinan besar akan berubah dari "normal" menjadi pesan peringatan/warning (tergantung isi teks di dalam blok if pada script ).
Mengapa demikian? Karena kondisi if [ "88" -lt "90" ] sekarang bernilai Benar (True).
Analisis: Secara teknis, RAM masih sangat lega (88%), namun karena menetapkan "batas waspada" yang sangat tinggi (90%), script akan menganggap sisa RAM 88% sudah masuk kategori "kurang dari batas aman".


## Praktikum 10.6

### Langkah 1
Input
```bash
strace ls 2>&1 | head -n 30
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ strace ls 2>&1 | head -n 30
execve("/usr/bin/ls", ["ls"], 0x7ffdbd6cc3c0 /* 22 vars */) = 0
brk(NULL)                               = 0x59442a95a000
mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x75608d8ae000
access("/etc/ld.so.preload", R_OK)      = -1 ENOENT (No such file or directory)
openat(AT_FDCWD, "/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3
fstat(3, {st_mode=S_IFREG|0644, st_size=32431, ...}) = 0
mmap(NULL, 32431, PROT_READ, MAP_PRIVATE, 3, 0) = 0x75608d8a6000
close(3)                                = 0
openat(AT_FDCWD, "/lib/x86_64-linux-gnu/libselinux.so.1", O_RDONLY|O_CLOEXEC) = 3
read(3, "\177ELF\2\1\1\0\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\0\0\0\0\0\0\0\0"..., 832) = 832
fstat(3, {st_mode=S_IFREG|0644, st_size=174472, ...}) = 0
mmap(NULL, 181960, PROT_READ, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0x75608d879000
mmap(0x75608d87f000, 118784, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x6000) = 0x75608d87f000
mmap(0x75608d89c000, 24576, PROT_READ, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x23000) = 0x75608d89c000
mmap(0x75608d8a2000, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x29000) = 0x75608d8a2000
mmap(0x75608d8a4000, 5832, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0x75608d8a4000
close(3)                                = 0
openat(AT_FDCWD, "/lib/x86_64-linux-gnu/libc.so.6", O_RDONLY|O_CLOEXEC) = 3
read(3, "\177ELF\2\1\1\3\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\220\243\2\0\0\0\0\0"..., 832) = 832
pread64(3, "\6\0\0\0\4\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0"..., 784, 64) = 784
fstat(3, {st_mode=S_IFREG|0755, st_size=2125328, ...}) = 0
pread64(3, "\6\0\0\0\4\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0@\0\0\0\0\0\0\0"..., 784, 64) = 784
mmap(NULL, 2170256, PROT_READ, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0x75608d600000
mmap(0x75608d628000, 1605632, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x28000) = 0x75608d628000
mmap(0x75608d7b0000, 323584, PROT_READ, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x1b0000) = 0x75608d7b0000
mmap(0x75608d7ff000, 24576, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x1fe000) = 0x75608d7ff000
mmap(0x75608d805000, 52624, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0x75608d805000
close(3)                                = 0
openat(AT_FDCWD, "/lib/x86_64-linux-gnu/libpcre2-8.so.0", O_RDONLY|O_CLOEXEC) = 3
read(3, "\177ELF\2\1\1\0\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0\0\0\0\0\0\0\0\0"..., 832) = 832
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 2
Input
```bash
strace -c ls
strace -c ls /etc 2>&1 | tail -5
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ strace -c ls
all-config-files.txt  backup.tar  hasil-pencarian.txt  play           Sistem-Operasi
backup-error.log      error.log   large-logs.txt       praktikum-os   sorted-users.txt
backup-success.log    error.txt   monitor-memori.sh    Sistem-Opeasi  system-monitor-20260303-145605.log
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
 20.84    0.011227         623        18           mmap
 13.74    0.007402        7402         1           execve
 10.82    0.005831         728         8           fstat
  8.39    0.004522         502         9           close
  8.29    0.004465        2232         2           ioctl
  6.61    0.003562        3562         1           rseq
  6.50    0.003504        1168         3           brk
  6.46    0.003482         696         5           read
  4.90    0.002640         377         7           openat
  3.77    0.002031        1015         2           pread64
  2.56    0.001378         689         2         2 statfs
  2.28    0.001228         245         5           mprotect
  1.99    0.001071         357         3           write
  1.32    0.000709         354         2           getdents64
  0.60    0.000325         325         1           munmap
  0.30    0.000160         160         1           set_robust_list
  0.29    0.000157         157         1           arch_prctl
  0.27    0.000145         145         1           set_tid_address
  0.04    0.000023          23         1           prlimit64
  0.04    0.000023          23         1           getrandom
  0.00    0.000000           0         2         2 access
------ ----------- ----------- --------- --------- ----------------
100.00    0.053885         709        76         4 total
dafanr11@Ubuntu-Server-New:~$ strace -c ls /etc 2>&1 | tail -5
  0.45    0.000221         221         1           getrandom
  0.03    0.000015          15         1           arch_prctl
  0.00    0.000000           0         1           execve
------ ----------- ----------- --------- --------- ----------------
100.00    0.048577         656        74         5 total
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Dari output Langkah 1, identifikasi minimal 4 system call berbeda. Jelaskan fungsi singkat masing-masing berdasarkan argumen yang terlihat.
2. Dari ringkasan strace -c, system call mana yang paling sering dipanggil? Mengapa?
3. Apakah ada system call dengan errors lebih dari 0? Apakah itu berarti program bermasalah, ataukah bagian normal dari logika program?
4. Apakah jumlah system call berbeda antara ls dan ls /etc? Faktor apa yang menyebabkan perbedaan tersebut?

Jawaban :  
1. execve: Menjalankan program (memulai perintah ls). openat: Membuka file atau direktori (misal: memuat library sistem). mmap: Mengalokasikan memori (memetakan data file ke RAM). close: Menutup akses file yang sudah tidak digunakan.
2. Paling Sering: mmap (18 kali). Terbanyak karena setiap program Ubuntu perlu memetakan banyak file library (.so) ke dalam memori agar bisa berjalan.
3. Ada (4-5 errors). Ini normal, bukan tanda program rusak. Misalnya, ls mencoba mencari file konfigurasi yang opsional; jika tidak ada (ENOENT), sistem hanya akan lanjut ke langkah berikutnya.
4. Jumlah berbeda (76 vs 74). Penyebabnya: 
Isi direktori: Jumlah file yang dibaca berbeda.
Resolusi Path: Proses kernel dalam mencari alamat /etc berbeda dengan direktori saat ini.


## STUDI KASUS

## Studi Kasus 10.1

### Langkah 1
Input
```bash
free -h
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ free -h
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       430Mi       3.2Gi       1.0Mi       323Mi       3.3Gi
Swap:          511Mi          0B       511Mi
dafanr11@Ubuntu-Server-New:~$
```

### Langkah 2
Input
```bash
top
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ top
top - 06:21:46 up 40 min,  2 users,  load average: 0.00, 0.00, 0.00
Tasks: 136 total,   1 running, 135 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.4 sy,  0.0 ni, 95.0 id,  0.0 wa,  0.0 hi,  4.6 si,  0.0 st
MiB Mem :   3819.3 total,   3280.5 free,    430.9 used,    324.0 buff/cache
MiB Swap:    512.0 total,    512.0 free,      0.0 used.   3388.4 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
   1199 root      20   0       0      0      0 I   2.0   0.0   0:02.81 kworker/2:1-events
    390 root      rt   0  288988  27324   8760 S   0.7   0.7   0:04.11 multipathd
     73 root      20   0       0      0      0 I   0.3   0.0   0:00.50 kworker/u11:1-events_power_efficient
   1314 dafanr11  20   0   11936   5964   3740 R   0.3   0.2   0:00.05 top
      1 root      20   0   22032  13212   9540 S   0.0   0.3   0:01.49 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.03 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     11 root      20   0       0      0      0 I   0.0   0.0   0:00.00 kworker/u8:0-ipv6_addrconf
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.02 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.99 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.19 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.58 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.03 ksoftirqd/1
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.59 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.42 ksoftirqd/2
     32 root       0 -20       0      0      0 I   0.0   0.0   0:00.04 kworker/2:0H-kblockd
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
     34 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
     35 root      rt   0       0      0      0 S   0.0   0.0   0:00.50 migration/3
     36 root      20   0       0      0      0 S   0.0   0.0   0:00.94 ksoftirqd/3
```

### Analisis
1. Apakah nilai available sangat kecil (misalnya di bawah 200 MB pada server dengan RAM 2 GB)? Jika ya, server kemungkinan kekurangan memori.
2. Apakah kolom used pada baris Swap lebih dari 0? Jika ya, kernel sedang menggunakan swap, yang berarti performa menurun.
3. Di tampilan top, proses apa yang memiliki %MEM terbesar? Proses tersebut menjadi kandidat utama penyebab lambatnya server.

Jawaban :  
1. Analisis: Nilai available adalah 3.3 GiB. Kesimpulan: Server SANGAT AMAN. Dengan total RAM 3.7 GiB, sisa 3.3 GiB berarti hanya sekitar 10-12% RAM yang terpakai. Tidak ada indikasi kekurangan memori. 
2. Analisis: Kolom used pada baris Swap bernilai 0B. Kesimpulan: Performa server OPTIMAL. Kernel tidak menggunakan swap sama sekali karena RAM fisik masih sangat mencukupi untuk menangani semua proses yang berjalan.
3. Analisis: Berdasarkan kolom %MEM di tampilan top:
Peringkat 1: multipathd dengan 0.7%.
Peringkat 2: systemd dengan 0.3%.
Peringkat 3: top sendiri dengan 0.2%.

## Studi Kasus 10.2

### Langkah 1
Input
```bash
mkdir -p ~/Sistem-Operasi/Minggu10-memory/syscall-case
cd ~/Sistem-Operasi/Minggu10-memory/syscall-case
echo "PORT=8080" > app.conf
ls -l app.conf
cat app.conf
```

Output
```bash
dafanr11@Ubuntu-Server-New:~$ mkdir -p ~/Sistem-Operasi/Minggu10-memory/syscall-case
dafanr11@Ubuntu-Server-New:~$ cd ~/Sistem-Operasi/Minggu10-memory/syscall-case
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ echo "PORT=8080" > app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ ls -l app.conf
-rw-rw-r-- 1 dafanr11 dafanr11 10 May 10 06:25 app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ cat app.conf
PORT=8080
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$
```

### Langkah 2
Input
```bash
chmod 000 app.conf
ls -l app.conf
sudo -u nobody cat app.conf
```

Output
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ chmod 000 app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ ls -l app.conf
---------- 1 dafanr11 dafanr11 10 May 10 06:25 app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ sudo -u nobody cat app.conf
[sudo] password for dafanr11:
cat: app.conf: Permission denied
```

### Langkah 3
Input
```bash
chmod 644 app.conf
ls -l app.conf
cat app.conf
```

Output
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ chmod 644 app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ ls -l app.conf
-rw-r--r-- 1 dafanr11 dafanr11 10 May 10 06:25 app.conf
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ cat app.conf
PORT=8080
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$
```

### Analisis
1. Mengapa cat menghasilkan Permission denied setelah chmod 000? System call apa yang gagal?
2. Apa perbedaan pesan error Permission denied vs No such file or directory? Coba rm app.conf lalu cat app.conf untuk melihat perbedaannya.
3. Permission 644 berarti apa untuk owner, group, dan others?

Jawaban :  
1. Penyebab: Perintah chmod 000 menghapus semua hak akses (read, write, execute) untuk siapa pun, termasuk pemiliknya sendiri. System Call yang Gagal: openat(). Saat cat mencoba membuka file, kernel memeriksa tabel izin file. Karena izinnya 000, kernel menolak memberikan file descriptor dan mengembalikan error EACCES (Permission denied).
2. Permission denied (EACCES): Filenya ada, tapi sistem operasi melarang mengaksesnya karena masalah hak izin (permission) sedangkan No such file or directory (ENOENT): Filenya tidak ada di lokasi tersebut. Kernel tidak bisa menemukan inode atau nama file yang dimaksud dalam direktori.
3. Owner (6): Read (4) + Write (2). Pemilik bisa membaca dan mengubah isi file. Group (4): Read. Anggota grup hanya bisa membaca file. Others (4): Read. Orang lain di luar pemilik dan grup hanya bisa membaca file.  

## TUGAS

## Tugas 10.1

### Langkah 1
Input :
```bash
nano memory-audit.sh
```

### Langkah 2
Input :
```bash
#!/bin/bash
set -euo pipefail

LAPORAN="memory-report.txt"

{
    echo "=== LAPORAN MEMORI SISTEM ==="
    date
    echo
    echo "--- Ringkasan free -h ---"
    free -h
    echo
    echo "--- /proc/meminfo ---"
    cat /proc/meminfo | head -n 20
} > "$LAPORAN"

echo "Laporan disimpan ke: $LAPORAN"
cat "$LAPORAN"
```

### Langkah 3
Input :
```bash
chmod +x ~/Sistem-Operasi/Minggu10-memory/syscall-case/memory-audit.sh
cd ~/Sistem-Operasi/Minggu10-memory/syscall-case
bash memory-audit.sh
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ nano memory-audit.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ chmod +x ~/Sistem-Operasi/Minggu10-memory/syscall-case/memory-audit.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ cd ~/Sistem-Operasi/Minggu10-memory/syscall-case
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ bash memory-audit.sh
Laporan disimpan ke: memory-report.txt
=== LAPORAN MEMORI SISTEM ===
Sun May 10 06:48:49 AM UTC 2026

--- Ringkasan free -h ---
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       427Mi       3.2Gi       1.0Mi       325Mi       3.3Gi
Swap:          511Mi          0B       511Mi

--- /proc/meminfo ---
MemTotal:        3910968 kB
MemFree:         3361148 kB
MemAvailable:    3472816 kB
Buffers:           21008 kB
Cached:           292932 kB
SwapCached:            0 kB
Active:           284348 kB
Inactive:          71000 kB
Active(anon):      51232 kB
Inactive(anon):        0 kB
Active(file):     233116 kB
Inactive(file):    71000 kB
Unevictable:       27316 kB
Mlocked:           27316 kB
SwapTotal:        524284 kB
SwapFree:         524284 kB
Zswap:                 0 kB
Zswapped:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$
```

### Analisis
1. Hitung persentase memori tersedia (available / total × 100%). Apakah sistem dalam kondisi normal?
2. Mengapa buff/cache tidak dihitung sebagai memori yang terpakai dari sudut pandang ketersediaan untuk aplikasi?
3. Dari /proc/meminfo, apakah SwapTotal lebih besar dari 0? Berapa nilai SwapFree?

Jawaban :  
1. Available/Total * 100% = 3,3/ 3,7 * 100% =89,1% Sistem dalam kondisi Sangat Normal. Memori tersedia jauh di atas ambang batas kritis 10%.
2. buff/cache adalah memori yang digunakan kernel untuk mempercepat akses data disk. Namun, jika ada aplikasi yang mendadak butuh RAM, kernel akan langsung melepaskan (evict) data di cache tersebut dan memberikannya ke aplikasi. Jadi, secara teknis memori ini tetap tersedia untuk aplikasi kapan saja.
3. SwapTotal: 524284 kB (Artinya lebih besar dari 0, yaitu sekitar 512 MiB). SwapFree: 524284 kB. Kesimpulan: Memiliki area Swap yang aktif, tetapi saat ini kosong (tidak terpakai sama sekali) karena SwapFree nilainya sama persis dengan SwapTotal.


## Tugas 10.2

### Langkah 1
Input :
```bash
ps aux --sort=-%mem | head -n 10 > top-memory-process.txt
cat top-memory-process.txt
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux --sort=-%mem | head -n 10 > top-memory-process.txt
dafanr11@Ubuntu-Server-New:~$ cat top-memory-process.txt
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1082  0.2  1.1 617888 44208 ?        Ssl  05:43   0:12 /usr/libexec/fwupd/fwupd
root         390  0.1  0.6 288988 27324 ?        SLsl 05:41   0:07 /sbin/multipathd -d -s
root         688  0.0  0.5 109640 23072 ?        Ssl  05:41   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         338  0.0  0.4  50472 16368 ?        S<s  05:41   0:00 /usr/lib/systemd/systemd-journald
root         654  0.0  0.3 468972 13552 ?        Ssl  05:41   0:00 /usr/libexec/udisks2/udisksd
root           1  0.0  0.3  22032 13212 ?        Ss   05:41   0:01 /sbin/init splash noprompt noshell automatic-ubiquity
root         709  0.0  0.3 392100 13096 ?        Ssl  05:41   0:00 /usr/sbin/ModemManager
systemd+     465  0.0  0.3  21584 13048 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd-resolved
dafanr11     956  0.0  0.2  20272 11428 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd --user
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Proses apa di urutan pertama? Catat nilai %MEM dan RSS.
2. Konversikan RSS ke MB (bagi 1024). Apakah wajar?
3. Jumlahkan %MEM dari 5 proses teratas. Berapa persen RAM yang mereka gunakan bersama?

Jawaban :  
1. Proses Urutan Pertama
COMMAND: /usr/libexec/fwupd/fwupd
%MEM: 1.1%
RSS: 44.208 KB
2. 44.208/1024 = 43,17 MB, Analisis: Sangat wajar. Ini adalah daemon pembaruan firmware standar Ubuntu. Penggunaan memori sekitar 43 MB untuk layanan latar belakang sistem termasuk kategori sangat ringan.
3. 2,9 persen, Kelima proses teratas hanya menggunakan total 2,9% dari RAM. Ini menunjukkan bahwa server memiliki banyak sumber daya menganggur dan siap untuk menjalankan aplikasi berat lainnya.

## Tugas 10.3

### Langkah 1
Input :
```bash
sudo fallocate -l 256M /swapfile-tugas-Minggu10
ls -lh /swapfile-tugas-Minggu10
sudo chmod 600 /swapfile-tugas-Minggu10
sudo mkswap /swapfile-tugas-Minggu10
sudo swapon /swapfile-tugas-Minggu10
swapon --show
```

### Langkah 2
Input :
```bash
{
    echo "=== VERIFIKASI SWAP ==="
    swapon --show
    echo
    free -h
} > swap-check.txt

cat swap-check.txt
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ sudo fallocate -l 256M /swapfile-tugas-Minggu10
[sudo] password for dafanr11:
dafanr11@Ubuntu-Server-New:~$ ls -lh /swapfile-tugas-Minggu10
-rw-r--r-- 1 root root 256M May 10 07:00 /swapfile-tugas-Minggu10
dafanr11@Ubuntu-Server-New:~$ sudo chmod 600 /swapfile-tugas-Minggu10
dafanr11@Ubuntu-Server-New:~$ sudo mkswap /swapfile-tugas-Minggu10
Setting up swapspace version 1, size = 256 MiB (268431360 bytes)
no label, UUID=94bd5ab4-1ecc-4edb-8f42-40465b72ac56
dafanr11@Ubuntu-Server-New:~$ sudo swapon /swapfile-tugas-Minggu10
dafanr11@Ubuntu-Server-New:~$ swapon --show
NAME                     TYPE SIZE USED PRIO
/swapfile-Minggu10       file 512M   0B   -2
/swapfile-tugas-Minggu10 file 256M   0B   -3
dafanr11@Ubuntu-Server-New:~$ {
    echo "=== VERIFIKASI SWAP ==="
    swapon --show
    echo
    free -h
} > swap-check.txt

cat swap-check.txt
=== VERIFIKASI SWAP ===
NAME                     TYPE SIZE USED PRIO
/swapfile-Minggu10       file 512M   0B   -2
/swapfile-tugas-Minggu10 file 256M   0B   -3

               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       434Mi       3.2Gi       1.0Mi       326Mi       3.3Gi
Swap:          767Mi          0B       767Mi
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Identifikasi kolom NAME, TYPE, SIZE, dan USED pada output swapon –show.
2. Apakah nilai total pada baris Swap di free -h bertambah 256 MB?
3. Mengapa permission 600 penting? Apa risiko jika diatur ke 644?

Jawaban :  
1. Berdasarkan baris /swapfile-tugas-Minggu10:
NAME: /swapfile-tugas-Minggu10 (Lokasi dan nama file swap).
TYPE: file (Menunjukkan swap berupa file, bukan partisi disk).
SIZE: 256M (Kapasitas total swapfile tersebut).
USED: 0B (Jumlah swap yang sedang digunakan saat ini).
2. Ya, bertambah. Sebelumnya (pada log sebelumnya), total swap adalah 511Mi / 512Mi. Setelah menambah swapfile 256M, output free -h sekarang menunjukkan total 767Mi. Hitungannya: 511 + 256 = 767 MiB.
3. Pentingnya: Izin 600 (-rw-------) memastikan bahwa hanya root yang bisa membaca atau menulis ke file tersebut. Risiko Izin 644: Jika diatur ke 644, pengguna biasa (others) bisa membaca isi swapfile tersebut. Bahaya Keamanan: Swap menyimpan data yang "tumpah" dari RAM. Ini bisa berisi informasi sensitif seperti password, kunci enkripsi, atau data pribadi dari aplikasi yang sedang berjalan. Jika orang lain bisa membaca file tersebut, mereka bisa mencuri data sensitif tersebut.

## Tugas 10.4

### Langkah 1
Input :
```bash
strace -c ls 2> strace-summary.txt
strace ls /etc 2> strace-ls-etc.txt
cat strace-summary.txt
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ strace -c ls 2> strace-summary.txt
all-config-files.txt  backup.tar  hasil-pencarian.txt  monitor-memori.sh  Sistem-Opeasi     strace-summary.txt                  top-memory-process.txt
backup-error.log      error.log   large-logs.txt       play               Sistem-Operasi    swap-check.txt
backup-success.log    error.txt   memory-audit.sh      praktikum-os       sorted-users.txt  system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$ strace ls /etc 2> strace-ls-etc.txt
adduser.conf            cryptsetup-initramfs  gshadow          libblockdev     mtab                 pm             sensors.d          timezone
alternatives            crypttab              gshadow-         libibverbs.d    multipath            polkit-1       services           tmpfiles.d
apparmor                dbus-1                gss              libnl-3         multipath.conf       pollinate      sgml               ubuntu-advantage
apparmor.d              debconf.conf          hdparm.conf      libpaper.d      nanorc               profile        shadow             ucf.conf
apport                  debian_version        host.conf        locale.alias    needrestart          profile.d      shadow-            udev
apt                     default               hostname         locale.conf     netconfig            protocols      shells             udisks2
bash.bashrc             deluser.conf          hosts            locale.gen      netplan              python3        skel               ufw
bash_completion         depmod.d              hosts.allow      localtime       network              python3.12     sos                update-manager
bash_completion.d       dhcp                  hosts.deny       logcheck        networkd-dispatcher  rc0.d          ssh                update-motd.d
bindresvport.blacklist  dhcpcd.conf           ImageMagick-6    login.defs      networks             rc1.d          ssl                update-notifier
binfmt.d                dpkg                  init.d           logrotate.conf  newt                 rc2.d          subgid             UPower
byobu                   e2scrub.conf          initramfs-tools  logrotate.d     nftables.conf        rc3.d          subgid-            usb_modeswitch.conf
ca-certificates         environment           inputrc          lsb-release     nsswitch.conf        rc4.d          subuid             usb_modeswitch.d
ca-certificates.conf    ethertypes            iproute2         lvm             opt                  rc5.d          subuid-            vconsole.conf
cloud                   fonts                 iscsi            machine-id      os-release           rc6.d          sudo.conf          vim
console-setup           fstab                 issue            magic           overlayroot.conf     rcS.d          sudoers            vmware-tools
credstore               fuse.conf             issue.net        magic.mime      PackageKit           resolv.conf    sudoers.d          vtrgb
credstore.encrypted     fwupd                 kernel           manpath.config  pam.conf             rmt            sudo_logsrvd.conf  w3m
cron.d                  gai.conf              landscape        mdadm           pam.d                rpc            supercat           wgetrc
cron.daily              ghostscript           ldap             mime.types      papersize            rsyslog.conf   sysctl.conf        X11
cron.hourly             gnutls                ld.so.cache      mke2fs.conf     passwd               rsyslog.d      sysctl.d           xattr.conf
cron.monthly            groff                 ld.so.conf       ModemManager    passwd-              screenrc       sysstat            xdg
crontab                 group                 ld.so.conf.d     modprobe.d      perl                 security       systemd            xml
cron.weekly             group-                legal            modules         pki                  selinux        terminfo           zsh_command_not_found
cron.yearly             grub.d                libaudit.conf    modules-load.d  plymouth             sensors3.conf  thermald
dafanr11@Ubuntu-Server-New:~$ cat strace-summary.txt
% time     seconds  usecs/call     calls    errors syscall
------ ----------- ----------- --------- --------- ----------------
 26.68    0.004924         273        18           mmap
 20.39    0.003763         418         9           close
 17.51    0.003232        3232         1           execve
 16.39    0.003025         378         8           fstat
  6.87    0.001267         633         2           pread64
  4.15    0.000766         109         7           openat
  2.72    0.000502         167         3           write
  2.35    0.000433         433         1           munmap
  0.80    0.000147          29         5           read
  0.69    0.000128          64         2           getdents64
  0.57    0.000106          21         5           mprotect
  0.22    0.000041          20         2         2 access
  0.22    0.000040          20         2         2 statfs
  0.21    0.000038          12         3           brk
  0.09    0.000016           8         2           ioctl
  0.04    0.000007           7         1           getrandom
  0.03    0.000006           6         1           prlimit64
  0.03    0.000005           5         1           arch_prctl
  0.02    0.000003           3         1           set_tid_address
  0.02    0.000003           3         1           set_robust_list
  0.02    0.000003           3         1           rseq
------ ----------- ----------- --------- --------- ----------------
100.00    0.018455         242        76         4 total
dafanr11@Ubuntu-Server-New:~$
```

### Analisis
1. Sebutkan minimal 5 system call dari strace-summary.txt beserta fungsi singkatnya.
2. System call mana yang paling sering dipanggil? Mengapa?
3. Apakah ada errors lebih dari 0? Apakah program tetap berjalan normal meskipun ada kegagalan tersebut?

Jawaban :   
1. mmap: Memetakan file atau perangkat ke dalam memori (alokasi memori). close: Menutup deskriptor file yang sudah dibuka. execve: Mengeksekusi program (dalam hal ini menjalankan perintah /usr/bin/ls). fstat: Mendapatkan status/informasi sebuah file (seperti ukuran atau jenis file). openat: Membuka file atau direktori untuk dibaca atau ditulis.
2. System call yang paling sering dipanggil adalah mmap (sebanyak 18 kali). Alasannya program ls sangat bergantung pada berbagai pustaka bersama (shared libraries seperti libc.so). Setiap kali pustaka tersebut dimuat, sistem perlu memanggil mmap berkali-kali untuk memetakan bagian-bagian kode dan data dari pustaka tersebut ke dalam ruang alamat memori proses.
3. Ya, terdapat errors. Apakah program tetap normal? Ya, tetap berjalan normal. Errors pada system call sering kali merupakan bagian dari logika normal program. Misalnya, program mencoba mengecek keberadaan file konfigurasi di lokasi tertentu menggunakan access. Jika file tidak ada, sistem mengembalikan error (seperti ENOENT), lalu program akan mencoba mencari di lokasi lain atau menggunakan nilai default. Ini bukan berarti aplikasi rusak, melainkan cara aplikasi beradaptasi dengan lingkungan sistem.


## Tugas 10.5

### Langkah 1
Input :
```bash
nano diagnosa-server.sh
```

### Langkah 2
Input :
```bash
#!/bin/bash
set -euo pipefail

LAPORAN="diagnosa-server-lambat.txt"
WARN_MEM=false
WARN_SWAP=0

cek_memori() {
    echo "--- Kondisi Memori ---"
    free -h
    echo
    AVAIL_PCT=$(free | awk '/Mem/ {printf "%d", $7/$2*100}')
    if [ "$AVAIL_PCT" -lt 20 ]; then
        echo "PERINGATAN: Memori tersedia hanya ${AVAIL_PCT}%"
        WARN_MEM=true
    fi
}

cek_swap() {
    echo "--- Penggunaan Swap ---"
    swapon --show 2>/dev/null || echo "Tidak ada swap aktif"
    echo
    WARN_SWAP=$(free | awk '/Swap/ {print $3}')
    if [ "$WARN_SWAP" -gt 0 ]; then
        echo "INFO: Swap digunakan (${WARN_SWAP} kB)"
    fi
}

cek_proses() {
    echo "--- 10 Proses Memori Tertinggi ---"
    ps aux --sort=-%mem | head -n 11
    echo
}

cek_paging() {
    echo "--- Aktivitas Paging (5 sampel) ---"
    vmstat 1 5
    echo
}

ringkasan() {
    echo "=== RINGKASAN ==="
    if [ "$WARN_MEM" = true ]; then
        echo "- Memori: KRITIS - perlu tindakan segera"
    else
        echo "- Memori: normal"
    fi
    if [ "$WARN_SWAP" -gt 0 ]; then
        echo "- Swap: aktif - pantau aktivitas paging"
    else
        echo "- Swap: tidak digunakan"
    fi
}

{
    echo "=== LAPORAN DIAGNOSA SERVER ==="
    date
    echo
    cek_memori
    cek_swap
    cek_proses
    cek_paging
    ringkasan
} | tee "$LAPORAN"

echo
echo "Laporan disimpan ke: $LAPORAN"
```

### Langkah 3
Input :
```bash
chmod +x diagnosa-server.sh
cd ~/Sistem-Operasi/Minggu10-memory
./diagnosa-server.sh
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ cd ~/Sistem-Operasi/Minggu10-memory/syscall-case
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ chmod +x diagnosa-server.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$ ./diagnosa-server.sh
=== LAPORAN DIAGNOSA SERVER ===
Sun May 10 07:18:13 AM UTC 2026

--- Kondisi Memori ---
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       433Mi       3.2Gi       1.0Mi       327Mi       3.3Gi
Swap:          767Mi          0B       767Mi

--- Penggunaan Swap ---
NAME                     TYPE SIZE USED PRIO
/swapfile-Minggu10       file 512M   0B   -2
/swapfile-tugas-Minggu10 file 256M   0B   -3

--- 10 Proses Memori Tertinggi ---
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1082  0.2  1.1 617888 44208 ?        Ssl  05:43   0:12 /usr/libexec/fwupd/fwupd
root         390  0.1  0.6 288988 27324 ?        SLsl 05:41   0:09 /sbin/multipathd -d -s
root         688  0.0  0.5 109640 23072 ?        Ssl  05:41   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         338  0.0  0.4  50472 16388 ?        S<s  05:41   0:00 /usr/lib/systemd/systemd-journald
root         654  0.0  0.3 468972 13552 ?        Ssl  05:41   0:00 /usr/libexec/udisks2/udisksd
root           1  0.0  0.3  22032 13212 ?        Ss   05:41   0:01 /sbin/init splash noprompt noshell automatic-ubiquity
root         709  0.0  0.3 392100 13096 ?        Ssl  05:41   0:00 /usr/sbin/ModemManager
systemd+     465  0.0  0.3  21584 13048 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd-resolved
dafanr11     956  0.0  0.2  20272 11428 ?        Ss   05:41   0:00 /usr/lib/systemd/systemd --user
root        1488  0.0  0.2  14964 10680 ?        Ss   06:55   0:00 sshd: dafanr11 [priv]

--- Aktivitas Paging (5 sampel) ---
procs -----------memory---------- ---swap-- -----io---- -system-- -------cpu-------
 r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st gu
 0  0      0 3353496  21884 313228    0    0    54    10 1256    0  0  5 95  0  0  0
 0  0      0 3353432  21884 313240    0    0     0     4 1438  157  0  3 96  0  0  0
 1  0      0 3353432  21884 313240    0    0     0     0 1310  182  0  6 94  0  0  0
 0  0      0 3353432  21884 313240    0    0     0     0 1388   67  0  4 96  0  0  0
 0  0      0 3353432  21884 313240    0    0     0     0 1488   68  0  4 96  0  0  0

=== RINGKASAN ===
- Memori: normal
- Swap: tidak digunakan

Laporan disimpan ke: diagnosa-server-lambat.txt
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu10-memory/syscall-case$
```

### Analisis
1. Jelaskan peran masing-masing fungsi: cek_memori, cek_swap, cek_proses, cek_paging, dan ringkasan. Mengapa diagnosa dipecah menjadi fungsi terpisah?
2. Berdasarkan bagian RINGKASAN, apakah kondisi sistem normal atau kritis? Jelaskan berdasarkan nilai threshold yang digunakan script.
3. Mengapa script menggunakan tee "$LAPORAN" bukan redirection biasa > "$LAPORAN"? Apa keuntungannya?
4. Dari output cek_paging, apakah ada aktivitas si atau so? Jika ada, apa implikasinya terhadap performa server?

Jawaban :  
1. Peran Fungsi-Fungsi Script:
cek_memori: Mengukur sisa RAM dan memberikan peringatan jika memori tersedia di bawah batas tertentu.
cek_swap: Memeriksa apakah ada partisi/file swap yang aktif dan berapa banyak yang sedang digunakan.
cek_proses: Mengidentifikasi 10 aplikasi atau layanan yang paling banyak memakan RAM.
cek_paging: Memantau lalu lintas data antara RAM dan Swap (I/O) secara real-time.
ringkasan: Memberikan kesimpulan akhir (Normal/Kritis) agar admin bisa cepat mengambil keputusan.
2. Kondisi sistem adalah NORMAL. Analisis Threshold: Di dalam script, ambang batas (threshold) memori kritis disetel pada 20%. Memori tersedia sekitar 89% (sangat jauh di atas 20%). Begitu juga dengan Swap yang digunakan bernilai 0, sehingga script menyimpulkan kondisi memori normal.
3. Jika menggunakan redirection biasa (>), output hanya akan masuk ke file dan layar terminal akan kosong. Keuntungan tee: Perintah ini membagi aliran data menjadi dua (seperti huruf T). Hasilnya muncul di layar (agar bisa langsung melihat) sekaligus disimpan ke file $LAPORAN. Ini sangat berguna untuk admin yang ingin memantau proses secara langsung sambil tetap memiliki arsip laporan.
4. Hasil Output: Nilai si (swap-in) dan so (swap-out) pada output kamu semuanya 0.
Implikasi: Ini adalah kondisi yang sangat ideal.
si = 0: Tidak ada data yang dipindahkan dari disk kembali ke RAM.
so = 0: Tidak ada data yang "dibuang" dari RAM ke Swap karena RAM penuh.
Kesimpulan Performa: Performa server sangat cepat karena semua proses berjalan sepenuhnya di RAM fisik tanpa mengalami pelambatan akibat akses ke disk (swap).