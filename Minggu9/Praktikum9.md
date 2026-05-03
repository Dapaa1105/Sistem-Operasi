# Laporan Praktikum 9

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## PRAKTIKUM

## Praktikum 7.1 Script Pertama: Laporan Sistem

### Langkah 1
Input : 
```bash
mkdir -p ~/Sistem-Operasi/Minggu9/{scripts,logs,data}
cd ~/Sistem-Operasi/Minggu9/scripts
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~$ mkdir -p ~/Sistem-Operasi/Minggu9/{scripts,logs,data}
dafanr11@Ubuntu-Server-New:~$ cd ~/Sistem-Operasi/Minggu9/scripts
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

### Langkah 2
Input : 
```bash
nano laporan-sistem.sh
```

### Langkah 3
Input : 
```bash
#!/bin/bash

# Script: laporan-sistem.sh

echo "==========================================="
echo "          LAPORAN SISTEM"
echo "==========================================="
echo "Tanggal   : $(date '+%A, %d %B %Y')"
echo "Jam       : $(date '+%H:%M:%S')"
echo "Hostname  : $(hostname)"
echo "User      : $(whoami)"
echo "CPU core  : $(nproc)"
echo "RAM bebas : $(free -h | awk '/^Mem/ {print $4}')"
echo "Disk /    : $(df -h / | awk 'NR==2 {print $5}')  terpakai"
echo "==========================================="
```
Output :
```bash
GNU nano 7.2                                                          laporan-sistem.sh
#!/bin/bash
# Script : laporan-sistem.sh

echo "================================"
echo "LAPORAN SISTEM"
echo "================================"
echo "Tanggal : $(date '+%A, %d %B %Y')"
echo "Jam : $(date '+%H:%M:%S')"
echo "Hostname : $(hostname)"
echo "User : $(whoami)"
echo "CPU core : $(nproc)"
echo "RAM bebas : $(free -h | awk '/^Mem/ {print $4}')"
echo "Disk / : $(df -h / | awk 'NR==2 {print $5}') terpakai"
echo "================================"























                                                                     [ Wrote 14 lines ]
^G Help          ^O Write Out     ^W Where Is      ^K Cut           ^T Execute       ^C Location      M-U Undo         M-A Set Mark     M-] To Bracket
^X Exit          ^R Read File     ^\ Replace       ^U Paste         ^J Justify       ^/ Go To Line    M-E Redo         M-6 Copy         ^Q Where Was
```

### Langkah 4
Input : 
```bash
chmod +x laporan-sistem.sh
./laporan-sistem.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ nano laporan-sistem.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x laporan-sistem.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./laporan-sistem.sh
================================
LAPORAN SISTEM
================================
Tanggal : Tuesday, 28 April 2026
Jam : 11:19:54
Hostname : Ubuntu-Server-New
User : dafanr11
CPU core : 4
RAM bebas : 3.2Gi
Disk / : 15% terpakai
================================
```

## Latihan 9.1

### Langkah 1
Input : 
```bash
cd ~/Sistem-Operasi/Minggu9/scripts
nano laporan-sistem.sh
```
Output :
```bash
 GNU nano 7.2                                                          laporan-sistem.sh
#!/bin/bash
# Script : laporan-sistem.sh

echo "================================"
echo "LAPORAN SISTEM"
echo "================================"
echo "Tanggal : $(date '+%A, %d %B %Y')"
echo "Jam : $(date '+%H:%M:%S')"
echo "Hostname : $(hostname)"
echo "User : $(whoami)"
echo "CPU core : $(nproc)"
echo "RAM bebas : $(free -h | awk '/^Mem/ {print $4}')"
echo "Disk / : $(df -h / | awk 'NR==2 {print $5}') terpakai"
echo "================================"























                                                                     [ Read 14 lines ]
^G Help          ^O Write Out     ^W Where Is      ^K Cut           ^T Execute       ^C Location      M-U Undo         M-A Set Mark     M-] To Bracket
^X Exit          ^R Read File     ^\ Replace       ^U Paste         ^J Justify       ^/ Go To Line    M-E Redo         M-6 Copy         ^Q Where Was
```

## Praktikum 9.2 Script Info Sistem dengan Argumen

### Langkah 1
Input : 
```bash
nano info-sistem.sh
```


### Langkah 2
Input : 
```bash
#!/bin/bash
# Penggunaan : ./info-sistem.sh [nama-admin] [batas-disk-persen]

ADMIN=${1:-"Tidak dikenal"}
BATAS=${2:-80}

TANGGAL=$(date '+%F %T')

DISK_PERSEN=$(df / | awk 'NR==2 {print $5}' | tr -d '%')

echo "Admin : $ADMIN"
echo "Tanggal : $TANGGAL"
echo "Disk / : ${DISK_PERSEN}% terpakai"
echo "Batas : ${BATAS}%"

