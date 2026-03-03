# Laporan Praktikum 3

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

# Latihan

## Latihan 3.1 

Buatlah script yang:
1. Menampilkan daftar 10 file terbesar di direktori /var/log/
2. Menyimpan hasilnya ke file large-logs.txt
3. Menampilkan output juga di terminal menggunakan tee
4. Menangani error dengan redirect ke error.log

### Jawaban  

Kode :  
```bash
dafanr11@Ubuntu-Server-New:~$ echo "===== Mencari 10 file terbesar di /var/log/ ====="
echo "Waktu: $(date)"
echo "----------------------------------------"

find /var/log/ -type f -exec ls -lh {} \; 2> error.log | sort -k5 -rh | head -10 | tee large-logs.txt

echo "----------------------------------------"
echo "Hasil disimpan di: large-logs.txt"
echo "Error disimpan di: error.log"
===== Mencari 10 file terbesar di /var/log/ =====
Waktu: Tue Mar  3 02:52:28 PM UTC 2026
----------------------------------------
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:51 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/user-1000.journal
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:51 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/system.journal
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:44 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/system@00064c1fc3e23d83-34e65b7d7dcd7981.journal~
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:43 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/user-1000@00064c1fc56085d2-b9b6a6382bfe9278.journal~
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:31 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/user-1000@574c4553a39641adbdf2d74611897bc8-000000000000065f-00064c1f50d433a3.journal
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:31 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/system@8630a4a9d0da405b848bb0ac2617e9ea-000000000000085a-00064c1f8cacee22.journal
-rw-r-----+ 1 root systemd-journal 8.0M Mar  3 14:28 /var/log/journal/3356d18ad6504b8aa9c4c390b8fb81ee/system@00064c1f8cbf3949-4a0b93280ba61d57.journal~
-rw-r--r-- 1 root root 787K Mar  3 14:32 /var/log/dpkg.log
-rw-r----- 1 syslog adm 415K Mar  3 14:51 /var/log/syslog
-rw-rw-r-- 1 root utmp 286K Mar  3 14:48 /var/log/lastlog
----------------------------------------
Hasil disimpan di: large-logs.txt
Error disimpan di: error.log


## Latihan 3.2

Buat pipeline yang:
1. Membaca /etc/passwd
2. Mengekstrak username (kolom pertama)
3. Mengurutkan alfabetis
4. Menyimpan ke file sorted-users.txt
Hint: Gunakan cut, sort, dan operator redirect.

### Jawaban :    

Kode :  
```bash
dafanr11@Ubuntu-Server-New:~$ cat /etc/passwd | cut -d: -f1 | sort | tee sorted-users.txt
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ cat /etc/passwd | cut -d: -f1 | sort | tee sorted-users.txt
_apt
backup
bin
daemon
dafanr11
dhcpcd
fwupd-refresh
games
irc
landscape
list
lp
mail
man
messagebus
news
nobody
polkitd
pollinate
proxy
root
sshd
sync
sys
syslog
systemd-network
systemd-resolve
systemd-timesync
tcpdump
tss
usbmux
uucp
uuidd
www-data
dafanr11@Ubuntu-Server-New:~$


## Latihan 3.3

Tulis script monitoring yang:
1. Mencatat penggunaan CPU dan memory setiap 5 detik
2. Menyimpan log dengan timestamp
3. Berjalan selama 1 menit (12 iterasi)
4. Output ditampilkan di terminal DAN disimpan ke file

### Jawaban    

Kode :  
```bash
dafanr11@Ubuntu-Server-New:~$ LOGFILE="system-monitor-$(date +%Y%m%d-%H%M%S).log"
ITERATIONS=12
COUNTER=1

echo "===== SYSTEM MONITORING LOG =====" | tee -a "$LOGFILE"
echo "Start time: $(date)" | tee -a "$LOGFILE"
echo "Monitoring setiap 5 detik selama 1 menit" | tee -a "$LOGFILE"
echo "===================================" | tee -a "$LOGFILE"
echo "" | tee -a "$LOGFILE"

while [ $COUNTER -le $ITERATIONS ]; do
    TIMESTAMP=$(date +"%Y-%m-%d %H:%M:%S")

    echo "[$TIMESTAMP] Iterasi ke-$COUNTER" | tee -a "$LOGFILE"
    echo "-----------------------------------" | tee -a "$LOGFILE"

    echo "CPU Usage:" | tee -a "$LOGFILE"
    top -bn1 | grep "Cpu(s)" | tee -a "$LOGFILE"

    echo "Memory Usage:" | tee -a "$LOGFILE"
    free -h | tee -a "$LOGFILE"

    echo "Load Average:" | tee -a "$LOGFILE"
    uptime | tee -a "$LOGFILE"

    echo "" | tee -a "$LOGFILE"

    COUNTER=$((COUNTER + 1))

    if [ $COUNTER -le $ITERATIONS ]; then
        sleep 5
    fi
done

echo "===================================" | tee -a "$LOGFILE"
echo "Monitoring selesai: $(date)" | tee -a "$LOGFILE"
echo "Log disimpan di: $LOGFILE"
```

