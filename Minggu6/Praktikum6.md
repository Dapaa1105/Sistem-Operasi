# Laporan Praktikum 6

<h4>Nama : Dafa Naufal Rabbani<h4>
<h4>Nim : 254107020086<h4>
<h4>Kelas : TI-1G<h4>

## Praktikum 6.1 — Melihat Proses dan Thread

1. Tampilkan semua proses yang berjalan:
```bash
ps aux
```
Output  :
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1  0.4  0.3  22028 13096 ?        Ss   14:12   0:00 /sbin/init splash noprompt noshell automatic-ubiquity
root           2  0.0  0.0      0     0 ?        S    14:12   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        S    14:12   0:00 [pool_workqueue_release]
root           4  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-rcu_g]
root           5  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-rcu_p]
root           6  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-slub_]
root           7  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-netns]
root           8  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/0:0-events]
root           9  0.4  0.0      0     0 ?        I    14:12   0:01 [kworker/0:1-events]
root          10  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/0:0H-events_highpri]
root          11  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u8:0-ipv6_addrconf]
root          12  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-mm_pe]
root          13  0.0  0.0      0     0 ?        I    14:12   0:00 [rcu_tasks_kthread]
root          14  0.0  0.0      0     0 ?        I    14:12   0:00 [rcu_tasks_rude_kthread]
root          15  0.0  0.0      0     0 ?        I    14:12   0:00 [rcu_tasks_trace_kthread]
root          16  0.0  0.0      0     0 ?        S    14:12   0:00 [ksoftirqd/0]
root          17  0.0  0.0      0     0 ?        I    14:12   0:00 [rcu_preempt]
root          18  0.0  0.0      0     0 ?        S    14:12   0:00 [migration/0]
root          19  0.0  0.0      0     0 ?        S    14:12   0:00 [idle_inject/0]
root          20  0.0  0.0      0     0 ?        S    14:12   0:00 [cpuhp/0]
root          21  0.0  0.0      0     0 ?        S    14:12   0:00 [cpuhp/1]
root          22  0.0  0.0      0     0 ?        S    14:12   0:00 [idle_inject/1]
root          23  0.1  0.0      0     0 ?        S    14:12   0:00 [migration/1]
root          24  0.0  0.0      0     0 ?        S    14:12   0:00 [ksoftirqd/1]
root          25  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/1:0-events]
root          26  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/1:0H-events_highpri]
root          27  0.0  0.0      0     0 ?        S    14:12   0:00 [cpuhp/2]
root          28  0.0  0.0      0     0 ?        S    14:12   0:00 [idle_inject/2]
root          29  0.1  0.0      0     0 ?        S    14:12   0:00 [migration/2]
root          30  0.0  0.0      0     0 ?        S    14:12   0:00 [ksoftirqd/2]
root          31  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/2:0-events]
root          32  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/2:0H-kblockd]
root          33  0.0  0.0      0     0 ?        S    14:12   0:00 [cpuhp/3]
root          34  0.0  0.0      0     0 ?        S    14:12   0:00 [idle_inject/3]
root          35  0.1  0.0      0     0 ?        S    14:12   0:00 [migration/3]
root          36  0.2  0.0      0     0 ?        S    14:12   0:00 [ksoftirqd/3]
root          37  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/3:0-events]
root          38  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/3:0H-kblockd]
root          39  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u9:0-flush-8:0]
root          40  0.1  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:0-events_power_efficient]
root          41  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u11:0-flush-8:0]
root          42  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u12:0-events_unbound]
root          43  0.0  0.0      0     0 ?        S    14:12   0:00 [kdevtmpfs]
root          44  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-inet_]
root          45  0.0  0.0      0     0 ?        S    14:12   0:00 [kauditd]
root          46  0.0  0.0      0     0 ?        S    14:12   0:00 [khungtaskd]
root          47  0.0  0.0      0     0 ?        S    14:12   0:00 [oom_reaper]
root          48  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u9:1-events_power_efficient]
root          49  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-write]
root          50  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u9:2-events_freezable_power_]
root          51  0.0  0.0      0     0 ?        S    14:12   0:00 [kcompactd0]
root          52  0.0  0.0      0     0 ?        SN   14:12   0:00 [ksmd]
root          53  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/1:1-events]
root          54  0.0  0.0      0     0 ?        SN   14:12   0:00 [khugepaged]
root          55  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-kinte]
root          56  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-kbloc]
root          57  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-blkcg]
root          58  0.0  0.0      0     0 ?        S    14:12   0:00 [irq/9-acpi]
root          59  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-tpm_d]
root          60  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-ata_s]
root          61  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-md]
root          62  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-md_bi]
root          63  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-edac-]
root          64  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-devfr]
root          65  0.0  0.0      0     0 ?        S    14:12   0:00 [watchdogd]
root          66  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/3:1-cgroup_destroy]
root          67  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:1-events_power_efficient]
root          68  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/1:1H-kblockd]
root          69  0.0  0.0      0     0 ?        S    14:12   0:00 [kswapd0]
root          70  0.0  0.0      0     0 ?        S    14:12   0:00 [ecryptfs-kthread]
root          71  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-kthro]
root          72  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-acpi_]
root          73  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:2-events_unbound]
root          74  0.0  0.0      0     0 ?        S    14:12   0:00 [scsi_eh_0]
root          75  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-scsi_]
root          76  0.0  0.0      0     0 ?        S    14:12   0:00 [scsi_eh_1]
root          77  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-scsi_]
root          78  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:3-events_unbound]
root          79  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:4-events_power_efficient]
root          80  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u10:5]
root          81  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-mld]
root          82  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-ipv6_]
root          84  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u8:1-ipv6_addrconf]
root          85  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/1:2-cgroup_destroy]
root          86  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/2:1H-kblockd]
root          88  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/2:1-cgroup_destroy]
root          93  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-kstrp]
root          94  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/3:1H-kblockd]
root          96  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/u13:0]
root          97  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/u14:0]
root          98  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/u15:0]
root          99  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/u16:0]
root         100  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/u17:0]
root         101  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u11:1-flush-8:0]
root         106  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-crypt]
root         107  0.4  0.0      0     0 ?        I    14:12   0:01 [kworker/3:2-events]
root         116  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-charg]
root         168  0.1  0.0      0     0 ?        I<   14:12   0:00 [kworker/0:1H-kblockd]
root         170  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/1:3-events]
root         185  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/1:4-events]
root         188  0.0  0.0      0     0 ?        S    14:12   0:00 [scsi_eh_2]
root         189  0.0  0.0      0     0 ?        I<   14:12   0:00 [kworker/R-scsi_]
root         194  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u12:1-events_power_efficient]
root         195  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/u12:2-events_power_efficient]
root         197  0.0  0.0      0     0 ?        I    14:12   0:00 [kworker/0:2-cgwb_release]
root         228  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-raid5]
root         256  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/2:2-cgroup_destroy]
root         257  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/2:2H-kblockd]
root         276  0.0  0.0      0     0 ?        S    14:13   0:00 [jbd2/sda2-8]
root         278  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-ext4-]
root         292  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/u11:2-flush-8:0]
root         343  0.0  0.4  42268 16168 ?        S<s  14:13   0:00 /usr/lib/systemd/systemd-journald
root         378  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/3:3-cgroup_destroy]
root         386  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-kmpat]
root         387  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-kmpat]
root         392  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/0:3-events]
root         393  0.0  0.6 288988 27324 ?        SLsl 14:13   0:00 /sbin/multipathd -d -s
root         404  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/u12:3-events_unbound]
root         407  0.0  0.1  28944  7788 ?        Ss   14:13   0:00 /usr/lib/systemd/systemd-udevd
root         445  0.0  0.0      0     0 ?        S    14:13   0:00 [psimon]
systemd+     466  0.0  0.2  19012  9504 ?        Ss   14:13   0:00 /usr/lib/systemd/systemd-networkd
root         467  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/3:4-events]
systemd+     481  0.0  0.3  21584 13032 ?        Ss   14:13   0:00 /usr/lib/systemd/systemd-resolved
systemd+     487  0.0  0.2  91028  7952 ?        Ssl  14:13   0:00 /usr/lib/systemd/systemd-timesyncd
message+     631  0.1  0.1   9784  5564 ?        Ss   14:13   0:00 @dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --sysl
polkitd      642  0.0  0.2 308164  8132 ?        Ssl  14:13   0:00 /usr/lib/polkit-1/polkitd --no-debug
root         661  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-cfg80]
root         662  0.0  0.2  18144  8980 ?        Ss   14:13   0:00 /usr/lib/systemd/systemd-logind
root         663  0.0  0.3 468972 13704 ?        Ssl  14:13   0:00 /usr/libexec/udisks2/udisksd
root         690  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/u8:2-ext4-rsv-conversion]
syslog       691  0.0  0.1 222508  6088 ?        Ssl  14:13   0:00 /usr/sbin/rsyslogd -n -iNONE
root         704  0.0  0.0      0     0 ?        S    14:13   0:00 [irq/18-vmwgfx]
root         705  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-ttm]
root         708  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/u8:3]
root         711  0.1  0.0      0     0 ?        I    14:13   0:00 [kworker/2:3-events]
root         749  0.0  0.5 109640 23172 ?        Ssl  14:13   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-si
root         753  0.0  0.3 392100 13044 ?        Ssl  14:13   0:00 /usr/sbin/ModemManager
root         846  0.0  0.0   6824  2904 ?        Ss   14:13   0:00 /usr/sbin/cron -f -P
root         852  0.0  0.2  12024  8148 ?        Ss   14:13   0:00 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
root         858  0.0  0.1   6944  4872 tty1     Ss   14:13   0:00 /bin/login -p --
root         968  0.0  0.0      0     0 ?        S    14:13   0:00 [psimon]
dafanr11     970  0.0  0.2  20092 11304 ?        Ss   14:13   0:00 /usr/lib/systemd/systemd --user
dafanr11     971  0.0  0.0  21152  3568 ?        S    14:13   0:00 (sd-pam)
dafanr11     982  0.0  0.1   8656  5664 tty1     S+   14:13   0:00 -bash
root        1023  0.0  0.0      0     0 ?        I<   14:13   0:00 [kworker/R-tls-s]
root        1025  0.0  0.0      0     0 ?        I    14:13   0:00 [kworker/u9:3-events_power_efficient]
root        1034  3.9  1.1 612364 43636 ?        Ssl  14:13   0:06 /usr/libexec/fwupd/fwupd
root        1041  0.2  0.2 314092  9172 ?        Ssl  14:13   0:00 /usr/libexec/upowerd
root        1074  0.0  0.2  14968 10628 ?        Ss   14:14   0:00 sshd: dafanr11 [priv]
root        1076  0.0  0.0      0     0 ?        I    14:14   0:00 [kworker/u11:3-events_power_efficient]
dafanr11    1127  0.0  0.1  14968  7124 ?        S    14:14   0:00 sshd: dafanr11@pts/0
dafanr11    1128  0.0  0.1   8648  5688 pts/0    Ss   14:14   0:00 -bash
dafanr11    1140  100  0.1  10884  4604 pts/0    R+   14:16   0:00 ps aux
```

2. Tampilkan proses beserta thread-nya, dapat dilihat pada kolom LWP (LightWeight Process ID):
```bash
ps aux -L
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux -L
USER         PID     LWP %CPU NLWP %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           1       1  0.5    1  0.3  22040 13240 ?        Ss   16:31   0:00 /sbin/init splash noprompt noshell automatic-ubiquity
root           2       2  0.0    1  0.0      0     0 ?        S    16:31   0:00 [kthreadd]
root           3       3  0.0    1  0.0      0     0 ?        S    16:31   0:00 [pool_workqueue_release]
root           4       4  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-rcu_g]
root           5       5  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-rcu_p]
root           6       6  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-slub_]
root           7       7  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-netns]
root           8       8  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/0:0-rcu_gp]
root           9       9  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/0:1-events]
root          10      10  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/0:0H-events_highpri]
root          11      11  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u8:0-ext4-rsv-conversion]
root          12      12  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-mm_pe]
root          13      13  0.0    1  0.0      0     0 ?        I    16:31   0:00 [rcu_tasks_kthread]
root          14      14  0.0    1  0.0      0     0 ?        I    16:31   0:00 [rcu_tasks_rude_kthread]
root          15      15  0.0    1  0.0      0     0 ?        I    16:31   0:00 [rcu_tasks_trace_kthread]
root          16      16  0.0    1  0.0      0     0 ?        S    16:31   0:00 [ksoftirqd/0]
root          17      17  0.0    1  0.0      0     0 ?        I    16:31   0:00 [rcu_preempt]
root          18      18  0.0    1  0.0      0     0 ?        S    16:31   0:00 [migration/0]
root          19      19  0.0    1  0.0      0     0 ?        S    16:31   0:00 [idle_inject/0]
root          20      20  0.0    1  0.0      0     0 ?        S    16:31   0:00 [cpuhp/0]
root          21      21  0.0    1  0.0      0     0 ?        S    16:31   0:00 [cpuhp/1]
root          22      22  0.0    1  0.0      0     0 ?        S    16:31   0:00 [idle_inject/1]
root          23      23  0.2    1  0.0      0     0 ?        S    16:31   0:00 [migration/1]
root          24      24  0.0    1  0.0      0     0 ?        S    16:31   0:00 [ksoftirqd/1]
root          25      25  0.1    1  0.0      0     0 ?        I    16:31   0:00 [kworker/1:0-events]
root          26      26  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/1:0H-events_highpri]
root          27      27  0.0    1  0.0      0     0 ?        S    16:31   0:00 [cpuhp/2]
root          28      28  0.0    1  0.0      0     0 ?        S    16:31   0:00 [idle_inject/2]
root          29      29  0.2    1  0.0      0     0 ?        S    16:31   0:00 [migration/2]
root          30      30  0.0    1  0.0      0     0 ?        S    16:31   0:00 [ksoftirqd/2]
root          31      31  0.1    1  0.0      0     0 ?        I    16:31   0:00 [kworker/2:0-events]
root          32      32  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/2:0H-kblockd]
root          33      33  0.0    1  0.0      0     0 ?        S    16:31   0:00 [cpuhp/3]
root          34      34  0.0    1  0.0      0     0 ?        S    16:31   0:00 [idle_inject/3]
root          35      35  0.0    1  0.0      0     0 ?        S    16:31   0:00 [migration/3]
root          36      36  0.0    1  0.0      0     0 ?        S    16:31   0:00 [ksoftirqd/3]
root          37      37  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/3:0-cgroup_destroy]
root          38      38  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/3:0H-events_highpri]
root          39      39  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u9:0-events_unbound]
root          40      40  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u10:0-flush-8:0]
root          41      41  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u11:0-flush-8:0]
root          42      42  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u12:0-events_power_efficient]
root          43      43  0.0    1  0.0      0     0 ?        S    16:31   0:00 [kdevtmpfs]
root          44      44  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-inet_]
root          45      45  0.0    1  0.0      0     0 ?        S    16:31   0:00 [kauditd]
root          46      46  0.0    1  0.0      0     0 ?        S    16:31   0:00 [khungtaskd]
root          47      47  0.0    1  0.0      0     0 ?        S    16:31   0:00 [oom_reaper]
root          48      48  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u9:1-events_power_efficient]
root          49      49  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-write]
root          50      50  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u9:2-events_unbound]
root          51      51  0.0    1  0.0      0     0 ?        S    16:31   0:00 [kcompactd0]
root          52      52  0.0    1  0.0      0     0 ?        SN   16:31   0:00 [ksmd]
root          53      53  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/2:1-cgroup_destroy]
root          54      54  0.0    1  0.0      0     0 ?        SN   16:31   0:00 [khugepaged]
root          55      55  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kinte]
root          56      56  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kbloc]
root          57      57  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-blkcg]
root          58      58  0.0    1  0.0      0     0 ?        S    16:31   0:00 [irq/9-acpi]
root          59      59  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/3:1-cgroup_destroy]
root          60      60  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-tpm_d]
root          61      61  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-ata_s]
root          62      62  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-md]
root          63      63  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-md_bi]
root          64      64  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-edac-]
root          65      65  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-devfr]
root          66      66  0.0    1  0.0      0     0 ?        S    16:31   0:00 [watchdogd]
root          67      67  0.2    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u11:1-flush-8:0]
root          68      68  0.1    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/2:1H-kblockd]
root          69      69  0.0    1  0.0      0     0 ?        S    16:31   0:00 [kswapd0]
root          70      70  0.0    1  0.0      0     0 ?        S    16:31   0:00 [ecryptfs-kthread]
root          71      71  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/1:1-events]
root          72      72  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kthro]
root          73      73  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-acpi_]
root          74      74  0.0    1  0.0      0     0 ?        S    16:31   0:00 [scsi_eh_0]
root          75      75  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-scsi_]
root          76      76  0.0    1  0.0      0     0 ?        S    16:31   0:00 [scsi_eh_1]
root          77      77  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-scsi_]
root          78      78  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u9:3-events_unbound]
root          79      79  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u9:4]
root          80      80  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-mld]
root          81      81  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/0:1H-kblockd]
root          82      82  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-ipv6_]
root          83      83  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u8:1-ipv6_addrconf]
root          85      85  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u11:2-events_unbound]
root          86      86  0.1    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u12:1-events_unbound]
root          87      87  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/3:2-cgroup_destroy]
root          93      93  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kstrp]
root          95      95  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/u13:0]
root          96      96  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/u14:0]
root          97      97  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/u15:0]
root          98      98  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/u16:0]
root          99      99  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/u17:0]
root         103     103  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u10:1]
root         105     105  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-crypt]
root         106     106  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/3:3-events]
root         115     115  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-charg]
root         142     142  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/1:1H-kblockd]
root         163     163  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/3:1H-kblockd]
root         170     170  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/2:2-cgroup_destroy]
root         171     171  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/0:2-rcu_gp]
root         186     186  0.6    1  0.0      0     0 ?        I    16:31   0:00 [kworker/0:3-events]
root         189     189  0.0    1  0.0      0     0 ?        S    16:31   0:00 [scsi_eh_2]
root         191     191  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-scsi_]
root         195     195  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u10:2-events_unbound]
root         209     209  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u12:2-writeback]
root         227     227  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-raid5]
root         272     272  0.0    1  0.0      0     0 ?        S    16:31   0:00 [jbd2/sda2-8]
root         273     273  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-ext4-]
root         337     337  0.1    1  0.4  42276 16148 ?        S<s  16:31   0:00 /usr/lib/systemd/systemd-journald
root         368     368  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kmpat]
root         369     369  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-kmpat]
root         372     372  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     405  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     406  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     407  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     408  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     409  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         372     410  0.0    7  0.6 288988 27324 ?        SLsl 16:31   0:00 /sbin/multipathd -d -s
root         392     392  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/3:4]
root         400     400  0.0    1  0.2  29208  7944 ?        Ss   16:31   0:00 /usr/lib/systemd/systemd-udevd
root         431     431  0.0    1  0.0      0     0 ?        S    16:31   0:00 [psimon]
systemd+     434     434  0.0    1  0.2  19012  9536 ?        Ss   16:31   0:00 /usr/lib/systemd/systemd-networkd
systemd+     471     471  0.0    1  0.3  21588 12988 ?        Ss   16:31   0:00 /usr/lib/systemd/systemd-resolved
systemd+     475     475  0.0    2  0.2  91028  7964 ?        Ssl  16:31   0:00 /usr/lib/systemd/systemd-timesyncd
systemd+     475     517  0.0    2  0.2  91028  7964 ?        Ssl  16:31   0:00 /usr/lib/systemd/systemd-timesyncd
root         491     491  0.3    1  0.0      0     0 ?        I    16:31   0:00 [kworker/1:2-events]
root         628     628  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/2:2H]
root         631     631  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u11:3-flush-8:0]
message+     639     639  0.0    1  0.1   9784  5492 ?        Ss   16:31   0:00 @dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-acti
root         645     645  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-cfg80]
polkitd      646     646  0.0    4  0.2 308164  8056 ?        Ssl  16:31   0:00 /usr/lib/polkit-1/polkitd --no-debug
polkitd      646     717  0.0    4  0.2 308164  8056 ?        Ssl  16:31   0:00 /usr/lib/polkit-1/polkitd --no-debug
polkitd      646     719  0.0    4  0.2 308164  8056 ?        Ssl  16:31   0:00 /usr/lib/polkit-1/polkitd --no-debug
polkitd      646     720  0.0    4  0.2 308164  8056 ?        Ssl  16:31   0:00 /usr/lib/polkit-1/polkitd --no-debug
root         653     653  0.0    1  0.2  18128  8876 ?        Ss   16:31   0:00 /usr/lib/systemd/systemd-logind
root         656     656  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         656     676  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         656     677  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         656     681  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         656     738  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         656     750  0.0    6  0.3 468976 13656 ?        Ssl  16:31   0:00 /usr/libexec/udisks2/udisksd
root         666     666  0.0    1  0.0      0     0 ?        S    16:31   0:00 [irq/18-vmwgfx]
root         672     672  0.0    1  0.0      0     0 ?        I<   16:31   0:00 [kworker/R-ttm]
root         688     688  0.0    2  0.5 109640 23112 ?        Ssl  16:31   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown
root         688     791  0.0    2  0.5 109640 23112 ?        Ssl  16:31   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown
syslog       691     691  0.0    4  0.1 222508  6044 ?        Ssl  16:31   0:00 /usr/sbin/rsyslogd -n -iNONE
syslog       691     731  0.0    4  0.1 222508  6044 ?        Ssl  16:31   0:00 /usr/sbin/rsyslogd -n -iNONE
syslog       691     732  0.0    4  0.1 222508  6044 ?        Ssl  16:31   0:00 /usr/sbin/rsyslogd -n -iNONE
syslog       691     733  0.0    4  0.1 222508  6044 ?        Ssl  16:31   0:00 /usr/sbin/rsyslogd -n -iNONE
root         712     712  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u8:2]
root         737     737  0.0    4  0.3 392032 12840 ?        Ssl  16:31   0:00 /usr/sbin/ModemManager
root         737     753  0.0    4  0.3 392032 12840 ?        Ssl  16:31   0:00 /usr/sbin/ModemManager
root         737     754  0.0    4  0.3 392032 12840 ?        Ssl  16:31   0:00 /usr/sbin/ModemManager
root         737     757  0.0    4  0.3 392032 12840 ?        Ssl  16:31   0:00 /usr/sbin/ModemManager
root         823     823  0.0    1  0.0   6824  2904 ?        Ss   16:31   0:00 /usr/sbin/cron -f -P
root         829     829  0.0    1  0.2  12024  8124 ?        Ss   16:31   0:00 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
root         834     834  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/2:3]
root         836     836  0.0    1  0.1   6948  4896 tty1     Ss   16:31   0:00 /bin/login -p --
root         862     862  0.0    1  0.0      0     0 ?        I    16:31   0:00 [kworker/u10:3-writeback]
root         944     944  0.0    1  0.0      0     0 ?        S    16:32   0:00 [psimon]
dafanr11     946     946  0.0    1  0.2  20276 11436 ?        Ss   16:32   0:00 /usr/lib/systemd/systemd --user
dafanr11     947     947  0.0    1  0.0  21152  3588 ?        S    16:32   0:00 (sd-pam)
dafanr11     958     958  0.0    1  0.1   8656  5664 tty1     S+   16:32   0:00 -bash
root         970     970  0.0    1  0.0      0     0 ?        I    16:32   0:00 [kworker/u11:4-flush-8:0]
root         971     971  0.1    1  0.2  14968 10568 ?        Ss   16:32   0:00 sshd: dafanr11 [priv]
dafanr11    1020    1020  0.7    1  0.1  14968  7108 ?        S    16:32   0:00 sshd: dafanr11@pts/0
dafanr11    1021    1021  0.1    1  0.1   8648  5688 pts/0    Ss   16:32   0:00 -bash
dafanr11    1031    1031  500    1  0.1  11012  4608 pts/0    R+   16:33   0:00 ps aux -L
```

3. Lihat PID shell aktif dan detail prosesnya:
```bash
echo $$
ps -p $$ -f
```
Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ echo $$
1021
dafanr11@Ubuntu-Server-New:~$ ps -p $$ -f
UID          PID    PPID  C STIME TTY          TIME CMD
dafanr11    1021    1020  0 16:32 pts/0    00:00:00 -bash
```