if [ "$DISK_PERSEN" -gt "$BATAS" ]; then
echo "STATUS : PERINGATAN - disk melebihi batas!"
else
SISA=$(( BATAS - DISK_PERSEN ))
echo "STATUS : Normal (sisa toleransi ${SISA}%)"
fi
```
Output :
```bash
GNU nano 7.2                                                           info-sistem.sh
#!/bin/bash
# Penggunaan : ./info-sistem.sh [nama-admin] [batas-disk-persen]

ADMIN=${1:-"Tidak dikenal"}
BATAS=${2:-80}

TANGGAL=$(date '+%F %T')

DISK_PERSEN=$(df / | awk 'NR==2 {print $5}' | tr -d '%')

echo "Admin : $ADMIN"
echo "Tanggal : $TANGGAL"
echo "Disk / : ${DISK_PERSEN}% terpakai"
echo "Batas : ${BATAS}%"

if [ "$DISK_PERSEN" -gt "$BATAS" ]; then
echo "STATUS : PERINGATAN - disk melebihi batas!"
else
SISA=$(( BATAS - DISK_PERSEN ))
echo "STATUS : Normal (sisa toleransi ${SISA}%)"
fi
















                                                                     [ Wrote 21 lines ]
^G Help          ^O Write Out     ^W Where Is      ^K Cut           ^T Execute       ^C Location      M-U Undo         M-A Set Mark     M-] To Bracket
^X Exit          ^R Read File     ^\ Replace       ^U Paste         ^J Justify       ^/ Go To Line    M-E Redo         M-6 Copy         ^Q Where Was
```

### Langkah 3
Input : 
```bash
chmod +x ~/Sistem-Operasi/Minggu9/scripts/info-sistem.sh
./info-sistem.sh
./info-sistem.sh " Dafa " 50
./info-sistem.sh " Dafa " 10
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x ~/Sistem-Operasi/Minggu9/scripts/info-sistem.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./info-sistem.sh
Admin : Tidak dikenal
Tanggal : 2026-04-28 11:31:24
Disk / : 15% terpakai
Batas : 80%
STATUS : Normal (sisa toleransi 65%)
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./info-sistem.sh " Dafa " 50
Admin :  Dafa
Tanggal : 2026-04-28 11:31:30
Disk / : 15% terpakai
Batas : 50%
STATUS : Normal (sisa toleransi 35%)
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./info-sistem.sh " Dafa " 10
Admin :  Dafa
Tanggal : 2026-04-28 11:31:36
Disk / : 15% terpakai
Batas : 10%
STATUS : PERINGATAN - disk melebihi batas!
```

## Latihan 9.2

### Langkah 1
Input : 
```bash
cd ~/Sistem-Operasi/Minggu9/scripts
nano kalkulator.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: kalkulator.sh
# Penggunaan: ./kalkulator.sh <angka1> <operator> <angka2>
# Operator: +, -, *, /

# Validasi jumlah argumen
if [ $# -ne 3 ]; then
    echo "ERROR: Argumen tidak lengkap."
    echo "Penggunaan: $0 <angka1> <operator> <angka2>"
    echo "Operator: +, -, *, /"
    exit 1
fi

ANGKA1=$1
OPERATOR=$2
ANGKA2=$3

# Validasi bahwa angka1 dan angka2 adalah bilangan bulat (opsional, tapi baik)
if ! [[ "$ANGKA1" =~ ^-?[0-9]+$ ]] || ! [[ "$ANGKA2" =~ ^-?[0-9]+$ ]]; then
    echo "ERROR: Angka harus bilangan bulat."
    exit 1
fi

# Case untuk operator
case $OPERATOR in
    +)
        HASIL=$((ANGKA1 + ANGKA2))
        ;;
    -)
        HASIL=$((ANGKA1 - ANGKA2))
        ;;
    '*')   # Bintang perlu dikutip atau di-escape
        HASIL=$((ANGKA1 * ANGKA2))
        ;;
    /)
        if [ "$ANGKA2" -eq 0 ]; then
            echo "ERROR: Pembagian dengan nol tidak diperbolehkan."
            exit 1
        fi
        HASIL=$((ANGKA1 / ANGKA2))
        ;;
    *)
        echo "ERROR: Operator '$OPERATOR' tidak dikenal. Gunakan +, -, *, /"
        exit 1
        ;;
esac

echo "Hasil: $ANGKA1 $OPERATOR $ANGKA2 = $HASIL"
```

### Langkah 3
Input : 
```bash
chmod +x kalkulator.sh
./kalkulator.sh 20 + 5
./kalkulator.sh 20 - 5
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x kalkulator.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./kalkulator.sh 20 + 5
Hasil: 20 + 5 = 25
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./kalkulator.sh 20 - 5
Hasil: 20 - 5 = 15
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

