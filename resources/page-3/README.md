# bagian 3 : networking setup

Bagian ini menjelaskan tentang konfigurasi jaringan pada Linux, serta mendapatkan informasi tentang IP interface


### inspecting interfaces information and its IP

Untuk melihat alamat IP pada Linux, dapat menggunakan perintah berikut.

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

Contoh konfigurasi:

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
#   dns-nameserver 8.8.8.8

```

RHEL/Fedora/CentOS (coming soon)

#### Netplan 

Netplan merupakan konfigurasi jaringan yang dikembangkan oleh Canonical yang digunakan pada distro Ubuntu. Menggunakan bahasa data-serialization bernama YAML, yang bersifat case-sensitive, dan tidak diperkenankan menggunakan indentasi dengan TAB, melainkan menggunakan spasi. 

Indentasi antar child dengan parent, ataupun sub-child dengan child harus konsisten. Sebagai contoh berikut, ethernets dengan enp3s0 (ataupun nama interface lainnya), bila indentasi awal adalah 2 spasi, maka indentasi berikutnya harus 2 spasi, dan ditambah 2 spasi lagi untuk child nya.

Lokasi konfigurasi terletak pada:

```
/etc/network/interfaces/
```

Contoh konfigurasi:

```
network:
  ethernets:
    enp3s0:
      addresses:
        - 10.10.10.2/24
      gateway4: 10.10.10.1
      nameservers:
          search: [mydomain, otherdomain]
          addresses: [10.10.10.1, 1.1.1.1]
  version: 2
```

Setelah mengubah konfigurasi tersebut, untuk menerapkannya dapat menggunakan:

```
netplan apply
```

### name server resolver

DNS (Domain Name Server) memiliki fungsi untuk translasi hostname dalam bentuk tulisan (domain), seperti **google.com** menjadi alamat IP.

DNS yang digunakan dapat diubah sesuai yang kita inginkan, dengan cara mengubah konfigurasi pada **/etc/resolv.conf** atau menambahkan opsi **dns-nameserver** pada konfigurasi interface (sesuai pada contoh sebelumnya).

Contoh konfigurasi resolv.conf

```
nameserver 8.8.8.8
```