4. Lihat hierarki proses secara visual:
```bash
pstree -p
```
Output:  
```bash
dafanr11@Ubuntu-Server-New:~$ pstree -p
systemd(1)─┬─ModemManager(737)─┬─{ModemManager}(753)
           │                   ├─{ModemManager}(754)
           │                   └─{ModemManager}(757)
           ├─cron(823)
           ├─dbus-daemon(639)
           ├─login(836)───bash(958)
           ├─multipathd(372)─┬─{multipathd}(405)
           │                 ├─{multipathd}(406)
           │                 ├─{multipathd}(407)
           │                 ├─{multipathd}(408)
           │                 ├─{multipathd}(409)
           │                 └─{multipathd}(410)
           ├─polkitd(646)─┬─{polkitd}(717)
           │              ├─{polkitd}(719)
           │              └─{polkitd}(720)
           ├─rsyslogd(691)─┬─{rsyslogd}(731)
           │               ├─{rsyslogd}(732)
           │               └─{rsyslogd}(733)
           ├─sshd(829)───sshd(971)───sshd(1020)───bash(1021)───pstree(1036)
           ├─systemd(946)───(sd-pam)(947)
           ├─systemd-journal(337)
           ├─systemd-logind(653)
           ├─systemd-network(434)
           ├─systemd-resolve(471)
           ├─systemd-timesyn(475)───{systemd-timesyn}(517)
           ├─systemd-udevd(400)
           ├─udisksd(656)─┬─{udisksd}(676)
           │              ├─{udisksd}(677)
           │              ├─{udisksd}(681)
           │              ├─{udisksd}(738)
           │              └─{udisksd}(750)
           └─unattended-upgr(688)───{unattended-upgr}(791)
```  

  
### Latihan 6.1  

