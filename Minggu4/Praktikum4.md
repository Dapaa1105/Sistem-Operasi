# Laporan Praktikum 4

<h4>Nama : Dafa Naufal R<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## TUGAS PENDAHULUAN

Jawablah pertanyaan-pertanyaan di bawah ini :

1. Apa yang dimaksud perintah-perintah direktory : pwd, cd, mkdir, rmdir.

2. Apa yang dimaksud perintah-perintah manipulasi file : cp, mv dan rm (sertakan format yang digunakan)

3. Jelaskan perbedaan Symbolic link menggunakan hard link (direct) dan soft link (indirect).

4. Tuliskan maksud perintah-perintah : file, find, which, locate dan grep.

Jawaban : 

1. Perintah-perintah direktori: pwd, cd, mkdir, rmdir

    * pwd (Print Working Directory) : Perintah untuk menampilkan lokasi direktori kerja saat ini di sistem file.

    * cd (Change Directory) : Perintah untuk berpindah dari satu direktori ke direktori lain.

    * mkdir (Make Directory) : Perintah untuk membuat direktori (folder) baru.

    * rmdir (Remove directory) : Perintah untuk menghapus direktori yang masih kosong.

2. Perintah manipulasi file : cp, mv, rm (beserta format)
    * cp (copy) : Digunakan untuk menyalin file atau direktori.  
    Format : cp [sumber] [tujuan]  
    Contoh : cp file1.txt file2.txt  

    * mv (move) : Digunakan untuk memindahkan file/direktori atau mengganti nama file.  
    Format : mv [sumber] [tujuan]  
    Contoh : mv file1.txt /home/user/  

    * rm (remove) : Digunakan untuk menghapus file atau direktori.
    Format : rm [nama_file]   
    Contoh : rm file1.txt  
    Untuk menghapus direktori beserta isinya: rm -r nama_direktori  

3. Perbedaan hard link dan soft link (symbolic link)  

* Hard link :

    * Merupakan salinan langsung dari file asli pada level inode

    * Jika file asli dihapus, hard link masih bisa mengakses data

    * Tidak bisa dibuat untuk direktori (umumnya)

    * Harus berada pada filesystem yang sama

* Soft link (symbolic link) :

    * Merupakan file khusus yang berisi path ke file asli

    * Jika file asli dihapus, soft link akan rusak

    * Bisa dibuat untuk file maupun direktori

    * Bisa berada di filesystem berbeda

4. Maksud perintah: file, find, which, locate, grep
* file : Digunakan untuk mengetahui tipe atau jenis suatu file.  
Contoh : file nama_file  

* find : Digunakan untuk mencari file atau direktori berdasarkan nama, ukuran, tipe, dll dalam suatu direktori.  
Contoh : find /home -name file.txt  

* which : Digunakan untuk mengetahui lokasi file executable dari suatu perintah.  
Contoh : which python

* locate : Digunakan untuk mencari file dengan cepat menggunakan database yang sudah diindeks.  
Contoh : locate file.txt.

* grep (Global Regular Expression Print) : Digunakan untuk mencari teks atau pola tertentu dalam file.  
Contoh : grep "kata" nama_file



## LATIHAN

### 1. Cobalah urutan perintah berikut :
```bash
$ cd
$ pwd
$ ls –al
$ cd .
$ pwd
$ cd ..
$ pwd
$ ls -al
$ cd ..
$ pwd
$ ls -al
$ cd /etc
$ ls –al | more
$ cat passwd
$ cd –
$ pwd
```


