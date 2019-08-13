# begian 3 : networking setup

Bagian ini menjelaskan tentang konfigurasi jaringan pada Linux.



### inspecting interfaces information and its IP

Untuk melihat alamat IP pada Linux, dapat menggunakan perintah berikut

```bash
ifconfig
```

Umumnya, distro Linux pada tahun 2018 ke atas tidak menyediakan **ifconfig** secara default, solusi alternatifnya adalah menggunakan perintah **ip**, seperti yang tertulis di bawah ini.

```bash
ip address
```

Bila menggunakan Ubuntu versi 18.04 ke atas, biasanya secara default menggunakan **netplan**.



### configuring ip address in linux

Linux memiliki konfigurasi networking yang tersimpan dalam bentuk teks.

Umumnya, bila menggunakan distro seperti Debian ataupun Ubuntu, tersimpan pada:

```
/etc/network/interfaces/
```

Contoh konfigurasi

```
# Example

# Loopback interface is necessary
auto lo
iface lo inet loopback

# config ethernet (broadcast opsional)
auto ens18
iface ens18 inet static
    address 192.168.1.37
    netmask 255.255.255.0
    broadcast 192.168.1.255
    gateway 192.168.1.1

```