Jalankan ps aux dan amati outputnya:
1. Berapa total proses yang berjalan? Proses apa yang memiliki PID terkecil?
2. Jalankan pstree -p dan temukan proses bash Anda. Proses apa yang menjadi induk (PPID) dari bash tersebut?
3. Bandingkan output ps aux dan ps aux -L. Apa perbedaan yang Anda lihat?  

Jawaban :

1. Total proses yang sedang berjalan pada sistem tersebut sekitar 120 proses, sedangkan proses yang memiliki PID terkecil adalah PID 1, yaitu proses /sbin/init yang merupakan sistem inisialisasi (systemd).
2. Berdasarkan output pstree -p, proses bash yang digunakan berada pada rantai systemd → sshd → sshd → sshd → bash, sehingga proses yang menjadi induk (PPID) dari bash tersebut adalah proses sshd dengan PID 1020. 
3. Perbedaan antara output ps aux dan ps aux -L adalah bahwa ps aux hanya menampilkan daftar proses yang sedang berjalan, sedangkan ps aux -L menampilkan proses beserta thread (LWP) yang dimiliki oleh setiap proses tersebut, sehingga pada ps aux -L satu proses dapat muncul beberapa kali sesuai jumlah thread-nya dan ditandai dengan adanya kolom tambahan seperti LWP dan NLWP.