output  
```bash
dafanr11@Ubuntu-Server-New:~$ mkdir -p ~/Sistem-Operasi/Minggu4
dafanr11@Ubuntu-Server-New:~$ cd ~/Sistem-Operasi/Minggu4
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu4$ pwd
/home/dafanr11/Sistem-Operasi/Minggu4
dafanr11@Ubuntu-Server-New:~/Sistem-Operasi/Minggu4$ cd
dafanr11@Ubuntu-Server-New:~$ pwd
/home/dafanr11
dafanr11@Ubuntu-Server-New:~$ ls -al
total 96
drwxr-x--- 6 dafanr11 dafanr11  4096 Mar  4 03:37 .
drwxr-xr-x 3 root     root      4096 Mar  3 14:12 ..
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw------- 1 dafanr11 dafanr11  1860 Mar  4 03:49 .bash_history
-rw-r--r-- 1 dafanr11 dafanr11   220 Mar 31  2024 .bash_logout
-rw-r--r-- 1 dafanr11 dafanr11  3771 Mar 31  2024 .bashrc
drwx------ 2 dafanr11 dafanr11  4096 Mar  3 14:14 .cache
drwxrwxr-x 4 dafanr11 dafanr11  4096 Mar  3 14:56 .config
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
-rw-r--r-- 1 dafanr11 dafanr11   807 Mar 31  2024 .profile
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
drwx------ 2 dafanr11 dafanr11  4096 Mar  3 14:13 .ssh
-rw-r--r-- 1 dafanr11 dafanr11     0 Mar  3 14:14 .sudo_as_admin_successful
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$ cd .
dafanr11@Ubuntu-Server-New:~$ pwd
/home/dafanr11
dafanr11@Ubuntu-Server-New:~$ cd ..
dafanr11@Ubuntu-Server-New:/home$ pwd
/home
dafanr11@Ubuntu-Server-New:/home$ ls -al
total 12
drwxr-xr-x  3 root     root     4096 Mar  3 14:12 .
drwxr-xr-x 24 root     root     4096 Mar  4 03:42 ..
drwxr-x---  6 dafanr11 dafanr11 4096 Mar  4 03:37 dafanr11
dafanr11@Ubuntu-Server-New:/home$ cd ..
dafanr11@Ubuntu-Server-New:/$ pwd
/
dafanr11@Ubuntu-Server-New:/$ ls -al
total 92
drwxr-xr-x  24 root root  4096 Mar  4 03:42 .
drwxr-xr-x  24 root root  4096 Mar  4 03:42 ..
lrwxrwxrwx   1 root root     7 Apr 22  2024 bin -> usr/bin
drwxr-xr-x   2 root root  4096 Feb 26  2024 bin.usr-is-merged
drwxr-xr-x   3 root root  4096 Mar  3 14:18 boot
dr-xr-xr-x   2 root root  4096 Mar  3 13:51 cdrom
drwxr-xr-x  19 root root  4040 Mar 10 13:24 dev
drwxr-xr-x 112 root root  4096 Mar  3 14:32 etc
drwxr-xr-x   3 root root  4096 Mar  3 14:12 home
lrwxrwxrwx   1 root root     7 Apr 22  2024 lib -> usr/lib
lrwxrwxrwx   1 root root     9 Apr 22  2024 lib64 -> usr/lib64
drwxr-xr-x   2 root root  4096 Feb 26  2024 lib.usr-is-merged
drwx------   2 root root 16384 Mar  3 13:52 lost+found
drwxr-xr-x   2 root root  4096 Aug  5  2025 media
drwxr-xr-x   2 root root  4096 Aug  5  2025 mnt
drwxr-xr-x   2 root root  4096 Aug  5  2025 opt
dr-xr-xr-x 202 root root     0 Mar 10 13:24 proc
drwx------   3 root root  4096 Mar  3 14:34 root
drwxr-xr-x  28 root root   860 Mar 10 13:42 run
lrwxrwxrwx   1 root root     8 Apr 22  2024 sbin -> usr/sbin
drwxr-xr-x   2 root root  4096 Dec 11  2024 sbin.usr-is-merged
drwxr-xr-x   2 root root  4096 Mar  4 03:42 Sistem-Operasi
drwxr-xr-x   2 root root  4096 Mar  3 14:12 snap
drwxr-xr-x   2 root root  4096 Aug  5  2025 srv
dr-xr-xr-x  13 root root     0 Mar 10 13:24 sys
drwxrwxrwt  14 root root  4096 Mar 10 13:35 tmp
drwxr-xr-x  12 root root  4096 Aug  5  2025 usr
drwxr-xr-x  13 root root  4096 Mar  3 14:12 var
dafanr11@Ubuntu-Server-New:/$ cd /etc
dafanr11@Ubuntu-Server-New:/etc$ ls -al | more
total 960
drwxr-xr-x 112 root root       4096 Mar  3 14:32 .
drwxr-xr-x  24 root root       4096 Mar  4 03:42 ..
-rw-r--r--   1 root root       3444 Jul  5  2023 adduser.conf
drwxr-xr-x   2 root root       4096 Mar  3 14:20 alternatives
drwxr-xr-x   2 root root       4096 Mar  3 14:18 apparmor
drwxr-xr-x   9 root root      12288 Mar  3 14:18 apparmor.d
drwxr-xr-x   3 root root       4096 Aug  5  2025 apport
drwxr-xr-x   9 root root       4096 Mar  3 13:52 apt
-rw-r--r--   1 root root       2319 Mar 31  2024 bash.bashrc
-rw-r--r--   1 root root         45 Aug  5  2025 bash_completion
drwxr-xr-x   2 root root       4096 Aug  5  2025 bash_completion.d
-rw-r--r--   1 root root        367 Aug  2  2022 bindresvport.blacklist
drwxr-xr-x   2 root root       4096 Jul  2  2025 binfmt.d
drwxr-xr-x   2 root root       4096 Aug  5  2025 byobu
drwxr-xr-x   3 root root       4096 Aug  5  2025 ca-certificates
-rw-r--r--   1 root root       6288 Aug  5  2025 ca-certificates.conf
drwxr-xr-x   5 root root       4096 Mar  3 14:18 cloud
drwxr-xr-x   2 root root       4096 Mar  3 13:53 console-setup
drwx------   2 root root       4096 Jul  2  2025 credstore
drwx------   2 root root       4096 Jul  2  2025 credstore.encrypted
drwxr-xr-x   2 root root       4096 Aug  5  2025 cron.d
drwxr-xr-x   2 root root       4096 Mar  3 14:12 cron.daily
drwxr-xr-x   2 root root       4096 Aug  5  2025 cron.hourly
drwxr-xr-x   2 root root       4096 Aug  5  2025 cron.monthly
-rw-r--r--   1 root root       1136 Aug  5  2025 crontab
drwxr-xr-x   2 root root       4096 Aug  5  2025 cron.weekly
drwxr-xr-x   2 root root       4096 Aug  5  2025 cron.yearly
drwxr-xr-x   2 root root       4096 Aug  5  2025 cryptsetup-initramfs
-rw-r--r--   1 root root         54 Aug  5  2025 crypttab
drwxr-xr-x   4 root root       4096 Aug  5  2025 dbus-1
-rw-r--r--   1 root root       2967 Apr 12  2024 debconf.conf
-rw-r--r--   1 root root         11 Apr 22  2024 debian_version
drwxr-xr-x   3 root root       4096 Mar  3 14:32 default
-rw-r--r--   1 root root       1706 Jul  5  2023 deluser.conf
drwxr-xr-x   2 root root       4096 Aug  5  2025 depmod.d
drwxr-xr-x   3 root root       4096 Aug  5  2025 dhcp
-rw-r--r--   1 root root       1429 May  7  2024 dhcpcd.conf
drwxr-xr-x   4 root root       4096 Mar  3 14:12 dpkg
-rw-r--r--   1 root root        685 Apr  8  2024 e2scrub.conf
-rw-r--r--   1 root root        106 Aug  5  2025 environment
-rw-r--r--   1 root root       1853 Oct 17  2022 ethertypes
drwxr-xr-x   4 root root       4096 Mar  3 14:11 fonts
-rw-r--r--   1 root root        446 Mar  3 14:11 fstab
-rw-r--r--   1 root root        694 Apr  8  2024 fuse.conf
drwxr-xr-x   4 root root       4096 Mar  3 14:18 fwupd
-rw-r--r--   1 root root       2584 Jan 31  2024 gai.conf
drwxr-xr-x   4 root root       4096 Mar  3 14:20 ghostscript
drwxr-xr-x   2 root root       4096 Mar  3 14:12 gnutls
drwxr-xr-x   2 root root       4096 Aug  5  2025 groff
-rw-r--r--   1 root root        781 Mar  3 14:12 group
-rw-r--r--   1 root root        773 Mar  3 14:12 group-
drwxr-xr-x   2 root root       4096 Mar  3 14:18 grub.d
-rw-r-----   1 root shadow      658 Mar  3 14:12 gshadow
-rw-r-----   1 root shadow      650 Mar  3 14:12 gshadow-
drwxr-xr-x   3 root root       4096 Aug  5  2025 gss
-rw-r--r--   1 root root       4436 Aug  5  2025 hdparm.conf
-rw-r--r--   1 root root         92 Apr 22  2024 host.conf
-rw-r--r--   1 root root         18 Mar  3 14:12 hostname
-rw-r--r--   1 root root          0 Aug  5  2025 hosts
-rw-r--r--   1 root root        411 Mar  3 14:32 hosts.allow
-rw-r--r--   1 root root        711 Mar  3 14:32 hosts.deny
drwxr-xr-x   2 root root       4096 Mar  3 14:20 ImageMagick-6
drwxr-xr-x   2 root root       4096 Mar  3 14:32 init.d
drwxr-xr-x   5 root root       4096 Mar  3 14:18 initramfs-tools
-rw-r--r--   1 root root       1875 Mar 31  2024 inputrc
drwxr-xr-x   4 root root       4096 Aug  5  2025 iproute2
drwxr-xr-x   2 root root       4096 Aug  5  2025 iscsi
-rw-r--r--   1 root root         26 Feb  6 07:23 issue
-rw-r--r--   1 root root         19 Feb  6 07:23 issue.net
drwxr-xr-x   6 root root       4096 Mar  3 14:11 kernel
drwxrwxr-x   2 root landscape  4096 Aug  5  2025 landscape
drwxr-xr-x   2 root root       4096 Mar  3 14:18 ldap
-rw-r--r--   1 root root      32431 Mar  3 14:32 ld.so.cache
-rw-r--r--   1 root root         34 Aug  2  2022 ld.so.conf
drwxr-xr-x   2 root root       4096 Mar  3 14:11 ld.so.conf.d
-rw-r--r--   1 root root        267 Apr 22  2024 legal
-rw-r--r--   1 root root        191 Mar 31  2024 libaudit.conf
drwxr-xr-x   3 root root       4096 Aug  5  2025 libblockdev
drwxr-xr-x   2 root root       4096 Aug  5  2025 libibverbs.d
drwxr-xr-x   2 root root       4096 Aug  5  2025 libnl-3
dafanr11@Ubuntu-Server-New:/etc$ cat passwd
root:x:0:0:root:/root:/bin/bash
daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin
bin:x:2:2:bin:/bin:/usr/sbin/nologin
sys:x:3:3:sys:/dev:/usr/sbin/nologin
sync:x:4:65534:sync:/bin:/bin/sync
games:x:5:60:games:/usr/games:/usr/sbin/nologin
man:x:6:12:man:/var/cache/man:/usr/sbin/nologin
lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin
mail:x:8:8:mail:/var/mail:/usr/sbin/nologin
news:x:9:9:news:/var/spool/news:/usr/sbin/nologin
uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin
proxy:x:13:13:proxy:/bin:/usr/sbin/nologin
www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin
backup:x:34:34:backup:/var/backups:/usr/sbin/nologin
list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin
irc:x:39:39:ircd:/run/ircd:/usr/sbin/nologin
_apt:x:42:65534::/nonexistent:/usr/sbin/nologin
nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin
systemd-network:x:998:998:systemd Network Management:/:/usr/sbin/nologin
systemd-timesync:x:997:997:systemd Time Synchronization:/:/usr/sbin/nologin
dhcpcd:x:100:65534:DHCP Client Daemon,,,:/usr/lib/dhcpcd:/bin/false
messagebus:x:101:102::/nonexistent:/usr/sbin/nologin
systemd-resolve:x:992:992:systemd Resolver:/:/usr/sbin/nologin
pollinate:x:102:1::/var/cache/pollinate:/bin/false
polkitd:x:991:991:User for polkitd:/:/usr/sbin/nologin
syslog:x:103:104::/nonexistent:/usr/sbin/nologin
uuidd:x:104:105::/run/uuidd:/usr/sbin/nologin
tcpdump:x:105:107::/nonexistent:/usr/sbin/nologin
tss:x:106:108:TPM software stack,,,:/var/lib/tpm:/bin/false
landscape:x:107:109::/var/lib/landscape:/usr/sbin/nologin
fwupd-refresh:x:989:989:Firmware update daemon:/var/lib/fwupd:/usr/sbin/nologin
usbmux:x:108:46:usbmux daemon,,,:/var/lib/usbmux:/usr/sbin/nologin
dafanr11:x:1000:1000:dafanr11:/home/dafanr11:/bin/bash
sshd:x:109:65534::/run/sshd:/usr/sbin/nologin
dafanr11@Ubuntu-Server-New:/etc$ cd -
/
dafanr11@Ubuntu-Server-New:/$ pwd
/
dafanr11@Ubuntu-Server-New:/$
```