## Praktikum 9.3 Script Grading dan Menu Interaktif

### Langkah 1
Input : 
```bash
cd ~/Sistem-Operasi/Minggu9/scripts
nano grading-batch.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: grading-batch.sh
# Proses daftar nilai mahasiswa

MAHASISWA=("Andi:92" "Budi:73" "Citra:55" "Deni:80" "Eka:45")

echo "=== HASIL GRADING ==="
for ENTRY in "${MAHASISWA[@]}"; do
    NAMA=$(echo "$ENTRY" | cut -d: -f1)
    NILAI=$(echo "$ENTRY" | cut -d: -f2)
    
    if [ "$NILAI" -ge 85 ]; then
        GRADE="A"
    elif [ "$NILAI" -ge 75 ]; then
        GRADE="B"
    elif [ "$NILAI" -ge 65 ]; then
        GRADE="C"
    elif [ "$NILAI" -ge 55 ]; then
        GRADE="D"
    else
        GRADE="E"
    fi
    
    printf "%-10s %3d %s\n" "$NAMA" "$NILAI" "$GRADE"
done
echo "====================="
```
Output :
```bash
  GNU nano 7.2                                                          grading-batch.sh
#!/bin/bash
# Script : grading-batch.sh

# Daftar mahasiswa dan nilai
MAHASISWA=("Andi:92" "Budi:73" "Citra:55" "Deni:80" "Eka:45")

echo "=== HASIL GRADING ==="

for ENTRI in "${MAHASISWA[@]}"; do

NAMA=$(echo "$ENTRI" | cut -d: -f1)
NILAI=$(echo "$ENTRI" | cut -d: -f2)

if [ "$NILAI" -ge 85 ]; then
GRADE="A"

elif [ "$NILAI" -ge 75 ]; then
GRADE="B"

elif [ "$NILAI" -ge 65 ]; then
GRADE="C"

elif [ "$NILAI" -ge 55 ]; then
GRADE="D"

else
GRADE="E"

fi

printf "%-10s %3d %s\n" "$NAMA" "$NILAI" "$GRADE"

done

echo "====================="


                                                                     [ Wrote 35 lines ]
^G Help          ^O Write Out     ^W Where Is      ^K Cut           ^T Execute       ^C Location      M-U Undo         M-A Set Mark     M-] To Bracket
^X Exit          ^R Read File     ^\ Replace       ^U Paste         ^J Justify       ^/ Go To Line    M-E Redo         M-6 Copy         ^Q Where Was
```

### Langkah 3
Input : 
```bash
chmod +x grading-batch.sh
./grading-batch.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x grading-batch.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./grading-batch.sh
=== HASIL GRADING ===
Andi        92 A
Budi        73 C
Citra       55 D
Deni        80 B
Eka         45 E
=====================
```

### Langkah 4
Input : 
```bash
nano menu-sistem.sh
```

### Langkah 5
Input : 
```bash
#!/bin/bash
# Menu interaktif pemantauan sistem

while true; do

echo ""
echo "===== MENU MONITOR ====="
echo "1) Info disk"
echo "2) Info memori"
echo "3) Proses teratas"
echo "4) Keluar"
echo -n "Pilih [1-4]: "

read PILIHAN

case $PILIHAN in

1)
df -h
;;

2)
free -h
;;

3)
ps aux --sort=-%cpu | head -6
;;

4)
echo "Sampai jumpa!"
exit 0
;;

*)
echo "Pilihan tidak valid."
;;

esac

done
```

### Langkah 6   
Input : 
```bash
chmod +x menu-sistem.sh
./menu-sistem.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x menu-sistem.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./menu-sistem.sh

===== MENU MONITOR =====
1) Info disk
2) Info memori
3) Proses teratas
4) Keluar
Pilih [1-4]: 1
Filesystem      Size  Used Avail Use% Mounted on
tmpfs           382M  1.1M  381M   1% /run
/dev/sda2        25G  3.5G   20G  15% /
tmpfs           1.9G     0  1.9G   0% /dev/shm
tmpfs           5.0M     0  5.0M   0% /run/lock
tmpfs           382M   12K  382M   1% /run/user/1000

===== MENU MONITOR =====
1) Info disk
2) Info memori
3) Proses teratas
4) Keluar
Pilih [1-4]: 4
Sampai jumpa!
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

## Latihan 9.3

### Langkah 1
Input : 
```bash
cd ~/Sistem-Operasi/Minggu9/scripts
nano grading-batch.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: grading-batch.sh
# Proses daftar nilai mahasiswa + ringkasan per grade

MAHASISWA=("Andi:92" "Budi:73" "Citra:55" "Deni:80" "Eka:45")

echo "=== HASIL GRADING ==="