## Praktikum 6.2 — Mengamati Siklus Hidup Proses

1. Buat proses di background dan amati kondisinya:
```bash
sleep 60 &
ps aux | grep sleep
```
Output :
```bash
dafanr11@Ubuntu-Server-New:~$ sleep 60 &
[1] 1172
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1172  0.0  0.0   5684  2104 pts/0    S    16:42   0:00 sleep 60
dafanr11    1174  0.0  0.0   6544  2328 pts/0    S+   16:42   0:00 grep --color=auto sleep
```

2. Amati perubahan exit code dari perintah yang berhasil dan gagal:
```bash
ls / tmp
echo " Sukses : $?"
ls / direktori - tidak - ada
echo " Gagal : $?"
```
Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ ls /tmp
snap-private-tmp
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-man-db.service-e6HVfP
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-ModemManager.service-0iqcjT
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-polkit.service-PPlWsl
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-systemd-logind.service-rbd0lb
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-systemd-resolved.service-zROjM9
systemd-private-a6aa73f8a1cb42a7a9158a0822fc076e-systemd-timesyncd.service-bXh6pp
[1]+  Done                    sleep 60
dafanr11@Ubuntu-Server-New:~$ echo " Sukses : $?"
 Sukses : 0
dafanr11@Ubuntu-Server-New:~$ ls /direktori-tidak-ada
ls: cannot access '/direktori-tidak-ada': No such file or directory
dafanr11@Ubuntu-Server-New:~$ echo " Gagal : $?"
Gagal : 2
```  

### Latihan 6.2  

1. Jalankan sleep 120 & dan amati kolom STAT pada ps aux. Kondisi
apa yang ditampilkan? Mengapa proses sleep berada di kondisi tersebut?  
2. Jalankan beberapa perintah yang berhasil dan yang gagal, lalu catat exit
code masing-masing. Pola apa yang Anda temukan?

Jawaban :  
1. Setelah menjalankan perintah sleep 120 &, pada output ps aux terlihat bahwa proses sleep memiliki status S, yang berarti sleeping (idle). Kondisi ini terjadi karena perintah sleep tidak melakukan aktivitas CPU, melainkan hanya menunggu selama 120 detik sebelum selesai, sehingga proses tersebut berada dalam keadaan menunggu (sleeping) sampai waktu yang ditentukan habis.
2. Pola yang dapat diamati adalah bahwa setiap perintah yang berhasil akan menghasilkan exit code 0, sedangkan perintah yang gagal akan menghasilkan exit code selain 0 (biasanya angka lebih besar, misalnya 1, 2, dan seterusnya sesuai jenis kesalahan).

 
## Praktikum 6.3 — Mengatur Prioritas Proses

1. Jalankan proses dengan prioritas rendah:
```bash
nice -n 10 sleep 300 &
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ nice -n 10 sleep 300 &
[3] 1211
```

2. Verifikasi nilai nice pada kolom NI:
```bash
ps aux | grep sleep
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1414  0.0  0.0   5684  2108 pts/0    SN   17:00   0:00 sleep 300
dafanr11    1418  0.0  0.0   6544  2328 pts/0    S+   17:00   0:00 grep --color=auto sleep
```

3. Ubah nilai nice proses yang sudah berjalan:
```bash
renice -n 15 -p <PID >
ps -p <PID > -o pid , ni , cmd
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ renice -n 15 -p 1414
1414 (process ID) old priority 10, new priority 15
dafanr11@Ubuntu-Server-New:~$ ps -p 1414 -o pid,ni,cmd
    PID  NI CMD
   1414  15 sleep 300
```

4. Bersihkan proses percobaan:
```bash
kill %1
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ kill %1
-bash: kill: (1414) - No such process
[1]+  Terminated              nice -n 10 sleep 300
```

### Latihan 6.3
1. Jalankan nice -n 5 sleep 200 & dan verifikasi nilai NI-nya dengan
ps.  
2. Ubah nilai nice menjadi 10 menggunakan renice, lalu verifikasi kembali.  
3. Coba ubah nilai nice menjadi -5 tanpa sudo. Apa yang terjadi? Mengapa Linux membatasi hal ini untuk user biasa?  

Jawaban :  
1.  
```bash
dafanr11@Ubuntu-Server-New:~$  nice -n 5 sleep 200 &
[1] 1440
dafanr11@Ubuntu-Server-New:~$ ps -o pid,ni,cmd
    PID  NI CMD
   1403   0 -bash
   1440   5 sleep 200
   1442   0 ps -o pid,ni,cmd
```
2.  
```bash
dafanr11@Ubuntu-Server-New:~$ renice -n 10 -p 1440
1440 (process ID) old priority 5, new priority 10
dafanr11@Ubuntu-Server-New:~$ ps -o pid,ni,cmd
    PID  NI CMD
   1403   0 -bash
   1440  10 sleep 200
   1449   0 ps -o pid,ni,cmd