### 2. Lanjutkan penelusuran pohon pada sistem file menggunakan cd, ls, pwd dan cat. Telusuri direktory /bin, /usr/bin, /sbin, /tmp dan /boot.

/bin : 
```bash
dafanr11@Ubuntu-Server-New:/$ cd /bin
dafanr11@Ubuntu-Server-New:/bin$ pwd
/bin
dafanr11@Ubuntu-Server-New:/bin$ ls -l | head -15
total 132692
-rwxr-xr-x 1 root root       55744 Jun 22  2025 [
-rwxr-xr-x 1 root root       14640 Mar 31  2024 411toppm
-rwxr-xr-x 1 root root       18744 Aug 15  2025 aa-enabled
-rwxr-xr-x 1 root root       18744 Aug 15  2025 aa-exec
-rwxr-xr-x 1 root root       18736 Aug 15  2025 aa-features-abi
-rwxr-xr-x 1 root root        1622 Feb  6 17:52 acpidbg
-rwxr-xr-x 1 root root       16422 Jul  2  2025 add-apt-repository
-rwxr-xr-x 1 root root       14720 Sep 16 00:08 addpart
lrwxrwxrwx 1 root root          25 Mar 31  2024 animate -> /etc/alternatives/animate
lrwxrwxrwx 1 root root          29 Mar 31  2024 animate-im6 -> /etc/alternatives/animate-im6
-rwxr-xr-x 1 root root       14656 Mar 31  2024 animate-im6.q16
-rwxr-xr-x 1 root root       12556 Mar 31  2024 anytopnm
-rwxr-xr-x 1 root root        2322 Apr 18  2024 apport-bug
-rwxr-xr-x 1 root root       13625 Jul  8  2025 apport-cli
dafanr11@Ubuntu-Server-New:/bin$
```

