# **LAPRES_MODUL 5_JARKOM** 
-----------------------------------
## **KELOMPOK T_16**
## Bagus Farhan Abdillah (05311840000016)
## I Gede Pradhana Indra Widnyana (05311840000031)

----------------------------------

### Soal 1 
### Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi SURABAYA menggunakan iptables, namun Bibah tidak ingin kalian menggunakan MASQUERADE.

- Melakukan konfigurasi pada SURABAYA dengan syntax ``iptables -t nat -A POSTROUTING -s 192.162.0.0/16 eth0 -j SNAT --to-source 10.151.76.90``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792643485332930571/1.1_Setting_iptables_surabaya.JPG">

- Dan berikut merupakan gambar berhasil melakukan ping saat menggunakan iptables.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792645413801951242/1.2_berhasil_ping_untuk_semua_menggunakan_iptables.JPG" width="800" height="400">

### Soal 2
### Kalian diminta untuk mendrop semua akses SSH dari luar Topologi (UML) Kalian pada server yang memiliki ip DMZ (DHCP dan DNS SERVER) pada SURABAYA demi menjaga keamanan.

- Melakukan konfigurasi iptables pada SURABAYA dengan syntax ``iptables -A FORWARD -p tcp --dport 22 -d 10.151.77.176/29 -i eth0 -j DROP``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792646769724620800/2.1_setting_iptables_pada_surabaya.JPG" width="500" height="400">

- Kemudian lakukan pengintsallan netcat pada MOJOKERTO dan MALANG dengan command ``apt-get install netcat``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792647357215932446/2.2_install_netcat_pada_mojokerto_dan_malang.JPG" width="500" height="400">

- Berikut merupakan hasil blok kiriman SSH dari luar (putty) ke malang (port 22). 

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792654535360249856/2.4_berhasil_memblok_kiriman_ssh_dari_luar_putty_ke_malang_port22.JPG" width="600" height="400">

- Berikut merupakan hasil blok kiriman SSH dari SIDOARJO ke MALANG.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792655117169721404/2.4_berhasil_memblok_kiriman_ssh_dari_sidoarjo_ke_malang_port22.JPG" width="600" height="400">

- Berikut merupakan hasil blok kiriman SSH dari luar (putty) ke MOJOKERTO (port 22).

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792656289464582144/2.5_berhasil_memblok_kiriman_ssh_dari_luar_putty_ke_mojokerto_port22.JPG" width="600" height="400">

### Soal 3
### Karena tim kalian maksimal terdiri dari 3 orang, Bibah meminta kalian untuk membatasi DHCP dan DNS server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan yang berasal dari mana saja menggunakan iptables pada masing masing server, selebihnya akan di DROP.

- Lakukan konfigurasi pada iptables MALANG dan MOJOKERTO dengan syntax ``iptables -A INPUT -p icmp -m conlimit-above 3 --conlimit-mask 0 -j DROP``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792659156418822164/3.1_setting_iptables_pada_malang_dan_mojokerto.JPG" width="400" height="500">

- Berikut merupakan hasil ping pada MADIUN, PROBOLINGGO, SIDOARJO dan gagal pada GRESIK karena dibatasi 3.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792659623843725322/3.1_berhasil_ping_pada_madiun_probolinggo_sidoarjo_dan_gagal_pada_gresik_dibatasi_3.JPG" width="500" height="500">

### Soal 4
### Akses dari subnet SIDOARJO hanya diperbolehkan pada pukul 07.00 - 17.00 pada hari Senin sampai Jumat.