```
3. Akan muncul pesan permission denied 
```bash
dafanr11@Ubuntu-Server-New:~$ nice -n -5 sleep 200
nice: cannot set niceness: Permission denied
```



## Praktikum 6.4 — Mengirim Sinyal ke Proses
1. Buat proses percobaan:
```bash
sleep 500 &
sleep 600 &
sleep 700 &
ps aux | grep -v grep | grep sleep
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ sleep 500 &
[1] 1192
dafanr11@Ubuntu-Server-New:~$ sleep 600 &
[2] 1193
dafanr11@Ubuntu-Server-New:~$ sleep 700 &
[3] 1194
dafanr11@Ubuntu-Server-New:~$ ps aux | grep -v grep | grep sleep
dafanr11    1192  0.0  0.0   5684  2104 pts/0    S    23:19   0:00 sleep 500
dafanr11    1193  0.0  0.0   5684  2104 pts/0    S    23:19   0:00 sleep 600
dafanr11    1194  0.0  0.0   5684  2108 pts/0    S    23:19   0:00 sleep 700
```

2. Hentikan satu proses dengan SIGTERM dan verifikasi:
```bash
kill <PID - sleep -500 >
ps aux | grep -v grep | grep sleep
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ kill 1192
dafanr11@Ubuntu-Server-New:~$ ps aux | grep -v grep | grep sleep
dafanr11    1193  0.0  0.0   5684  2104 pts/0    S    23:19   0:00 sleep 600
dafanr11    1194  0.0  0.0   5684  2108 pts/0    S    23:19   0:00 sleep 700
[1]   Terminated              sleep 500
```

3. Jeda dan lanjutkan proses dengan SIGSTOP/SIGCONT:
```bash
kill - SIGSTOP <PID - sleep -600 >
ps aux | grep sleep # amati kolom STAT : berubah
menjadi T
kill - SIGCONT <PID - sleep -600 >
ps aux | grep sleep # STAT kembali ke S
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ kill -SIGSTOP 1193
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1193  0.0  0.0   5684  2104 pts/0    T    23:19   0:00 sleep 600
dafanr11    1194  0.0  0.0   5684  2108 pts/0    S    23:19   0:00 sleep 700
dafanr11    1205  0.0  0.0   6544  2332 pts/0    S+   23:22   0:00 grep --color=auto sleep

[2]+  Stopped                 sleep 600
dafanr11@Ubuntu-Server-New:~$ kill -SIGCONT 1193
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1193  0.0  0.0   5684  2104 pts/0    S    23:19   0:00 sleep 600
dafanr11    1194  0.0  0.0   5684  2108 pts/0    S    23:19   0:00 sleep 700
dafanr11    1207  0.0  0.0   6544  2328 pts/0    S+   23:22   0:00 grep --color=auto sleep
```

4. Hentikan semua proses sleep sekaligus:
```bash
pkill sleep
```

Output :  
```bash
dafanr11@Ubuntu-Server-New:~$ pkill sleep
[2]-  Terminated              sleep 600
[3]+  Terminated              sleep 700
```


### Latihan 6.4
1. Jalankan sleep 400 &, kirim SIGSTOP, dan amati perubahan kolom STAT. Kondisi apa yang muncul?
2. Kirim SIGCONT dan verifikasi proses kembali berjalan.
3. Hentikan proses dengan SIGTERM lalu verifikasi sudah tidak ada. Kapan Anda memilih SIGKILL daripada SIGTERM?

Jawaban :  
1. Kondisi yang muncul adalah status proses berubah menjadi T (Stopped), yang berarti proses tersebut sedang dihentikan sementara oleh sinyal kontrol dan tidak akan berlanjut hingga menerima sinyal SIGCONT.
```bash
dafanr11@Ubuntu-Server-New:~$ sleep 400 &
[1] 1214
dafanr11@Ubuntu-Server-New:~$ kill -SIGSTOP 1214
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1214  0.0  0.0   5684  2104 pts/0    T    23:25   0:00 sleep 400
dafanr11    1219  0.0  0.0   6544  2328 pts/0    S+   23:25   0:00 grep --color=auto sleep

[1]+  Stopped                 sleep 400
```
2. STAT kembali ke sleep dan proses akan berjalan seperti normal. 
```bash
dafanr11@Ubuntu-Server-New:~$ kill -SIGCONT 1214
dafanr11@Ubuntu-Server-New:~$ ps aux | grep sleep
dafanr11    1214  0.0  0.0   5684  2104 pts/0    S    23:25   0:00 sleep 400
dafanr11    1222  0.0  0.0   6544  2332 pts/0    S+   23:26   0:00 grep --color=auto sleep
```
3. Pilih SIGKILL jika proses sudah tidak responsif (freeze) atau tetap berjalan meski sudah diberi perintah SIGTERM. Hal ini dikarenakan SIGTERM adalah permintaan sopan agar program berhenti secara normal, sedangkan SIGKILL adalah perintah paksa dari kernel yang tidak dapat diabaikan oleh proses tersebut. 
```bash
dafanr11@Ubuntu-Server-New:~$ kill 1214
dafanr11@Ubuntu-Server-New:~$ ps aux | grep -v grep | grep sleep
[1]+  Terminated              sleep 400
```

## Praktikum 6.5 — Manajemen Job Foreground dan Background
1. Jalankan tiga job di background:
```bash
sleep 200 &
sleep 300 &
sleep 400 &
jobs
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ sleep 200 &
[1] 1266
dafanr11@Ubuntu-Server-New:~$ sleep 300 &
[2] 1267
dafanr11@Ubuntu-Server-New:~$ sleep 400 &
[3] 1268
dafanr11@Ubuntu-Server-New:~$ jobs
[1]   Running                 sleep 200 &
[2]-  Running                 sleep 300 &
[3]+  Running                 sleep 400 &
```

2. Bawa job pertama ke foreground, jeda, lalu kembalikan ke background:
```bash
fg %1
# Tekan Ctrl +Z untuk menjeda
bg %1
jobs
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ fg %1
sleep 200
^Z
[1]+  Stopped                 sleep 200
dafanr11@Ubuntu-Server-New:~$ bg %1
[1]+ sleep 200 &
dafanr11@Ubuntu-Server-New:~$ jobs
[1]   Running                 sleep 200 &
[2]-  Running                 sleep 300 &
[3]+  Running                 sleep 400 &
```

3. Hentikan semua job:
```bash
kill %1 %2 %3
jobs
```

Output : 
```bash
dafanr11@Ubuntu-Server-New:~$ kill %1 %2 %3
dafanr11@Ubuntu-Server-New:~$ jobs
[1]   Terminated              sleep 200
[2]-  Terminated              sleep 300
[3]+  Terminated              sleep 400
```


### Latihan 6.5
1. Jalankan top di foreground. Apa yang terjadi di terminal?
2. Tekan Ctrl+Z dan cek statusnya dengan jobs. Kondisi apa yang ditampilkan?
3. Pindahkan ke background dengan bg. Apakah top dapat berjalan dengan baik di background? Mengapa?
4. Kembalikan ke foreground dengan fg, lalu keluar dengan q .

Jawaban :  

1. Terminal terisi penuh dengan tampilan top dan tidak bisa menerima perintah lain sampai top keluar dengan menekan ctrl + z. 
```bash
top - 23:42:31 up 29 min,  2 users,  load average: 0.00, 0.00, 0.00
Tasks: 137 total,   3 running, 134 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.2 sy,  0.0 ni, 99.4 id,  0.3 wa,  0.0 hi,  0.1 si,  0.0 st
MiB Mem :   3819.3 total,   3381.4 free,    416.3 used,    236.9 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3403.0 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
   1265 root      20   0       0      0      0 R   0.6   0.0   0:00.58 kworker/0:2-events
    816 root      20   0       0      0      0 I   0.3   0.0   0:01.34 kworker/3:3-mm_percpu_wq
    836 root      20   0       0      0      0 I   0.3   0.0   0:01.22 kworker/2:3-events
      1 root      20   0   21984  13208   9532 S   0.0   0.3   0:01.37 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.03 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.12 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.54 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.11 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.44 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.15 ksoftirqd/1
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.47 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/2
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
     34 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
     35 root      rt   0       0      0      0 S   0.0   0.0   0:00.08 migration/3
     36 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/3
     38 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/3:0H-events_highpri
     40 root      20   0       0      0      0 I   0.0   0.0   0:00.16 kworker/u10:0-events_power_efficient
```

2. Kondisi yang ditampilkan adalah status Stopped, yang menunjukkan bahwa perintah top telah dihentikan sementara dan dipindahkan ke latar belakang (background)
```bash
[1]+  Stopped                 top
dafanr11@Ubuntu-Server-New:~$ jobs
[1]+  Stopped                 top
```

3. Top tidak dapat berjalan dengan baik di background karena ia adalah program interaktif yang membutuhkan akses langsung ke layar terminal untuk memperbarui tampilan secara real-time. Begitu dipindah ke latar belakang, proses tersebut biasanya akan langsung terhenti (stopped) kembali karena tidak bisa menerima input atau mengirim output visual ke terminal. 
```bash
dafanr11@Ubuntu-Server-New:~$ bg %1
[1]+ top &

