# **LAPRES_MODUL 5_JARKOM** 
-----------------------------------
## **KELOMPOK T_16**
## Bagus Farhan Abdillah (05311840000016)
## I Gede Pradhana Indra Widnyana (05311840000031)

----------------------------------

## Topologi Soal Pada Modul 5

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792730817842642964/Topologi_A.JPG">

### A

- Lakukan konfigurasi setup topologi UML seperti pada gambar dibawah ini.

```
# Switch
uml_switch -unix switch0 > /dev/null < /dev/null &
uml_switch -unix switch1 > /dev/null < /dev/null &
uml_switch -unix switch2 > /dev/null < /dev/null &
uml_switch -unix switch3 > /dev/null < /dev/null &
uml_switch -unix switch4 > /dev/null < /dev/null &
uml_switch -unix switch5 > /dev/null < /dev/null &

# Router
xterm -T SURABAYA -e linux ubd0=SURABAYA,jarkom umid=SURABAYA eth0=tuntap,,,10.151.76.88 eth1=daemon,,,switch3 eth2=daemon,,,switch2 mem=96M &
xterm -T KEDIRI -e linux ubd0=KEDIRI,jarkom umid KEDIRI eth0=daemon,,,switch3 eth1=daemon,,,switch4 eth2=daemon,,,seitch5 mem=96M &
xterm -T BATU -e linux ubd0=BATU,jarkom umid BATU eth0=daemon,,,switch2 eth1=daemon,,,switch1 eth2=daemon,,,switch0 mem=96M &

# Server
xterm -T MALANG -e linux ubd0=MALANG,jarkom umid=MALANG eth0=daemon,,,switch0 mem=128M &
xterm -T MOJOKERTO -e linux ubd0=MOJOKERTO,jarkom umid=MOJOKERTO eth0=daemon,,,switch0 mem=128M &
xterm -T MADIUN -e linux ubd0=MADIUN,jarkom umid=MADIUN eth0=daemon,,,switch5 mem=128M &
xterm -T PROBOLINGGO -e linux ubd0=PROBOLINGGO,jarkom umid=PROBOLINGGO eth0=daemon,,,switch5 mem=128M &

# Klien
xterm -T SIDOARJO -e linux ubd0=SIDOARJO,jarkom umid=SIDOARJO eth0=daemon,,,switch1 mem=96M &
xterm -T GRESIK -e linux ubd0=GRESIK,jarkom umid=GRESIK eth0=daemon,,,switch4 mem=96M &
```

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792735718702186526/Setup_Topologi_UML.JPG" width="800" height="400">

- Kemudian lakukan konfigurasi interfaces pada UML BATU, GRESIK, KEDIRI, MADIUN, MALANG, MOJOKERTO, PROBOLINGGO, SIDOARJO, dan SURABAYA sepeti pada gambar dibawah ini.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792736484708712459/A._Setting_Batu.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792736804380999700/A._Setting_Gresik.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737548035162122/A._Setting_Kediri.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737610082156564/A._Setting_Madiun.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737670228344852/A._Setting_Malang.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737734548652032/A._Setting_Mojokerto.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737793381367808/A._Setting_Probolinggo.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737843179946005/A._Setting_Sidoarjo.JPG" width="500" height="400">
<br />
<img src="https://cdn.discordapp.com/attachments/777146787336290354/792737893193744394/A._Setting_Surabaya.JPG" width="500" height="400">

### B

- Berikut merupakan pembagian menggunakan metode CIDR untuk perhitungan IP pada pohon CIDR (Tree CIDR).

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792738225264656454/B._Pembagian_CIDR.png">

- Berikut merupakan perhitungan pohon untuk pembagian IP dengan menggunakan metode CIDR.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792738268801400832/B._Tree_CIDR.JPG">

- Berikut merupakan pembagian IP yang sudah disesuaikan dengan lingkaran topologi dan perhitungan dari tree CIDR.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792738248912928778/B._Pembagian_IP_setelah_pembuatan_tree.JPG">

### C

- Lakukan konfigurasi untuk routing pada SURABAYA seperti pada gambar dibawah ini.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792739245210730516/C.1_Routing_Surabaya.JPG" width="400" height="500">

- Berikut merupakan hasil routing SURABAYA.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792739526656393216/C.2_Routing_surabaya_berhasil.JPG" width="400" height="500">

- Kemudian lakukan konfigurasi untuk routing pada KEDIRI seperti pada gambar dibawah ini.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792739715530358804/C.3_Routing_Kediri.JPG" width="500" height="400">

- Berikut merupakan hasil routing KEDIRI.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792739736145100840/C.4_Routing_Kediri_berhasil.JPG" width="500" height="400">

- Berikut merupakan hasil ping untuk semua routing.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792740387143417906/C.5_berhasil_ping_untuk_semua_routing.JPG" width="800" height="400">