/usr/bin : 
```bash
dafanr11@Ubuntu-Server-New:/bin$ cd /usr/bin
dafanr11@Ubuntu-Server-New:/usr/bin$ pwd
/usr/bin
dafanr11@Ubuntu-Server-New:/usr/bin$ ls -l | head -15
total 132692
-rwxr-xr-x 1 root root       55744 Jun 22  2025 [
-rwxr-xr-x 1 root root       14640 Mar 31  2024 411toppm
-rwxr-xr-x 1 root root       18744 Aug 15  2025 aa-enabled
-rwxr-xr-x 1 root root       18744 Aug 15  2025 aa-exec
-rwxr-xr-x 1 root root       18736 Aug 15  2025 aa-features-abi
-rwxr-xr-x 1 root root        1622 Feb  6 17:52 acpidbg
-rwxr-xr-x 1 root root       16422 Jul  2  2025 add-apt-repository
-rwxr-xr-x 1 root root       14720 Sep 16 00:08 addpart
lrwxrwxrwx 1 root root          25 Mar 31  2024 animate -> /etc/alternatives/animate
lrwxrwxrwx 1 root root          29 Mar 31  2024 animate-im6 -> /etc/alternatives/animate-im6
-rwxr-xr-x 1 root root       14656 Mar 31  2024 animate-im6.q16
-rwxr-xr-x 1 root root       12556 Mar 31  2024 anytopnm
-rwxr-xr-x 1 root root        2322 Apr 18  2024 apport-bug
-rwxr-xr-x 1 root root       13625 Jul  8  2025 apport-cli
dafanr11@Ubuntu-Server-New:/usr/bin$
```

/sbin : 
```bash
dafanr11@Ubuntu-Server-New:/usr/bin$ cd /sbin
dafanr11@Ubuntu-Server-New:/sbin$ pwd
/sbin
dafanr11@Ubuntu-Server-New:/sbin$ ls -l | head -15
total 33140
-rwxr-xr-x 1 root root     39680 Aug 15  2025 aa-load
-rwxr-xr-x 1 root root      3225 Aug 15  2025 aa-remove-unknown
-rwxr-xr-x 1 root root     40000 Aug 15  2025 aa-status
-rwxr-xr-x 1 root root       137 Apr 12  2024 aa-teardown
-rwxr-xr-x 1 root root     14904 Aug  5  2025 accessdb
-rwxr-xr-x 1 root root      3075 Jan  5 22:01 addgnupghome
lrwxrwxrwx 1 root root         7 Jul  5  2023 addgroup -> adduser
-rwxr-xr-x 1 root root      1053 Mar 31  2024 add-shell
-rwxr-xr-x 1 root root     55191 Jul  5  2023 adduser
-rwxr-xr-x 1 root root     60992 Sep 16 00:08 agetty
-rwxr-xr-x 1 root root   1629848 Aug 15  2025 apparmor_parser
lrwxrwxrwx 1 root root         9 Aug 15  2025 apparmor_status -> aa-status
-rwxr-xr-x 1 root root      2217 Jan  5 22:01 applygnupgdefaults
-rwxr-xr-x 1 root root     36862 Apr 16  2024 argdist-bpfcc
dafanr11@Ubuntu-Server-New:/sbin$
```

/tmp : 
```bash
dafanr11@Ubuntu-Server-New:/sbin$ cd /tmp
dafanr11@Ubuntu-Server-New:/tmp$ pwd
/tmp
dafanr11@Ubuntu-Server-New:/tmp$ ls -l | head -15
total 32
drwx------ 2 root root 4096 Mar 10 13:24 snap-private-tmp
drwx------ 3 root root 4096 Mar 10 13:35 systemd-private-9a8b283a04df44f388e00d09cbf4b196-fwupd.service-EII6QA
drwx------ 3 root root 4096 Mar 10 13:24 systemd-private-9a8b283a04df44f388e00d09cbf4b196-ModemManager.service-Ed027v
drwx------ 3 root root 4096 Mar 10 13:24 systemd-private-9a8b283a04df44f388e00d09cbf4b196-polkit.service-8w3HI7
drwx------ 3 root root 4096 Mar 10 13:24 systemd-private-9a8b283a04df44f388e00d09cbf4b196-systemd-logind.service-lFT0NA
drwx------ 3 root root 4096 Mar 10 13:24 systemd-private-9a8b283a04df44f388e00d09cbf4b196-systemd-resolved.service-ZtbqWJ
drwx------ 3 root root 4096 Mar 10 13:24 systemd-private-9a8b283a04df44f388e00d09cbf4b196-systemd-timesyncd.service-Ooq1RD
drwx------ 3 root root 4096 Mar 10 13:35 systemd-private-9a8b283a04df44f388e00d09cbf4b196-upower.service-sroBrt
dafanr11@Ubuntu-Server-New:/tmp$
```

/boot : 
```bash
dafanr11@Ubuntu-Server-New:/tmp$ cd /boot
dafanr11@Ubuntu-Server-New:/boot$ pwd
/boot
dafanr11@Ubuntu-Server-New:/boot$ ls -l | head -15
total 96776
-rw-r--r-- 1 root root   287599 Feb  6 17:52 config-6.8.0-101-generic
drwxr-xr-x 5 root root     4096 Mar  3 14:11 grub
lrwxrwxrwx 1 root root       28 Mar  3 14:11 initrd.img -> initrd.img-6.8.0-101-generic
-rw-r--r-- 1 root root 74646767 Mar  3 14:18 initrd.img-6.8.0-101-generic
lrwxrwxrwx 1 root root       28 Mar  3 14:11 initrd.img.old -> initrd.img-6.8.0-101-generic
-rw------- 1 root root  9120274 Feb  6 17:52 System.map-6.8.0-101-generic
lrwxrwxrwx 1 root root       25 Mar  3 14:11 vmlinuz -> vmlinuz-6.8.0-101-generic
-rw------- 1 root root 15030664 Feb  6 18:21 vmlinuz-6.8.0-101-generic
lrwxrwxrwx 1 root root       25 Mar  3 14:11 vmlinuz.old -> vmlinuz-6.8.0-101-generic
dafanr11@Ubuntu-Server-New:/boot$
```