# Array untuk menyimpan grade setiap mahasiswa (opsional, bisa langsung hitung)
declare -A COUNTER
COUNTER[A]=0
COUNTER[B]=0
COUNTER[C]=0
COUNTER[D]=0
COUNTER[E]=0

for ENTRY in "${MAHASISWA[@]}"; do
    NAMA=$(echo "$ENTRY" | cut -d: -f1)
    NILAI=$(echo "$ENTRY" | cut -d: -f2)
    
    if [ "$NILAI" -ge 85 ]; then
        GRADE="A"
    elif [ "$NILAI" -ge 75 ]; then
        GRADE="B"
    elif [ "$NILAI" -ge 65 ]; then
        GRADE="C"
    elif [ "$NILAI" -ge 55 ]; then
        GRADE="D"
    else
        GRADE="E"
    fi
    
    printf "%-10s %3d %s\n" "$NAMA" "$NILAI" "$GRADE"
    
    # Increment counter grade
    COUNTER[$GRADE]=$((COUNTER[$GRADE] + 1))
done

echo "====================="
echo ""
echo "=== RINGKASAN PER GRADE ==="

# Perulangan for kedua untuk menampilkan ringkasan
for GRADE in A B C D E; do
    echo "Grade $GRADE : ${COUNTER[$GRADE]} mahasiswa"
done
echo "============================"
```

### Langkah 3
Input : 
```bash
./grading-batch.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ nano grading-batch.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./grading-batch.sh
=== HASIL GRADING ===
Andi        92 A
Budi        73 C
Citra       55 D
Deni        80 B
Eka         45 E
=====================

=== RINGKASAN PER GRADE ===
Grade A : 1 mahasiswa
Grade B : 1 mahasiswa
Grade C : 1 mahasiswa
Grade D : 1 mahasiswa
Grade E : 1 mahasiswa
============================
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

## Praktikum 9.4 Library Fungsi Validasi

### Langkah 1
Input : 
```bash
nano lib-validasi.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# lib-validasi.sh - Library fungsi validasi

adalah_angka() {
[[ "$1" =~ ^[0-9]+$ ]]
}

file_bisa_dibaca() {
[ -f "$1" ] && [ -r "$1" ]
}

error_exit() {
echo "ERROR: $1" >&2
exit 1
}

info() {
echo "[INFO] $1"
}

sukses() {
echo "[OK] $1"
}
```

### Langkah 3
Input : 
```bash
nano pakai-library.sh
```

### Langkah 4
Input : 
```bash
#!/bin/bash

# Load library
source ~/Sistem-Operasi/Minggu9/scripts/lib-validasi.sh

ANGKA=$1
FILE=$2

# Validasi argumen
[ -z "$ANGKA" ] || [ -z "$FILE" ] && \
error_exit "Penggunaan: $0 <angka> <path-file>"

# Cek angka
if adalah_angka "$ANGKA"; then
sukses "Input '$ANGKA' adalah angka valid"
else
error_exit "'$ANGKA' bukan angka"
fi

# Cek file
if file_bisa_dibaca "$FILE"; then
sukses "File '$FILE' bisa dibaca"
info "Jumlah baris: $(wc -l < "$FILE")"
else
error_exit "File '$FILE' tidak ada atau tidak bisa dibaca"
fi
```
### Langkah 5
Input : 
```bash
chmod +x ~/Sistem-Operasi/Minggu9/scripts/pakai-library.sh
./pakai-library.sh 42 /etc/hostname
./pakai-library.sh abc /etc/hostname
./pakai-library.sh 42 /tidak-ada.txt
./pakai-library.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x ~/Sistem-Operasi/Minggu9/scripts/pakai-library.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./pakai-library.sh 42 /etc/hostname
./pakai-library.sh: line 1: !/bin/bash: No such file or directory
[OK] Input '42' adalah angka valid
[OK] File '/etc/hostname' bisa dibaca
[INFO] Jumlah baris: 1
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./pakai-library.sh abc /etc/hostname
./pakai-library.sh: line 1: !/bin/bash: No such file or directory
ERROR: 'abc' bukan angka
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./pakai-library.sh 42 /tidak-ada.txt
./pakai-library.sh: line 1: !/bin/bash: No such file or directory
[OK] Input '42' adalah angka valid
ERROR: File '/tidak-ada.txt' tidak ada atau tidak bisa dibaca
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./pakai-library.sh
./pakai-library.sh: line 1: !/bin/bash: No such file or directory
ERROR: Penggunaan: ./pakai-library.sh <angka> <path-file>
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

## Latihan 9.4

### Langkah 1
Input : 
```bash
nano demo-konfirmasi.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: demo-konfirmasi.sh
# Mendemonstrasikan fungsi konfirmasi sebelum menghapus file

# Muat library
source ~/Sistem-Operasi/Minggu9/scripts/lib-validasi.sh

