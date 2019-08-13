# begian 4 : package installation

Pada bagian ini, saia bagi menjadi 3 kategori berdasarkan distribusi Linux yang umum digunakan. Berlaku untuk ~~anaknya~~ turunannya.

### Debian / Ubuntu

Debian, Ubuntu dan turunannya menggunakan package installer **dpkg** untuk instalasi package yang telah di-download.

Untuk instalasi dan download package melalui repositori, menggunakan **apt**, atau **apt-get**.

Syntax dasar

Offline install deb dengan dpkg

```
dpkg -i <file-package.deb>
```

Update repo
```
apt update
```

Install package
```
apt install <package-name>
```
Upgrade packages
```
apt upgrade
```



### Red Hat / Fedora / Oracle

Pada distro RHEL/Fedora dan turunannya, menggunakan **RPM** sebagai package installer.

Untuk instalasi dan download package melalui repo, menggunakan **dnf** atau **yum**.

Syntax dasar

```
dnf install <nama-package>
```

```
yum install <nama-package>
```

### Arch Linux

Arch Linux memiliki repo sendiri, yang terdiri dari repo umum, dan komunitas (AUR).

Semua instalasi dan download package dapat dilakukan melalui **pacman**. Namun bila package yang ingin di-*install* adalah package yang berasal dari AUR, maka perlu menggunakan ~~pacar anda~~ **pacaur** ataupun **yaourt**.

Syntax dasar

Install

```
pacman -S <nama package>
```

Refresh repo (?)

```
pacman -Syu
```

Update packages

```
pacman -Syyu
```