### 3. Telusuri direktory /dev. Identifikasi perangkat yang tersedia. Identifikasi tty  (termninal) Anda (ketik who am i); siapa pemilih tty Anda (gunakan ls –l).

Output
```bash
dafanr11@Ubuntu-Server-New:/boot$ cd /dev
dafanr11@Ubuntu-Server-New:/dev$ ls -l | head -15
total 0
crw-r--r--  1 root     root     10, 235 Mar 10 13:24 autofs
drwxr-xr-x  2 root     root         280 Mar 10 13:24 block
drwxr-xr-x  2 root     root          80 Mar 10 13:24 bsg
crw-rw----  1 root     disk     10, 234 Mar 10 13:24 btrfs-control
drwxr-xr-x  3 root     root          60 Mar 10 13:24 bus
lrwxrwxrwx  1 root     root           3 Mar 10 13:24 cdrom -> sr0
drwxr-xr-x  2 root     root        3760 Mar 10 13:24 char
crw-------  1 root     root      5,   1 Mar 10 13:24 console
lrwxrwxrwx  1 root     root          11 Mar 10 13:24 core -> /proc/kcore
drwxr-xr-x  6 root     root         120 Mar 10 13:24 cpu
crw-------  1 root     root     10, 123 Mar 10 13:24 cpu_dma_latency
crw-------  1 root     root     10, 203 Mar 10 13:24 cuse
drwxr-xr-x  7 root     root         140 Mar 10 13:24 disk
drwxr-xr-x  2 root     root          60 Mar 10 13:24 dma_heap
dafanr11@Ubuntu-Server-New:/dev$
```

### 4. Telusuri derectory /proc. Tampilkan isi file interrupts, devices, cpuinfo, meminfo dan uptime menggunakan perintah cat. Dapatkah Anda melihat mengapa directory /proc disebut pseudo -filesystem yang memungkinkan akses ke struktur data kernel ?
 
>Direktori /proc disebut sebagai pseudo-filesystem karena merupakan sistem file virtual yang tidak menyimpan data secara fisik di hard disk, melainkan dibuat secara dinamis oleh kernel Linux di dalam memori saat sistem sedang berjalan. Isi dari direktori ini berfungsi untuk menyediakan berbagai informasi penting mengenai kondisi sistem, seperti informasi proses yang sedang berjalan, penggunaan CPU dan memori, konfigurasi kernel, serta perangkat keras yang digunakan. Dengan adanya /proc, pengguna maupun administrator sistem dapat mengakses dan memantau struktur data internal kernel melalui antarmuka yang menyerupai file biasa. Oleh karena itu, /proc menjadi mekanisme penting yang memungkinkan komunikasi antara kernel dan pengguna untuk melihat maupun mengelola informasi sistem secara langsung.
Output

```bash
dafanr11@Ubuntu-Server-New:/dev$ cd /proc
dafanr11@Ubuntu-Server-New:/proc$ cat interrupts
           CPU0       CPU1       CPU2       CPU3
  0:        129          0          0          0   IO-APIC   2-edge      timer
  1:          0          0          0         47   IO-APIC   1-edge      i8042
  8:          0          0          0          0   IO-APIC   8-edge      rtc0
  9:          0          0          0          0   IO-APIC   9-fasteoi   acpi
 12:          0        158          0          0   IO-APIC  12-edge      i8042
 14:          0          0       1942          0   IO-APIC  14-edge      ata_piix
 15:          0          0          0          0   IO-APIC  15-edge      ata_piix
 18:          0          0          0          0   IO-APIC  18-fasteoi   vmwgfx
 19:          0          0      19122          0   IO-APIC  19-fasteoi   ehci_hcd:usb2, enp0s3
 20:          0          0          0          0   IO-APIC  20-fasteoi   vboxguest
 21:          0       7127          0          0   IO-APIC  21-fasteoi   ahci[0000:00:0d.0], snd_intel8x0
 22:         26          0          0          0   IO-APIC  22-fasteoi   ohci_hcd:usb1
NMI:          0          0          0          0   Non-maskable interrupts
LOC:      14058      28507     258824      23896   Local timer interrupts
SPU:          0          0          0          0   Spurious interrupts
PMI:          0          0          0          0   Performance monitoring interrupts
IWI:          2         53          4          5   IRQ work interrupts
RTR:          0          0          0          0   APIC ICR read retries
RES:        662        669        308        778   Rescheduling interrupts
CAL:      14816      12339       7356       7472   Function call interrupts
TLB:         37         23         53         30   TLB shootdowns
TRM:          0          0          0          0   Thermal event interrupts
THR:          0          0          0          0   Threshold APIC interrupts
DFR:          0          0          0          0   Deferred Error APIC interrupts
MCE:          0          0          0          0   Machine check exceptions
MCP:          7          7          7          7   Machine check polls
ERR:          0
MIS:          0
PIN:          0          0          0          0   Posted-interrupt notification event
NPI:          0          0          0          0   Nested posted-interrupt event
PIW:          0          0          0          0   Posted-interrupt wakeup event
dafanr11@Ubuntu-Server-New:/proc$ cat devices
Character devices:
  1 mem
  4 /dev/vc/0
  4 tty
  4 ttyS
  5 /dev/tty
  5 /dev/console
  5 /dev/ptmx
  5 ttyprintk
  7 vcs
 10 misc
 13 input
 21 sg
 29 fb
 89 i2c
108 ppp
116 alsa
128 ptm
136 pts
180 usb
189 usb_device
202 cpu/msr
204 ttyMAX
226 drm
241 hidraw
242 ttyDBC
243 bsg
244 watchdog
245 remoteproc
246 ptp
247 pps
248 rtc
249 dma_heap
250 dax
251 dimmctl
252 ndctl
253 tpm
254 gpiochip
261 accel

Block devices:
  7 loop
  8 sd
  9 md
 11 sr
 65 sd
 66 sd
 67 sd
 68 sd
 69 sd
 70 sd
 71 sd
128 sd
129 sd
130 sd
131 sd
132 sd
133 sd
134 sd
135 sd
252 device-mapper
253 virtblk
254 mdp
259 blkext
dafanr11@Ubuntu-Server-New:/proc$ cat meminfo
MemTotal:        3910944 kB
MemFree:         3356308 kB
MemAvailable:    3455548 kB
Buffers:           21400 kB
Cached:           279184 kB
SwapCached:            0 kB
Active:           268392 kB
Inactive:          73232 kB
Active(anon):      50860 kB
Inactive(anon):        0 kB
Active(file):     217532 kB
Inactive(file):    73232 kB
Unevictable:       27316 kB
Mlocked:           27316 kB
SwapTotal:             0 kB
SwapFree:              0 kB
Zswap:                 0 kB
Zswapped:              0 kB
Dirty:                 0 kB
Writeback:             0 kB
AnonPages:         68428 kB
Mapped:            82316 kB
Shmem:              1068 kB
KReclaimable:      21376 kB
Slab:              72496 kB
SReclaimable:      21376 kB
SUnreclaim:        51120 kB
KernelStack:        2720 kB
PageTables:         2884 kB
SecPageTables:         0 kB
NFS_Unstable:          0 kB
Bounce:                0 kB
WritebackTmp:          0 kB
CommitLimit:     1955472 kB
Committed_AS:     470240 kB
VmallocTotal:   34359738367 kB
VmallocUsed:       19520 kB
VmallocChunk:          0 kB
Percpu:             2000 kB
HardwareCorrupted:     0 kB
AnonHugePages:         0 kB
ShmemHugePages:        0 kB
ShmemPmdMapped:        0 kB
FileHugePages:         0 kB
FilePmdMapped:         0 kB
Unaccepted:            0 kB
HugePages_Total:       0
HugePages_Free:        0
HugePages_Rsvd:        0
HugePages_Surp:        0
Hugepagesize:       2048 kB
Hugetlb:               0 kB
DirectMap4k:      118720 kB
DirectMap2M:     3977216 kB
dafanr11@Ubuntu-Server-New:/proc$ cat uptime
2258.04 8868.08
dafanr11@Ubuntu-Server-New:/proc$
```