# Cek argumen
if [ $# -ne 1 ]; then
    echo "Penggunaan: $0 <file-yang-akan-dihapus>"
    exit 1
fi

TARGET_FILE="$1"

# Cek apakah file ada
if [ ! -f "$TARGET_FILE" ]; then
    error_exit "File '$TARGET_FILE' tidak ditemukan."
fi

# Tampilkan info file
echo "File target: $TARGET_FILE"
echo "Ukuran: $(du -h "$TARGET_FILE" | cut -f1)  |  Baris: $(wc -l < "$TARGET_FILE")"

# Minta konfirmasi
if konfirmasi "Apakah Anda yakin ingin menghapus file '$TARGET_FILE'?"; then
    # Jika user menjawab Y (return 0)
    rm "$TARGET_FILE"
    sukses "File '$TARGET_FILE' telah dihapus."
else
    # Jika menjawab selain Y
    info "Penghapusan dibatalkan. File tetap aman."
fi
```

### Langkah 3
Input : 
```bash
chmod +x demo-konfirmasi.sh
echo "Ini adalah file contoh" > ~/Sistem-Operasi/Minggu9/data/contoh.txt
./demo-konfirmasi.sh ~/Sistem-Operasi/Minggu9/data/contoh.txt
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x demo-konfirmasi.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ echo "Ini adalah file contoh" > ~/Sistem-Operasi/Minggu9/data/contoh.txt
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./demo-konfirmasi.sh ~/Sistem-Operasi/Minggu9/data/contoh.txt
File target: /home/dafanr11/Sistem-Operasi/Minggu9/data/contoh.txt
Ukuran: 4.0K  |  Baris: 1
./demo-konfirmasi.sh: line 26: konfirmasi: command not found
[INFO] Penghapusan dibatalkan. File tetap aman.
```

## Praktikum 9.6 Debugging Script

### Langkah 1
Input : 
```bash
nano debug-latihan.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: debug-latihan.sh
# Penggunaan: ./debug-latihan.sh <direktori> <batas-MB>

DIREKTORI=$1
BATAS=$2

if [ $# -ne 2 ]; then
    echo "Penggunaan: $0 <direktori> <batas-MB>"
    exit 1
fi

UKURAN=$(du -sm "$DIREKTORI" | cut -f1)
echo "Direktori : $DIREKTORI"
echo "Ukuran   : ${UKURAN} MB"
echo "Batas    : ${BATAS} MB"

if ["$UKURAN" -gt "$BATAS" ]; then
    echo "PERINGATAN: Ukuran melebihi batas!"
    echo "Kelebihan: $((UKURAN - BATAS)) MB"
else
    echo "Status: Normal (sisa: $((BATAS - UKURAN)) MB)"
fi
```

### Langkah 3
Input : 
```bash
chmod +x ~/Sistem-Operasi/Minggu9/scripts/debug-latihan.sh
bash -n debug-latihan.sh && echo " Sintaks OK"
bash -x debug-latihan.sh / etc 10

```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x ~/Sistem-Operasi/Minggu9/scripts/debug-latihan.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ bash -n debug-latihan.sh && echo " Sintaks OK"
 Sintaks OK
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ bash -x debug-latihan.sh / etc 10
+ DIREKTORI=/
+ BATAS=etc
+ '[' 3 -ne 2 ']'
+ echo 'Penggunaan: debug-latihan.sh <direktori> <batas-MB>'
Penggunaan: debug-latihan.sh <direktori> <batas-MB>
+ exit 1
```

## Latihan 9.5

### Langkah 1
Input : 
```bash
nano debug-latihan.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
set -euo pipefail   # -e: stop on error, -u: undefined var error, -o pipefail: pipeline error

# Script: debug-latihan.sh
# Penggunaan: ./debug-latihan.sh <direktori> <batas-MB>

# Validasi jumlah argumen
if [ $# -ne 2 ]; then
    echo "Penggunaan: $0 <direktori> <batas-MB>"
    exit 1
fi

DIREKTORI=$1
BATAS=$2

# Cek apakah direktori ada
if [ ! -d "$DIREKTORI" ]; then
    echo "ERROR: Direktori '$DIREKTORI' tidak ditemukan atau bukan direktori."
    exit 2
fi

# Dapatkan ukuran dalam MB
UKURAN=$(du -sm "$DIREKTORI" | cut -f1)

echo "Direktori : $DIREKTORI"
echo "Ukuran   : ${UKURAN} MB"
echo "Batas    : ${BATAS} MB"

# Perbandingan dengan spasi yang benar
if [ "$UKURAN" -gt "$BATAS" ]; then
    echo "PERINGATAN: Ukuran melebihi batas!"
    echo "Kelebihan: $((UKURAN - BATAS)) MB"
else
    echo "Status: Normal (sisa: $((BATAS - UKURAN)) MB)"
fi
```

### Langkah 3
Input : 
```bash
./debug-latihan.sh /etc 10
./debug-latihan.sh /tidak-ada 50
bash -x ./debug-latihan.sh /etc 10
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./debug-latihan.sh /etc 10
du: cannot read directory '/etc/multipath': Permission denied
du: cannot read directory '/etc/credstore': Permission denied
du: cannot read directory '/etc/credstore.encrypted': Permission denied
du: cannot read directory '/etc/polkit-1/rules.d': Permission denied
du: cannot read directory '/etc/ssl/private': Permission denied
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./debug-latihan.sh /tidak-ada 50
ERROR: Direktori '/tidak-ada' tidak ditemukan atau bukan direktori.
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ bash -x ./debug-latihan.sh /etc 10
+ set -euo pipefail
+ '[' 2 -ne 2 ']'
+ DIREKTORI=/etc
+ BATAS=10
+ '[' '!' -d /etc ']'
++ cut -f1
++ du -sm /etc
du: cannot read directory '/etc/multipath': Permission denied
du: cannot read directory '/etc/credstore': Permission denied
du: cannot read directory '/etc/credstore.encrypted': Permission denied
du: cannot read directory '/etc/polkit-1/rules.d': Permission denied
du: cannot read directory '/etc/ssl/private': Permission denied
+ UKURAN=7
```

## TUGAS 1

### Langkah 1
Input : 
```bash
nano absensi.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# Script: absensi.sh
# Mencatat kehadiran mahasiswa

# Konfigurasi
LOG_DIR="../logs"
mkdir -p "$LOG_DIR"

# File log harian
TGL=$(date '+%Y-%m-%d')
ABSENSI_FILE="$LOG_DIR/absensi-$TGL.txt"

# Fungsi bantuan
usage() {
    echo "Penggunaan: $0 [OPTIONS] [NAMA] [STATUS]"
    echo ""
    echo "Catat kehadiran:"
    echo "  $0 \"Budi\" hadir"
    echo "  $0 \"Citra\" izin"
    echo "  $0 \"Dewi\" alpha"
    echo ""
    echo "Opsi:"
    echo "  -r      Tampilkan rekapitulasi (jumlah per status)"
    echo "  -h      Tampilkan bantuan ini"
    exit 0
}

# Fungsi rekapitulasi
rekap() {
    if [ ! -f "$ABSENSI_FILE" ]; then
        echo "Belum ada data absensi untuk hari ini."
        exit 0
    fi
    
    echo "=== REKAPITULASI ABSENSI $TGL ==="
    echo "File: $ABSENSI_FILE"
    echo ""
    
    # Inisialisasi counter
    HADIR=0
    IZIN=0
    ALPHA=0
    
    # Baca file dan hitung
    while IFS= read -r line; do
        case "$line" in
            *"- HADIR"*) ((HADIR++)) ;;
            *"- IZIN"*)  ((IZIN++)) ;;
            *"- ALPHA"*) ((ALPHA++)) ;;
        esac
    done < "$ABSENSI_FILE"
    
    echo "HADIR : $HADIR"
    echo "IZIN  : $IZIN"
    echo "ALPHA : $ALPHA"
    echo "TOTAL : $((HADIR + IZIN + ALPHA))"
    echo "================================"
}

# Fungsi catat kehadiran
catat() {
    local NAMA=$1
    local STATUS=$2
    
    # Validasi status
    if [[ "$STATUS" != "hadir" && "$STATUS" != "izin" && "$STATUS" != "alpha" ]]; then
        echo "ERROR: Status harus 'hadir', 'izin', atau 'alpha'"
        exit 1
    fi
    
    # Format waktu [HH:MM]
    JAM=$(date '+%H:%M')
    STATUS_UPPER=$(echo "$STATUS" | tr '[:lower:]' '[:upper:]')
    
    # Tulis ke file
    echo "[$JAM] $NAMA - $STATUS_UPPER" >> "$ABSENSI_FILE"
    echo "✅ Dicatat: $NAMA - $STATUS_UPPER pada jam $JAM"
}

# Proses opsi dengan getopts
MODE="catat"
while getopts "rh" OPT; do
    case $OPT in
        r) MODE="rekap" ;;
        h) usage ;;
        *) usage ;;
    esac
done

# Geser argumen opsi
shift $((OPTIND - 1))

# Eksekusi berdasarkan mode
if [ "$MODE" = "rekap" ]; then
    rekap
else
    # Mode catat: butuh 2 argumen (NAMA STATUS)
    if [ $# -ne 2 ]; then
        echo "ERROR: Untuk mencatat, berikan NAMA dan STATUS."
        usage
    fi
    catat "$1" "$2"
fi
```

### Langkah 3
Input : 
```bash
chmod +x absensi.sh
./absensi.sh "Andi" hadir
./absensi.sh "Budi" hadir
./absensi.sh "Citra" izin
./absensi.sh "Dewi" alpha
./absensi.sh "Eka" hadir
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ nano absensi.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x absensi.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./absensi.sh "Andi" hadir
./absensi.sh "Budi" hadir
./absensi.sh "Citra" izin
./absensi.sh "Dewi" alpha
./absensi.sh "Eka" hadir
✅ Dicatat: Andi - HADIR pada jam 11:59
✅ Dicatat: Budi - HADIR pada jam 11:59
✅ Dicatat: Citra - IZIN pada jam 11:59
✅ Dicatat: Dewi - ALPHA pada jam 11:59
✅ Dicatat: Eka - HADIR pada jam 11:59
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

### Langkah 4
Input : 
```bash
./absensi.sh -r
./absensi.sh -h
cat ../logs/absensi-2026-04-26.txt
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./absensi.sh -r
=== REKAPITULASI ABSENSI 2026-04-28 ===
File: ../logs/absensi-2026-04-28.txt

HADIR : 3
IZIN  : 1
ALPHA : 1
TOTAL : 5
================================
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./absensi.sh -h
Penggunaan: ./absensi.sh [OPTIONS] [NAMA] [STATUS]

Catat kehadiran:
  ./absensi.sh "Budi" hadir
  ./absensi.sh "Citra" izin
  ./absensi.sh "Dewi" alpha

Opsi:
  -r      Tampilkan rekapitulasi (jumlah per status)
  -h      Tampilkan bantuan ini
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ cat ../logs/absensi-2026-04-28.txt
[11:59] Andi - HADIR
[11:59] Budi - HADIR
[11:59] Citra - IZIN
[11:59] Dewi - ALPHA
[11:59] Eka - HADIR
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

## TUGAS 2

### Langkah 1
Input : 
```bash
nano healthcheck.sh
```

### Langkah 2
Input : 
```bash
#!/bin/bash
# ================================================
# Script: healthcheck.sh
# Deskripsi: Memeriksa kesehatan sistem (CPU, memori, disk)
# Penggunaan: ./healthcheck.sh [-t batas] [-h]
# ================================================

set -euo pipefail

SCRIPT_NAME=$(basename "$0")
LOG_DIR="../logs"
mkdir -p "$LOG_DIR"

# Default batas disk (%)
BATAS_DISK=80

# File log harian
TGL=$(date '+%Y-%m-%d')
LOG_FILE="$LOG_DIR/healthcheck-$TGL.log"

usage() {
    echo "Penggunaan: $SCRIPT_NAME [-t batas] [-h]"
    echo "  -t batas   Atur batas peringatan disk (default 80%)"
    echo "  -h         Tampilkan bantuan"
    exit 0
}

log() {
    echo "[$(date '+%F %T')] $*"
}

error_exit() {
    echo "ERROR: $*" >&2
    exit 1
}

cleanup() {
    log "Script healthcheck selesai."
}
trap cleanup EXIT

# Proses opsi getopts
while getopts "t:h" opt; do
    case $opt in
        t)
            if [[ "$OPTARG" =~ ^[0-9]+$ ]] && [ "$OPTARG" -ge 0 ] && [ "$OPTARG" -le 100 ]; then
                BATAS_DISK="$OPTARG"
            else
                error_exit "Batas disk harus angka 0-100"
            fi
            ;;
        h) usage ;;
        *) usage ;;
    esac
done

shift $((OPTIND - 1))

# Mulai healthcheck
{
    echo "==========================================="
    echo "         HEALTH CHECK SISTEM"
    echo "==========================================="
    echo "Tanggal/Waktu : $(date '+%A, %d %B %Y %H:%M:%S')"
    echo "Hostname      : $(hostname)"
    echo "Uptime        : $(uptime -p 2>/dev/null || uptime | awk -F 'up ' '{print $2}' | awk -F ',' '{print $1}')"
    echo ""

    echo "--- CPU ---"
    # Load average dari uptime
    LOAD=$(uptime | awk -F 'load average:' '{print $2}' | xargs)
    echo "Load average : $LOAD"
    # CPU usage (sederhana, bisa pakai top -bn1)
    if command -v mpstat >/dev/null 2>&1; then
        CPU_IDLE=$(mpstat 1 1 | awk '/Average/ && /all/ {print $12}')
        CPU_USED=$(echo "100 - $CPU_IDLE" | bc)
        printf "CPU usage    : %.1f%%\n" "$CPU_USED"
    else
        echo "CPU usage    : (instal sysstat untuk detail)"
    fi
    echo ""

    echo "--- MEMORI ---"
    free -h | awk '/^Mem:/ {print "Total   : " $2; print "Terpakai: " $3; print "Bebas   : " $4}'
    echo ""

    echo "--- DISK (setiap filesystem) ---"
    df -h | grep -E '^/dev/' | while read -r line; do
        FILESYSTEM=$(echo "$line" | awk '{print $1}')
        UKURAN=$(echo "$line" | awk '{print $2}')
        TERPAKAI=$(echo "$line" | awk '{print $3}')
        AVAIL=$(echo "$line" | awk '{print $4}')
        PERSEN=$(echo "$line" | awk '{print $5}' | tr -d '%')
        MOUNT=$(echo "$line" | awk '{print $6}')
        
        printf "Filesystem: %s (%s)\n" "$FILESYSTEM" "$MOUNT"
        printf "  Ukuran : %s, Terpakai: %s (%s%%), Sisa: %s\n" "$UKURAN" "$TERPAKAI" "$PERSEN" "$AVAIL"
        
        if [ "$PERSEN" -gt "$BATAS_DISK" ]; then
            echo "  ⚠️ PERINGATAN: Penggunaan disk melebihi batas $BATAS_DISK%"
        fi
        echo ""
    done

    echo "==========================================="
    echo "Log disimpan di: $LOG_FILE"
} | tee -a "$LOG_FILE"
```

### Langkah 3
Input : 
```bash
chmod +x healthcheck.sh
./healthcheck.sh
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ nano healthcheck.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ chmod +x healthcheck.sh
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./healthcheck.sh
===========================================
         HEALTH CHECK SISTEM
===========================================
Tanggal/Waktu : Tuesday, 28 April 2026 12:02:59
Hostname      : Ubuntu-Server-New
Uptime        : up 1 hour, 24 minutes

--- CPU ---
Load average : 0.01, 0.02, 0.00
CPU usage    : 7.7%

--- MEMORI ---
Total   : 3.7Gi
Terpakai: 432Mi
Bebas   : 3.2Gi

--- DISK (setiap filesystem) ---
Filesystem: /dev/sda2 (/)
  Ukuran : 25G, Terpakai: 3.5G (15%), Sisa: 20G

===========================================
Log disimpan di: ../logs/healthcheck-2026-04-28.log
[2026-04-28 12:03:00] Script healthcheck selesai.
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```

### Langkah 4
Input : 
```bash
./healthcheck.sh -t 30
./healthcheck.sh -h
cat ../logs/healthcheck-2026-04-28.log
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./healthcheck.sh -t 30
===========================================
         HEALTH CHECK SISTEM
===========================================
Tanggal/Waktu : Tuesday, 28 April 2026 12:03:28
Hostname      : Ubuntu-Server-New
Uptime        : up 1 hour, 24 minutes

--- CPU ---
Load average : 0.06, 0.03, 0.00
CPU usage    : 7.5%

--- MEMORI ---
Total   : 3.7Gi
Terpakai: 431Mi
Bebas   : 3.2Gi

--- DISK (setiap filesystem) ---
Filesystem: /dev/sda2 (/)
  Ukuran : 25G, Terpakai: 3.5G (15%), Sisa: 20G

===========================================
Log disimpan di: ../logs/healthcheck-2026-04-28.log
[2026-04-28 12:03:29] Script healthcheck selesai.
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ ./healthcheck.sh -h
Penggunaan: healthcheck.sh [-t batas] [-h]
  -t batas   Atur batas peringatan disk (default 80%)
  -h         Tampilkan bantuan
[2026-04-28 12:03:33] Script healthcheck selesai.
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$ cat ../logs/healthcheck-2026-04-28.log
===========================================
         HEALTH CHECK SISTEM
===========================================
Tanggal/Waktu : Tuesday, 28 April 2026 12:02:59
Hostname      : Ubuntu-Server-New
Uptime        : up 1 hour, 24 minutes

--- CPU ---
Load average : 0.01, 0.02, 0.00
CPU usage    : 7.7%

--- MEMORI ---
Total   : 3.7Gi
Terpakai: 432Mi
Bebas   : 3.2Gi

--- DISK (setiap filesystem) ---
Filesystem: /dev/sda2 (/)
  Ukuran : 25G, Terpakai: 3.5G (15%), Sisa: 20G

===========================================
Log disimpan di: ../logs/healthcheck-2026-04-28.log
===========================================
         HEALTH CHECK SISTEM
===========================================
Tanggal/Waktu : Tuesday, 28 April 2026 12:03:28
Hostname      : Ubuntu-Server-New
Uptime        : up 1 hour, 24 minutes

--- CPU ---
Load average : 0.06, 0.03, 0.00
CPU usage    : 7.5%

--- MEMORI ---
Total   : 3.7Gi
Terpakai: 431Mi
Bebas   : 3.2Gi

--- DISK (setiap filesystem) ---
Filesystem: /dev/sda2 (/)
  Ukuran : 25G, Terpakai: 3.5G (15%), Sisa: 20G

===========================================
Log disimpan di: ../logs/healthcheck-2026-04-28.log
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu9/scripts$
```