### Soal 1 
### Agar topologi yang kalian buat dapat mengakses keluar, kalian diminta untuk mengkonfigurasi SURABAYA menggunakan iptables, namun Bibah tidak ingin kalian menggunakan MASQUERADE.

- Melakukan konfigurasi pada SURABAYA dengan syntax ``iptables -t nat -A POSTROUTING -s 192.162.0.0/16 eth0 -j SNAT --to-source 10.151.76.90``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792643485332930571/1.1_Setting_iptables_surabaya.JPG">

- Dan berikut merupakan gambar berhasil melakukan ping saat menggunakan iptables.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792645413801951242/1.2_berhasil_ping_untuk_semua_menggunakan_iptables.JPG" width="800" height="400">

### Soal 2
### Kalian diminta untuk mendrop semua akses SSH dari luar Topologi (UML) Kalian pada server yang memiliki ip DMZ (DHCP dan DNS SERVER) pada SURABAYA demi menjaga keamanan.

- Melakukan konfigurasi iptables pada SURABAYA dengan syntax ``iptables -A FORWARD -p tcp --dport 22 -d 10.151.77.176/29 -i eth0 -j DROP``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792646769724620800/2.1_setting_iptables_pada_surabaya.JPG" width="800" height="400">

- Kemudian lakukan pengintsallan netcat pada MOJOKERTO dan MALANG dengan command ``apt-get install netcat``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792647357215932446/2.2_install_netcat_pada_mojokerto_dan_malang.JPG" width="800" height="400">

- Berikut merupakan hasil blok kiriman SSH dari luar (putty) ke malang (port 22). 

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792654535360249856/2.4_berhasil_memblok_kiriman_ssh_dari_luar_putty_ke_malang_port22.JPG" width="800" height="400">

- Berikut merupakan hasil blok kiriman SSH dari SIDOARJO ke MALANG.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792655117169721404/2.4_berhasil_memblok_kiriman_ssh_dari_sidoarjo_ke_malang_port22.JPG" width="800" height="400">

- Berikut merupakan hasil blok kiriman SSH dari luar (putty) ke MOJOKERTO (port 22).

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792656289464582144/2.5_berhasil_memblok_kiriman_ssh_dari_luar_putty_ke_mojokerto_port22.JPG" width="800" height="400">

### Soal 3
### Karena tim kalian maksimal terdiri dari 3 orang, Bibah meminta kalian untuk membatasi DHCP dan DNS server hanya boleh menerima maksimal 3 koneksi ICMP secara bersamaan yang berasal dari mana saja menggunakan iptables pada masing masing server, selebihnya akan di DROP.

- Lakukan konfigurasi pada iptables MALANG dan MOJOKERTO dengan syntax ``iptables -A INPUT -p icmp -m conlimit-above 3 --conlimit-mask 0 -j DROP``.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792659156418822164/3.1_setting_iptables_pada_malang_dan_mojokerto.JPG" width="400" height="500">

- Berikut merupakan hasil ping pada MADIUN, PROBOLINGGO, SIDOARJO dan gagal pada GRESIK karena dibatasi 3.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792659623843725322/3.1_berhasil_ping_pada_madiun_probolinggo_sidoarjo_dan_gagal_pada_gresik_dibatasi_3.JPG" width="500" height="500">

### Soal 5
### Akses dari subnet GRESIK hanya diperbolehkan pada pukul 17.00 hingga pukul 07.00 setiap harinya. Selain itu paket akan di REJECT.

- Lakukan konfigurasi iptables MALANG pada subnet GRESIK dengan syntax ``iptables -A INPUT -s 192.168.0.0/24 -m time --timestart 09.01 --timestop 16.59 -j reject``

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792724934387826698/5.1_setup_iptables_malang_pada_subnet_gresik.JPG" width="500" height="400">

- Berikut merupakan percobaan netcat pada MALANG dari GRESIK di waktu yang tidak diperbolehkan dan gagal.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792725463314464788/5.2_percobaan_netcat_pada_malang_dari_gresik_diwaktu_yang_tidak_diperbolehkan_dan_gagal.JPG" width="800" height="400">

- Kemudian lakukan konfigurasi penggantian waktu MALANG di waktu yang diperbolehkan.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792725905474322453/5.3_mengganti_waktu_malang_di_waktu_yang_diperbolehkan.JPG" width="500" height="400">

- Berikut merupakan hasil dari mengirimkan pesan dari GRESIK ke MALANG di waktu yang diperbolehkan.

<img src="https://cdn.discordapp.com/attachments/777146787336290354/792726238036623370/5.4_berhasil_mengirimkan_pesan_dari_gresik_ke_malang_diwaktu_yang_diperbolehkan.JPG" width="800" height="400">