### 5. Ubahlah direktory home ke user lain secara langsung menggunakan cd ~username.

Output 
```bash
dafanr11@Ubuntu-Server-New:/proc$ cd ~dafanr11
dafanr11@Ubuntu-Server-New:~$
```  

### 6. Ubah kembali ke direktory home Anda

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ cd
dafanr11@Ubuntu-Server-New:~$ pwd
/home/dafanr11
dafanr11@Ubuntu-Server-New:~$
```

### 7. Buat subdirektory work dan play.

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ mkdir work play
dafanr11@Ubuntu-Server-New:~$ ls -l
total 68
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:10 play
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:10 work
dafanr11@Ubuntu-Server-New:~$
```

### 8. Hapus subdirektory work.

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ rmdir work
dafanr11@Ubuntu-Server-New:~$ ls -l
total 64
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:10 play
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$
```

### 9. Copy file /etc/passwd ke direktory home Anda.

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ cp /etc/passwd .
dafanr11@Ubuntu-Server-New:~$ ls -l
total 68
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
-rw-r--r-- 1 dafanr11 dafanr11  1789 Mar 10 14:12 passwd
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:10 play
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$
```

### 10. Pindahkan ke subdirektory play

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ mv passwd play/
dafanr11@Ubuntu-Server-New:~$ ls -l play
total 4
-rw-r--r-- 1 dafanr11 dafanr11 1789 Mar 10 14:12 passwd
dafanr11@Ubuntu-Server-New:~$
```

### 11. Ubahlah ke subdirektory play dan buat symbolic link dengan nama terminal yang menunjuk ke perangkat tty. Apa yang terjadi jika melakukan hard link ke perangkat tty ?

>Jika mencoba membuat hard link ke perangkat tty, sistem akan menolak perintah tersebut dan biasanya menampilkan pesan error. Hal ini terjadi karena hard link tidak diizinkan untuk file device, bahkan jika perintah dijalankan oleh root, demi menjaga keamanan dan stabilitas sistem.

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ cd play
dafanr11@Ubuntu-Server-New:~/play$ pwd
/home/dafanr11/play
dafanr11@Ubuntu-Server-New:~/play$ who am i
dafanr11 pts/0        2026-03-10 13:29 (10.0.2.2)
dafanr11@Ubuntu-Server-New:~/play$ ln -s /dev/pts/2 terminal
dafanr11@Ubuntu-Server-New:~/play$ ls -l
total 4
-rw-r--r-- 1 dafanr11 dafanr11 1789 Mar 10 14:12 passwd
lrwxrwxrwx 1 dafanr11 dafanr11   10 Mar 10 14:16 terminal -> /dev/pts/2
dafanr11@Ubuntu-Server-New:~/play$ ln /dev/pts/0 hardtty
ln: failed to create hard link 'hardtty' => '/dev/pts/0': Invalid cross-device link
dafanr11@Ubuntu-Server-New:~/play$
```
 

### 12. Buatlah file bernama hello.txt yang berisi kata ”hello word”. Dapatkah Anda gunakan ”cp” menggunakan ”terminal” sebagai file asal untuk menghasilkan efek yang sama ?

>Tidak. Perintah cp dengan terminal (/dev/tty) sebagai sumber tidak dapat secara langsung menghasilkan efek yang sama seperti menyalin file hello.txt, karena terminal hanya memberikan input dari pengguna, bukan membaca isi file yang sudah ada.

Output 
```bash
dafanr11@Ubuntu-Server-New:~/play$ echo "hello word" > hello.txt
dafanr11@Ubuntu-Server-New:~/play$ cat hello.txt
hello word
dafanr11@Ubuntu-Server-New:~/play$
```

### 13. Copy hello.txt ke terminal. Apa yang terjadi ?

>Tidak ada file baru, hanya output ke terminal.

Output 
```bash
dafanr11@Ubuntu-Server-New:~/play$ cp hello.txt /dev/pts/0
hello word
dafanr11@Ubuntu-Server-New:~/play$
```