Output :  
```bash
===== SYSTEM MONITORING LOG =====
Start time: Tue Mar  3 02:56:05 PM UTC 2026
Monitoring setiap 5 detik selama 1 menit
===================================

[2026-03-03 14:56:05] Iterasi ke-1
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  1.8 sy,  0.0 ni, 94.6 id,  1.8 wa,  0.0 hi,  1.8 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       428Mi       3.3Gi       1.0Mi       199Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:05 up 9 min,  2 users,  load average: 0.00, 0.07, 0.08

[2026-03-03 14:56:10] Iterasi ke-2
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       429Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:11 up 9 min,  2 users,  load average: 0.00, 0.07, 0.08

[2026-03-03 14:56:16] Iterasi ke-3
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       432Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:17 up 10 min,  2 users,  load average: 0.00, 0.06, 0.08

[2026-03-03 14:56:22] Iterasi ke-4
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       434Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:23 up 10 min,  2 users,  load average: 0.00, 0.06, 0.08

[2026-03-03 14:56:28] Iterasi ke-5
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.8 id,  0.0 wa,  0.0 hi,  0.2 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       434Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:30 up 10 min,  2 users,  load average: 0.00, 0.06, 0.07

[2026-03-03 14:56:35] Iterasi ke-6
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  2.4 sy,  0.0 ni, 97.6 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       433Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:35 up 10 min,  2 users,  load average: 0.08, 0.08, 0.08

[2026-03-03 14:56:40] Iterasi ke-7
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 98.4 id,  0.0 wa,  0.0 hi,  1.6 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       433Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:41 up 10 min,  2 users,  load average: 0.15, 0.09, 0.09

[2026-03-03 14:56:46] Iterasi ke-8
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       435Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:46 up 10 min,  2 users,  load average: 0.13, 0.09, 0.08

[2026-03-03 14:56:54] Iterasi ke-9
-----------------------------------
CPU Usage:
%Cpu(s):  0.9 us,  0.9 sy,  0.0 ni, 98.2 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       433Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:56:55 up 10 min,  2 users,  load average: 0.12, 0.09, 0.08

[2026-03-03 14:57:00] Iterasi ke-10
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 99.1 id,  0.0 wa,  0.0 hi,  0.9 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       432Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:57:00 up 10 min,  2 users,  load average: 0.11, 0.09, 0.08

[2026-03-03 14:57:06] Iterasi ke-11
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       431Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:57:07 up 10 min,  2 users,  load average: 0.17, 0.10, 0.09

[2026-03-03 14:57:12] Iterasi ke-12
-----------------------------------
CPU Usage:
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni, 98.9 id,  0.0 wa,  0.0 hi,  1.1 si,  0.0 st
Memory Usage:
               total        used        free      shared  buff/cache   available
Mem:           3.7Gi       430Mi       3.3Gi       1.0Mi       200Mi       3.3Gi
Swap:             0B          0B          0B
Load Average:
 14:57:12 up 11 min,  2 users,  load average: 0.15, 0.10, 0.09

===================================
Monitoring selesai: Tue Mar  3 02:57:12 PM UTC 2026
Log disimpan di: system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$
```



## Latihan 3.4
Buat perintah yang:
1. Mencari semua file .conf di sistem
2. Membuang pesan "Permission denied"
3. Menghitung jumlah file yang ditemukan
4. Menyimpan daftar path lengkap ke file

### Jawaban :

Kode :  
```bash
dafanr11@Ubuntu-Server-New:~$ find / -name "*.conf" 2> /dev/null | tee all-config-files.txt | wc -l
```
Output :  
```bash
394
dafanr11@Ubuntu-Server-New:~$
```


## Latihan 3.5

Implementasikan script backup yang:
1. Menggunakan tar untuk backup direktori
2. Menampilkan progress dengan tee
3. Mencatat stdout ke backup-success.log
4. Mencatat stderr ke backup-error.log
5. Menambahkan timestamp di setiap log entry

### Jawaban :  

Kode :  
```bash
tar -cvf backup.tar praktikum-os 2> backup-error.log | while read line; do echo "$(date '+%F %T') $line"; done | tee backup-success.log
```
Output :  
```bash
2026-03-01 03:54:41 praktikum-os/
2026-03-01 03:54:41 praktikum-os/week03/
2026-03-01 03:54:41 praktikum-os/week03/backup-error.log
2026-03-01 03:54:41 praktikum-os/week03/backup-success.l
2026-03-01 03:54:41 praktikum-os/week03/backup-success.log
2026-03-01 03:54:41 praktikum-os/week03/backup.tar
2026-03-01 03:54:41 praktikum-os/week02/
2026-03-01 03:54:41 praktikum-os/week02/server.log
2026-03-01 03:54:41 praktikum-os/week02/data.log
2026-03-01 03:54:41 praktikum-os/week02/server1.log
2026-03-01 03:54:41 praktikum-os/week02/config.txt
2026-03-01 03:54:41 praktikum-os/week02/server1.log.bak
2026-03-01 03:54:41 praktikum-os/week02/server.log.bak
2026-03-01 03:54:41 praktikum-os/week02/notes.txt
```