[1]+  Stopped                 top
```

4. Top kembali ke foreground, lalu tekan q untuk keluar dengan normal. 
```bash
top - 23:43:36 up 30 min,  2 users,  load average: 0.12, 0.03, 0.01
Tasks: 136 total,   1 running, 135 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.1 sy,  0.0 ni, 99.8 id,  0.0 wa,  0.0 hi,  0.1 si,  0.0 st
MiB Mem :   3819.3 total,   3381.4 free,    416.3 used,    236.9 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3403.0 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
     59 root      20   0       0      0      0 I   1.0   0.0   0:08.75 kworker/1:1-events
     18 root      rt   0       0      0      0 S   0.1   0.0   0:00.12 migration/0
    386 root      rt   0  288988  27324   8760 S   0.1   0.7   0:00.85 multipathd
   1220 root      20   0       0      0      0 I   0.1   0.0   0:00.39 kworker/u10:3-events_power_efficient
   1255 root      20   0  314096   9268   7640 S   0.1   0.2   0:00.40 upowerd
top - 23:50:02 up 36 min,  2 users,  load average: 0.05, 0.01, 0.00
Tasks: 135 total,   1 running, 134 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.2 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.1 si,  0.0 st
MiB Mem :   3819.3 total,   3381.4 free,    416.2 used,    237.1 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3403.1 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
     59 root      20   0       0      0      0 I   0.7   0.0   0:10.01 kworker/1:1-events
   1255 root      20   0  314096   9288   7640 S   0.7   0.2   0:00.64 upowerd
     79 root      20   0       0      0      0 I   0.3   0.0   0:00.65 kworker/u10:2-events_power_efficient
      1 root      20   0   21984  13208   9532 S   0.0   0.3   0:01.38 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.03 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.14 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.60 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.13 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.45 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.17 ksoftirqd/1
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.49 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/2
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
     34 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
     35 root      rt   0       0      0      0 S   0.0   0.0   0:00.10 migration/3
     36 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/3
     38 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/3:0H-events_highpri
     43 root      20   0       0      0      0 S   0.0   0.0   0:00.00 kdevtmpfs
```


## Praktikum 6.6 — Pemantauan Proses
1. Temukan proses dengan penggunaan CPU dan memori tertinggi:
```bash
ps aux -- sort = -% cpu | head -10
ps aux -- sort = -% mem | head -10
```

Output ;  
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux --sort=-%cpu | head -10
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
dafanr11    1293  200  0.1  10884  4580 pts/0    R+   23:51   0:00 ps aux --sort=-%cpu
root          59  0.4  0.0      0     0 ?        I    23:13   0:10 [kworker/1:1-events]
dafanr11    1182  0.3  0.1  14972  7116 ?        S    23:19   0:06 sshd: dafanr11@pts/0
root        1281  0.2  0.0      0     0 ?        I    23:47   0:00 [kworker/0:1-events]
root        1265  0.1  0.0      0     0 ?        I    23:36   0:01 [kworker/0:2-mm_percpu_wq]
root         836  0.0  0.0      0     0 ?        I    23:13   0:02 [kworker/2:3-events]
root         816  0.0  0.0      0     0 ?        I    23:13   0:01 [kworker/3:3-events]
root        1255  0.0  0.2 314096  9292 ?        Ssl  23:35   0:00 /usr/libexec/upowerd
root        1248  0.0  1.0 478196 41868 ?        Ssl  23:35   0:00 /usr/libexec/fwupd/fwupd
dafanr11@Ubuntu-Server-New:~$ ps aux --sort=-%mem | head -10
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1248  0.0  1.0 478196 41868 ?        Ssl  23:35   0:00 /usr/libexec/fwupd/fwupd
root         386  0.0  0.6 288988 27324 ?        SLsl 23:13   0:01 /sbin/multipathd -d -s
root         711  0.0  0.5 109640 23132 ?        Ssl  23:13   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         334  0.0  0.4  50464 16352 ?        S<s  23:13   0:00 /usr/lib/systemd/systemd-journald
root         646  0.0  0.3 468972 13576 ?        Ssl  23:13   0:00 /usr/libexec/udisks2/udisksd
root           1  0.0  0.3  21984 13208 ?        Ss   23:13   0:01 /sbin/init splash noprompt noshell automatic-ubiquity
systemd+     443  0.0  0.3  21584 12984 ?        Ss   23:13   0:00 /usr/lib/systemd/systemd-resolved
root         717  0.0  0.3 392032 12844 ?        Ssl  23:13   0:00 /usr/sbin/ModemManager
dafanr11     943  0.0  0.2  20272 11492 ?        Ss   23:13   0:00 /usr/lib/systemd/systemd --user
```

2. Jalankan top dan eksplorasi shortcut-nya:
```bash
top
# Tekan M, P, 1 , u secara bergantian
# Tekan q untuk keluar
```

Output ;  
```bash
dafanr11@Ubuntu-Server-New:~$ top
top - 23:56:17 up 42 min,  2 users,  load average: 0.00, 0.01, 0.00
Tasks: 135 total,   1 running, 134 sleeping,   0 stopped,   0 zombie
%Cpu0  :  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
%Cpu1  :  0.0 us,  0.0 sy,  0.0 ni, 98.3 id,  1.0 wa,  0.0 hi,  0.7 si,  0.0 st
%Cpu2  :  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
%Cpu3  :  0.0 us,  0.7 sy,  0.0 ni, 99.3 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3819.3 total,   3379.7 free,    417.6 used,    237.4 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3401.7 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    816 root      20   0       0      0      0 I   0.7   0.0   0:01.98 kworker/3:3-events
   1308 dafanr11  20   0   11936   5952   3724 R   0.3   0.2   0:00.12 top
      1 root      20   0   21984  13208   9532 S   0.0   0.3   0:01.41 systemd
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.04 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.19 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.67 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.15 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.46 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.20 ksoftirqd/1
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.51 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/2
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
     34 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
     35 root      rt   0       0      0      0 S   0.0   0.0   0:00.11 migration/3
     36 root      20   0       0      0      0 S   0.0   0.0   0:00.01 ksoftirqd/3
```

3. Instal dan jalankan htop:
```bash
sudo apt install -y htop
htop
# Tekan F6 untuk pilih kolom pengurutan
# Tekan F10 atau q untuk keluar
```

Output ;  
```bash
dafanr11@Ubuntu-Server-New:~$ sudo apt install -y htop
[sudo] password for dafanr11:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
htop is already the newest version (3.3.0-4build1).
htop set to manually installed.
0 upgraded, 0 newly installed, 0 to remove and 0 not upgraded.
dafanr11@Ubuntu-Server-New:~$ htop
```

### Latihan 6.6  
1. Gunakan ps aux –sort=%mem untuk menemukan proses yang menggunakan memori paling banyak di VM Anda. Proses apa itu?  
2. Di dalam top, tekan 1 . Apa yang berubah pada tampilan? Mengapa
informasi ini berguna?  
3. Di dalam htop, navigasikan ke proses sshd menggunakan tombol panah.
Tekan F9 dan amati opsi sinyal yang tersedia.  

Jawaban :  