### 14. Masih direktory home, copy keseluruhan direktory play ke direktory bernama work menggunakan symbolic link

Output 
```bash
dafanr11@Ubuntu-Server-New:~/play$ cd ..
dafanr11@Ubuntu-Server-New:~$ pwd
/home/dafanr11
dafanr11@Ubuntu-Server-New:~$ ln -s play work
dafanr11@Ubuntu-Server-New:~$ ls -l
total 64
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:17 play
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
lrwxrwxrwx 1 dafanr11 dafanr11     4 Mar 10 14:26 work -> play
dafanr11@Ubuntu-Server-New:~$
```

### 15. Hapus direktory work dan isinya dengan satu perintah

Output 
```bash
dafanr11@Ubuntu-Server-New:~$ rm -rf work
dafanr11@Ubuntu-Server-New:~$ ls -l
total 64
-rw-rw-r-- 1 dafanr11 dafanr11 16433 Mar  3 14:58 all-config-files.txt
-rw-rw-r-- 1 dafanr11 dafanr11     0 Mar  4 03:46 backup-error.log
-rw-rw-r-- 1 dafanr11 dafanr11   124 Mar  4 03:46 backup-success.log
-rw-rw-r-- 1 dafanr11 dafanr11 10240 Mar  4 03:46 backup.tar
-rw-rw-r-- 1 dafanr11 dafanr11   158 Mar  3 14:52 error.log
-rw-rw-r-- 1 dafanr11 dafanr11  1249 Mar  3 14:52 large-logs.txt
drwxrwxr-x 2 dafanr11 dafanr11  4096 Mar 10 14:17 play
drwxrwxr-x 5 dafanr11 dafanr11  4096 Mar 10 13:41 Sistem-Operasi
-rw-rw-r-- 1 dafanr11 dafanr11   251 Mar  3 14:53 sorted-users.txt
-rw-rw-r-- 1 dafanr11 dafanr11  5789 Mar  3 14:57 system-monitor-20260303-145605.log
dafanr11@Ubuntu-Server-New:~$
```


## LAPORAN RESMI

### 1. Analisis Hasil Percobaan

### Percobaan 1: Direktory

### a. Analisis Setiap Hasil Tampilan   

* $ pwd  
Menampilkan direktori aktif saat ini, yaitu /home/user (home user).

* $ echo $HOME  
Menampilkan variabel lingkungan HOME yang berisi path home user, sama dengan hasil pwd.

* $ cd .  
Perintah cd . berpindah ke direktori saat ini (titik berarti direktori sendiri). Tidak ada perubahan direktori.

* $ pwd  
Masih /home/user.

* $ cd ..  
Berpindah ke parent direktori, yaitu /home.

* $ pwd  
Menampilkan /home.

* $ cd  
Tanpa argumen, cd kembali ke home user, yaitu /home/user.

* $ mkdir A B C A/D A/E B/F A/D/A  
Perintah ini membuat struktur direktori:

    * A, B, C di level pertama.

    * Di dalam A dibuat D dan E.

    * Di dalam B dibuat F.

    * Di dalam A/D dibuat A.
    Tidak ada output jika berhasil.

* $ ls -l  
Menampilkan daftar direktori A, B, C beserta atributnya.

* $ ls -l A  
Menampilkan isi direktori A, yaitu D dan E.

* $ ls -l A/D  
Menampilkan isi A/D, yaitu subdirektori A.

* $ rmdir B   
Mencoba menghapus direktori B. Error: rmdir: failed to remove 'B': Directory not empty karena B masih berisi subdirektori F.

* $ ls -l B  
Menampilkan isi B, yaitu F.

* $ rmdir B/F B  
Perintah ini menghapus B/F terlebih dahulu, kemudian B. Setelah B/F dihapus, B menjadi kosong sehingga rmdir B berhasil. Tidak ada output.

* $ ls -l B  
Error: ls: cannot access 'B': No such file or directory karena B sudah dihapus.

* Navigasi dengan cd:

    * $ cd A → pindah ke A, pwd menjadi /home/user/A.

    * $ cd . → tetap di A.

    * $ cd /home/user/C → pindah ke C dengan path absolut, berhasil jika C ada.

    * $ cd /user/C → Error: bash: cd: /user/C: No such file or directory karena path yang benar adalah /home/user/C, bukan /user/C.

### b. Pohon Struktur File dan Direktori (Percobaan 1 point 3)  

Berdasarkan perintah mkdir A B C A/D A/E B/F A/D/A, struktur direktori yang terbentuk adalah:
```bash
/home/user/
├── A
│   ├── D
│   │   └── A
│   └── E
├── B
│   └── F
└── C
```

### c. Penjelasan Pesan Error

* rmdir B error karena direktori tidak kosong. rmdir hanya dapat menghapus direktori kosong. Untuk menghapus direktori berisi, harus menggunakan rm -r.

* ls -l B setelah dihapus error karena direktori sudah tidak ada.

* cd /user/C error karena path absolut salah. Root (/) tidak memiliki direktori user; yang benar adalah /home/user/C.


### Percobaan 2: Manipulasi File

### a. Analisis Hasil Tampilan

* $ cat > contoh  
Membuat file contoh dengan input keyboard. Akhiri dengan Ctrl+D.

* $ cp contoh contoh1  
Menyalin contoh menjadi contoh1.

* $ ls -l  
Menampilkan kedua file.

* $ cp contoh A  
Menyalin contoh ke dalam direktori A (menjadi A/contoh).

* $ ls -l A  
Isi A sekarang ada file contoh dan subdirektori D, E.

* $ cp contoh contoh1 A/D  
Menyalin dua file ke dalam A/D.

* $ ls -l A/D  
Di A/D sekarang terdapat file contoh, contoh1, dan subdirektori A.

* $ mv contoh contoh2  
Memindahkan (rename) contoh menjadi contoh2.

* $ ls -l  
File contoh hilang, muncul contoh2.

* $ mv contoh1 contoh2 A/D  
Memindahkan contoh1 dan contoh2 ke dalam direktori A/D.

* $ ls -l A/D  
Di A/D sekarang terdapat file contoh, contoh1, contoh2, dan subdirektori A.

* $ mv contoh contoh1 C  
Error: mv: cannot stat 'contoh': No such file or directory (mungkin salah satu atau kedua file sudah tidak ada karena sudah dipindah ke A/D).

* $ ls -l C  
Direktori C kosong.

* $ rm contoh2  
Error: rm: cannot remove 'contoh2': No such file or directory karena file sudah dipindah.

* $ ls -l  
Hanya tersisa direktori A dan C.

* $ rm -i contoh  
Error: file tidak ada.

* $ rm -rf A C   
Menghapus seluruh direktori A dan C beserta isinya. Perintah -rf memaksa penghapusan rekursif tanpa konfirmasi.


### Percobaan 3 : Symbolic Link

### a. Analisis Hasil Tampilan

* $ echo "Hallo apa khabar" > halo.txt  
Membuat file teks.

* $ ls -l  
File halo.txt muncul.

* $ ln halo.txt z  
Membuat hard link z ke halo.txt.

* $ ls -l  
Dua file dengan ukuran sama dan link count menjadi 2 (kolom ketiga).

* $ cat z  
Menampilkan isi yang sama.

* $ mkdir mydir  
Membuat direktori.

* $ ln z mydir/halo.juga  
Membuat hard link lain di dalam mydir.

* $ cat mydir/halo.juga  
Isi sama.

* $ ln -s z bye.txt  
Membuat soft link bye.txt yang menunjuk ke z.

* $ ls -l bye.txt  
Menampilkan bye.txt -> z.

* $ cat bye.txt  
Membaca isi bye.txt (mengikuti link) dan menampilkan teks.

### Percobaan 4: Melihat Isi File

### a. Analisis Hasil Tampilan

* $ file halo.txt → output: halo.txt: ASCII text

* $ file bye.txt → output: bye.txt: symbolic link to z

### Percobaan 5: Mencari File

### a. Analisis Hasil Tampilan

*  $ find /home -name "*.txt" -print > myerror.txt  
Mencari semua file .txt di bawah /home, hasil disimpan ke myerror.txt.

* $ cat myerror.txt  
Menampilkan daftar file yang ditemukan.

* $ find . -name "*.txt" -exec wc -l '{}' ';'  
Menghitung jumlah baris setiap file .txt di direktori saat ini.

* $ which ls  
Menampilkan lokasi program ls, misal /bin/ls.

* $ locate "*.txt"  
Mencari semua file .txt menggunakan database locate.

### Percobaan 6: Mencari Teks pada File

### a. Analisis Hasil Tampilan

* $ grep Hallo *.txt  
Mencari kata "Hallo" di semua file .txt. Output menampilkan baris yang mengandung kata tersebut beserta nama file.



### Analisis Hasil Latihan

### Latihan 1: Urutan Perintah Navigasi

* $cd → pindah ke home.

* pwd → /home/user.

* ls -al → menampilkan semua file termasuk yang tersembunyi.

* cd . → tetap.

* pwd → /home/user.

* cd .. → pindah ke /home.

* pwd → /home.

* ls -al → menampilkan isi /home (direktori user).

* cd .. → pindah ke root (/).

* pwd → /.

* ls -al → menampilkan isi root.

* cd /etc → pindah ke /etc.

* ls -al | more → menampilkan isi /etc per halaman.

* cat passwd → menampilkan isi file /etc/passwd.

* cd - → kembali ke direktori sebelumnya, yaitu /.

* pwd → /.

### Latihan 2: Penelusuran Direktori Sistem

* /bin → berisi perintah dasar (binary) untuk semua user.

* /usr/bin → berisi lebih banyak perintah dan aplikasi.

* /sbin → berisi perintah untuk administrasi sistem (biasanya hanya root).

* /tmp → direktori sementara, dapat diakses semua user.

* /boot → berisi file boot seperti kernel dan initrd.

Semua direktori ditelusuri dengan cd, ls, dan cat untuk file teks (misal config di /boot).

### Latihan 3: Direktori /dev dan Terminal

* ls -l /dev menampilkan banyak file device.

* who am i menunjukkan terminal yang digunakan, misal pts/0.

* ls -l /dev/pts/0 menunjukkan pemilik terminal adalah user yang login (misal ubuntuser) dan group tty.

### Latihan 4: Direktori /proc

* cat /proc/interrupts, devices, cpuinfo, meminfo, uptime menampilkan informasi kernel.

* /proc disebut pseudo-filesystem karena file-file di dalamnya tidak tersimpan di disk, melainkan dibuat dinamis oleh kernel saat diakses.

### Latihan 5: cd ~username

* Jika user lain ada dan diizinkan, pindah ke home-nya. Biasanya user biasa tidak bisa karena izin, hanya root yang bisa.

### Latihan 6: cd kembali ke home sendiri.

### Latihan 7–8: Membuat dan menghapus direktori work dan play.

### Latihan 9–10: Menyalin /etc/passwd ke home lalu memindah ke play.

### Latihan 11: Symbolic link ke terminal

* ln -s /dev/pts/0 terminal berhasil.

* Hard link ke device gagal karena device file tidak mendukung hard link (berbeda filesystem dan tipe khusus).

### Latihan 12–13: File hello.txt

* cp terminal hello2.txt tidak menghasilkan efek sama karena membaca input.

* cp hello.txt /dev/pts/0 mencetak isi file ke layar.

### Latihan 14: Membuat symbolic link work ke play

* ln -s play work membuat link, bukan copy.

### Latihan 15: Menghapus link work

* rm -rf work hanya menghapus link, bukan direktori play.


### 3. Kesimpulan

Berdasarkan praktikum yang telah dilakukan, dapat disimpulkan bahwa sistem operasi Linux memiliki struktur direktori yang tersusun secara hirarkis seperti pohon (tree) yang dimulai dari root (/). Pengguna dapat melakukan navigasi dan pengelolaan direktori menggunakan perintah seperti pwd, cd, mkdir, dan rmdir, serta melakukan manipulasi file menggunakan cp, mv, dan rm.
Selain itu, praktikum ini juga memperkenalkan konsep hard link dan symbolic link, serta penggunaan perintah seperti file, find, which, locate, dan grep untuk melihat informasi file dan mencari file atau teks di dalam sistem. Secara umum, praktikum ini membantu memahami dasar pengelolaan file dan direktori pada sistem operasi Linux.