1.   
```bash
ps aux --sort=-%mem | head -5
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root        1248  0.0  1.0 478196 41868 ?        Ssl  23:35   0:00 /usr/libexec/fwupd/fwupd
root         386  0.0  0.6 288988 27324 ?        SLsl 23:13   0:01 /sbin/multipathd -d -s
root         711  0.0  0.5 109640 23132 ?        Ssl  23:13   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-signal
root         334  0.0  0.4  50464 16360 ?        S<s  23:13   0:00 /usr/lib/systemd/systemd-journald
```
2. Tampilan berubah dari satu baris rata-rata menjadi rincian per core CPU (%Cpu0, %Cpu1, dst). Informasi ini berguna untuk mendeteksi apakah beban kerja terbagi rata atau ada satu core yang bekerja terlalu berat akibat proses tertentu yang tidak efisien.
```bash
dafanr11@Ubuntu-Server-New:~$ top
top - 00:01:56 up 48 min,  2 users,  load average: 0.00, 0.00, 0.00
Tasks: 136 total,   1 running, 135 sleeping,   0 stopped,   0 zombie
%Cpu0  :  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
%Cpu1  :  0.0 us,  0.0 sy,  0.0 ni, 99.3 id,  0.0 wa,  0.0 hi,  0.7 si,  0.0 st
%Cpu2  :  0.0 us,  0.0 sy,  0.0 ni, 99.7 id,  0.0 wa,  0.0 hi,  0.3 si,  0.0 st
%Cpu3  :  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3819.3 total,   3295.3 free,    432.8 used,    307.1 buff/cache
MiB Swap:      0.0 total,      0.0 free,      0.0 used.   3386.5 avail Mem

    PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
     59 root      20   0       0      0      0 I   0.7   0.0   0:13.50 kworker/1:1-events
      1 root      20   0   21984  13208   9532 S   0.3   0.3   0:01.50 systemd
   1241 root      20   0       0      0      0 I   0.3   0.0   0:00.28 kworker/u11:0-events_unbound
   1287 root      20   0       0      0      0 I   0.3   0.0   0:00.48 kworker/0:3-events
   1354 dafanr11  20   0   11936   5980   3752 R   0.3   0.2   0:00.26 top
      2 root      20   0       0      0      0 S   0.0   0.0   0:00.04 kthreadd
      3 root      20   0       0      0      0 S   0.0   0.0   0:00.00 pool_workqueue_release
      4 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_g
      5 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-rcu_p
      6 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-slub_
      7 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-netns
     10 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/0:0H-events_highpri
     12 root       0 -20       0      0      0 I   0.0   0.0   0:00.00 kworker/R-mm_pe
     13 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_kthread
     14 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_rude_kthread
     15 root      20   0       0      0      0 I   0.0   0.0   0:00.00 rcu_tasks_trace_kthread
     16 root      20   0       0      0      0 S   0.0   0.0   0:00.23 ksoftirqd/0
     17 root      20   0       0      0      0 I   0.0   0.0   0:00.79 rcu_preempt
     18 root      rt   0       0      0      0 S   0.0   0.0   0:00.16 migration/0
     19 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/0
     20 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/0
     21 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/1
     22 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/1
     23 root      rt   0       0      0      0 S   0.0   0.0   0:00.46 migration/1
     24 root      20   0       0      0      0 S   0.0   0.0   0:00.32 ksoftirqd/1
     27 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/2
     28 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/2
     29 root      rt   0       0      0      0 S   0.0   0.0   0:00.52 migration/2
     30 root      20   0       0      0      0 S   0.0   0.0   0:00.02 ksoftirqd/2
     33 root      20   0       0      0      0 S   0.0   0.0   0:00.00 cpuhp/3
     34 root     -51   0       0      0      0 S   0.0   0.0   0:00.00 idle_inject/3
```
3. Akan muncul daftar sinyal yang bisa dikirim (SIGTERM, SIGKILL, SIGHUP, dll). Ini memudahkan tanpa perlu mengingat nomor sinyal.



## 1.8 Latihan
### Latihan 6.A
Eksplorasi Proses Sistem
1. Jalankan ps aux –forest dan temukan proses dengan PID 1. Apa
nama dan fungsi proses tersebut dalam sistem Linux modern?
2. Hitung berapa proses yang dimiliki oleh user root dan berapa yang
dimiliki oleh user Anda. Mengapa root memiliki lebih banyak proses?
3. Temukan semua proses yang berada dalam kondisi S. Mengapa sebagian
besar proses di sistem berada dalam kondisi ini?

Jawaban :  

1. PID 1 adalah /sbin/init (systemd), yaitu proses utama yang dijalankan saat boot dan berfungsi mengelola semua service serta proses dalam sistem Linux.
```bash
dafanr11@Ubuntu-Server-New:~$ ps aux --forest
USER         PID %CPU %MEM    VSZ   RSS TTY      STAT START   TIME COMMAND
root           2  0.0  0.0      0     0 ?        S    03:57   0:00 [kthreadd]
root           3  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [pool_workqueue_release]
root           4  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-rcu_g]
root           5  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-rcu_p]
root           6  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-slub_]
root           7  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-netns]
root           8  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/0:0-events]
root           9  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/0:1-cgroup_destroy]
root          10  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/0:0H-events_highpri]
root          11  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u8:0-ipv6_addrconf]
root          12  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-mm_pe]
root          13  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [rcu_tasks_kthread]
root          14  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [rcu_tasks_rude_kthread]
root          15  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [rcu_tasks_trace_kthread]
root          16  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [ksoftirqd/0]
root          17  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [rcu_preempt]
root          18  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [migration/0]
root          19  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [idle_inject/0]
root          20  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [cpuhp/0]
root          21  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [cpuhp/1]
root          22  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [idle_inject/1]
root          23  0.1  0.0      0     0 ?        S    03:57   0:00  \_ [migration/1]
root          24  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [ksoftirqd/1]
root          25  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/1:0-cgroup_destroy]
root          26  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/1:0H-events_highpri]
root          27  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [cpuhp/2]
root          28  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [idle_inject/2]
root          29  0.1  0.0      0     0 ?        S    03:57   0:00  \_ [migration/2]
root          30  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [ksoftirqd/2]
root          31  0.1  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/2:0-events]
root          32  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/2:0H-kblockd]
root          33  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [cpuhp/3]
root          34  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [idle_inject/3]
root          35  0.1  0.0      0     0 ?        S    03:57   0:00  \_ [migration/3]
root          36  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [ksoftirqd/3]
root          37  0.3  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/3:0-events]
root          38  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/3:0H-events_highpri]
root          39  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u9:0-events_power_efficient]
root          40  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u10:0-events_freezable_power_]
root          41  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u11:0-events_power_efficient]
root          42  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u12:0-events_power_efficient]
root          43  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [kdevtmpfs]
root          44  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-inet_]
root          45  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [kauditd]
root          46  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [khungtaskd]
root          47  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [oom_reaper]
root          48  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u9:1-events_power_efficient]
root          49  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-write]
root          50  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u9:2-events_power_efficient]
root          51  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [kcompactd0]
root          52  0.0  0.0      0     0 ?        SN   03:57   0:00  \_ [ksmd]
root          53  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/3:1-rcu_gp]
root          54  0.0  0.0      0     0 ?        SN   03:57   0:00  \_ [khugepaged]
root          55  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kinte]
root          56  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kbloc]
root          57  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-blkcg]
root          58  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [irq/9-acpi]
root          59  0.6  0.0      0     0 ?        I    03:57   0:01  \_ [kworker/2:1-events]
root          60  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-tpm_d]
root          61  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-ata_s]
root          62  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-md]
root          63  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-md_bi]
root          64  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-edac-]
root          65  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-devfr]
root          66  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [watchdogd]
root          67  0.1  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u12:1-events_unbound]
root          68  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/3:1H-kblockd]
root          69  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [kswapd0]
root          70  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [ecryptfs-kthread]
root          71  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kthro]
root          72  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-acpi_]
root          73  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [scsi_eh_0]
root          74  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-scsi_]
root          75  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [scsi_eh_1]
root          76  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-scsi_]
root          77  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u9:3-events_power_efficient]
root          78  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u9:4]
root          79  0.4  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/1:1-mm_percpu_wq]
root          80  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-mld]
root          81  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u10:1-events_power_efficient]
root          82  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/1:1H-kblockd]
root          83  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-ipv6_]
root          84  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u8:1-ext4-rsv-conversion]
root          86  0.1  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/0:2-events]
root          88  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/2:1H-kblockd]
root          93  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kstrp]
root          95  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/u13:0]
root          96  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/u14:0]
root          97  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/u15:0]
root          98  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/u16:0]
root          99  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/u17:0]
root         101  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u10:2-flush-8:0]
root         105  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-crypt]
root         106  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/3:2-events]
root         107  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/1:2-cgroup_bpf_destroy]
root         113  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u11:1-events_unbound]
root         117  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-charg]
root         142  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/0:1H-kblockd]
root         185  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [scsi_eh_2]
root         186  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-scsi_]
root         204  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u12:2-events_power_efficient]
root         207  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u11:2-events_unbound]
root         228  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-raid5]
root         273  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [jbd2/sda2-8]
root         274  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-ext4-]
root         357  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u12:3-writeback]
root         362  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kmpat]
root         363  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-kmpat]
root         364  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/2:2-events]
root         404  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/3:3-cgroup_destroy]
root         434  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/3:4-events]
root         440  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [psimon]
root         503  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u11:3-events_unbound]
root         653  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/2:2H-kblockd]
root         682  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/u11:4]
root         698  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-cfg80]
root         712  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [irq/18-vmwgfx]
root         713  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/R-ttm]
root         835  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/0:3-cgroup_destroy]
root         853  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/1:3-events]
root         856  0.0  0.0      0     0 ?        I    03:57   0:00  \_ [kworker/2:3-cgroup_destroy]
root         960  0.0  0.0      0     0 ?        S    03:57   0:00  \_ [psimon]
root         986  0.0  0.0      0     0 ?        I<   03:57   0:00  \_ [kworker/3:2H-kblockd]
root        1049  0.0  0.0      0     0 ?        I    03:58   0:00  \_ [kworker/u10:3-events_unbound]
root           1  0.4  0.3  22024 13184 ?        Ss   03:57   0:01 /sbin/init splash noprompt noshell automatic-ubiquity
root         338  0.1  0.4  50468 17196 ?        S<s  03:57   0:00 /usr/lib/systemd/systemd-journald
root         372  0.1  0.6 288988 27324 ?        SLsl 03:57   0:00 /sbin/multipathd -d -s
root         400  0.0  0.1  28944  7692 ?        Ss   03:57   0:00 /usr/lib/systemd/systemd-udevd
systemd+     454  0.0  0.2  19012  9500 ?        Ss   03:57   0:00 /usr/lib/systemd/systemd-networkd
systemd+     469  0.0  0.3  21584 13044 ?        Ss   03:57   0:00 /usr/lib/systemd/systemd-resolved
systemd+     477  0.0  0.2  91028  7932 ?        Ssl  03:57   0:00 /usr/lib/systemd/systemd-timesyncd
message+     636  0.0  0.1   9788  5560 ?        Ss   03:57   0:00 @dbus-daemon --system --address=systemd: --nofork --nopidfile --systemd-activation --sysl
polkitd      642  0.0  0.2 308164  8104 ?        Ssl  03:57   0:00 /usr/lib/polkit-1/polkitd --no-debug
root         650  0.0  0.2  18132  8844 ?        Ss   03:57   0:00 /usr/lib/systemd/systemd-logind
root         652  0.0  0.3 468972 13652 ?        Ssl  03:57   0:00 /usr/libexec/udisks2/udisksd
syslog       703  0.0  0.1 222508  6156 ?        Ssl  03:57   0:00 /usr/sbin/rsyslogd -n -iNONE
root         708  0.0  0.3 392100 12920 ?        Ssl  03:57   0:00 /usr/sbin/ModemManager
root         711  0.0  0.5 109640 23080 ?        Ssl  03:57   0:00 /usr/bin/python3 /usr/share/unattended-upgrades/unattended-upgrade-shutdown --wait-for-si
root         840  0.0  0.0   6824  2904 ?        Ss   03:57   0:00 /usr/sbin/cron -f -P
root         846  0.0  0.2  12024  8208 ?        Ss   03:57   0:00 sshd: /usr/sbin/sshd -D [listener] 0 of 10-100 startups
root         990  0.0  0.2  14968 10648 ?        Ss   03:58   0:00  \_ sshd: dafanr11 [priv]
dafanr11    1039  1.1  0.1  14968  7120 ?        S    03:58   0:01      \_ sshd: dafanr11@pts/0
dafanr11    1040  0.0  0.1   8648  5656 pts/0    Ss   03:58   0:00          \_ -bash
dafanr11    1065  200  0.1  10884  4584 pts/0    R+   04:01   0:00              \_ ps aux --forest
root         852  0.0  0.1   6944  4880 tty1     Ss   03:57   0:00 /bin/login -p --
dafanr11     972  0.0  0.1   8656  5708 tty1     S+   03:57   0:00  \_ -bash
dafanr11     962  0.0  0.2  20272 11436 ?        Ss   03:57   0:00 /usr/lib/systemd/systemd --user
dafanr11     963  0.0  0.0  21152  3568 ?        S    03:57   0:00  \_ (sd-pam)
```
2. Root memiliki ±100+ proses, user dafanr11 memiliki sekitar 6 proses. Root lebih banyak karena menjalankan kernel thread dan service sistem, sedangkan user hanya menjalankan proses sesi sendiri.

3. Status S (sleeping) berarti proses sedang menunggu event/input. Mayoritas proses S karena sistem Linux bekerja efisien: proses hanya aktif saat dibutuhkan, sisanya idle.


### Latihan 6.B
Simulasi Manajemen Job
1. Jalankan tiga perintah sleep dengan durasi 100, 200, dan 300 detik di
background. Verifikasi ketiganya dengan jobs.
2. Bawa job kedua ke foreground, jeda dengan Ctrl+Z , lalu kembalikan
ke background dengan bg.
3. Hentikan job pertama dengan kill %1. Tampilkan kembali daftar job.
Berapa job yang tersisa?

Jawaban : 

1.  
```bash
dafanr11@Ubuntu-Server-New:~$ sleep 100 &
[1] 1081
dafanr11@Ubuntu-Server-New:~$ sleep 200 &
[2] 1082
dafanr11@Ubuntu-Server-New:~$ sleep 300 &
[3] 1083
dafanr11@Ubuntu-Server-New:~$ jobs
[1]   Running                 sleep 100 &
[2]-  Running                 sleep 200 &
[3]+  Running                 sleep 300 &
```
2.  
```bash
dafanr11@Ubuntu-Server-New:~$ fg %2
sleep 200
^Z
[2]+  Stopped                 sleep 200
dafanr11@Ubuntu-Server-New:~$ bg %2
[2]+ sleep 200 &
```
3.  
```bash
dafanr11@Ubuntu-Server-New:~$ kill %1
-bash: kill: (1081) - No such process
[1]   Done                    sleep 100
dafanr11@Ubuntu-Server-New:~$ jobs
[2]-  Running                 sleep 200 &
[3]+  Running                 sleep 300 &
```


### Latihan 6.C
Prioritas dan Sinyal
1. Jalankan dua proses sleep: satu dengan nice +5 dan satu dengan nice
+15. Verifikasi nilai NI keduanya dengan ps.
2. Gunakan renice untuk mengubah nice proses pertama menjadi +10.
Proses mana yang kini lebih diprioritaskan scheduler?
3. Kirim SIGSTOP ke salah satu proses, verifikasi kondisi T-nya, lalu kirim
SIGCONT. Akhiri semua proses percobaan dengan pkill sleep.

Jawaban :  

1.  
```bash
dafanr11@Ubuntu-Server-New:~$ nice -n 5 sleep 200 &
[4] 1090
dafanr11@Ubuntu-Server-New:~$ nice -n 15 sleep 200 &
[5] 1091
dafanr11@Ubuntu-Server-New:~$ ps -o pid,ni,cmd | grep sleep
   1082   0 sleep 200
   1083   0 sleep 300
   1090   5 sleep 200
   1091  15 sleep 200
   1093   0 grep --color=auto sleep
```
2. Proses dengan nilai nice lebih kecil (lebih rendah dari +10, misalnya yang sebelumnya +5) kini lebih diprioritaskan oleh scheduler, karena semakin besar nilai nice maka prioritasnya semakin rendah.
```bash
dafanr11@Ubuntu-Server-New:~$ renice -n 10 -p 1090
1090 (process ID) old priority 5, new priority 10
[2]   Done                    sleep 200
``` 
3.
```bash
dafanr11@Ubuntu-Server-New:~$ kill -SIGSTOP 1090
[3]   Done                    sleep 300

[4]+  Stopped                 nice -n 5 sleep 200
dafanr11@Ubuntu-Server-New:~$ ps -o pid,stat,cmd | grep sleep
   1090 TN   sleep 200
   1091 SN   sleep 200
   1099 S+   grep --color=auto sleep
dafanr11@Ubuntu-Server-New:~$ kill -SIGCONT 1090
dafanr11@Ubuntu-Server-New:~$ ps -o pid,stat,cmd | grep sleep
   1090 SN   sleep 200
   1091 SN   sleep 200
   1104 S+   grep --color=auto sleep
dafanr11@Ubuntu-Server-New:~$ pkill sleep
[4]-  Done                    nice -n 5 sleep 200
[5]+  Terminated              nice -n 15 sleep 200
```