# bagian 4 : package installation

Pada bagian ini, saia bagi menjadi 3 kategori berdasarkan distribusi Linux yang umum digunakan. Berlaku untuk ~~anaknya~~ turunannya.

### Debian / Ubuntu

Debian, Ubuntu dan turunannya menggunakan package installer **dpkg** untuk instalasi package yang telah di-download.

Untuk instalasi dan download package melalui repositori, menggunakan **apt**, atau **apt-get**.

#### Syntax dasar

| Functions                             | Command line               |
| ------------------------------------- | -------------------------- |
| Offline install **deb** dengan dpkg   | dpkg -i <file-package.deb> |
| **Update** repo                       | apt update                 |
| **Install** package                   | apt install <package-name> |
| **Upgrade** packages                  | apt upgrade                |
| **Remove** package(s)                 | apt remove <package-name>  |
| **Purge** packages(s) (total removal) | apt purge <package-name>   |

Debian, Ubuntu serta turunannya memiliki repositori yang berisi daftar package untuk instalasi, dan package tersebut didapatkan melalui repo tersebut.



**penambahan repo coming soon**



### Red Hat / Fedora / Oracle

Pada distro RHEL/Fedora dan turunannya, menggunakan **RPM** sebagai package installer.

Untuk instalasi dan download package melalui repo, menggunakan **dnf** atau **yum**. Lebih disarankan menggunakan **dnf**, karena sudah mengalami improvisasi dari segi algoritma untuk deteksi *broken dependencies*.

Syntax dasar:

```bash
dnf install <nama-package>
```

```bash
yum install <nama-package>
```

### Arch Linux

Arch Linux memiliki repo sendiri, yang terdiri dari repo umum, dan komunitas (AUR).

Semua instalasi dan download package dapat dilakukan melalui **pacman**. Namun bila package yang ingin di-*install* adalah package yang berasal dari AUR, maka perlu menggunakan ~~pacar anda~~ **pacaur** ataupun **yaourt**.

Syntax dasar

Install

```bash
pacman -S <package-name>
```

Update repo (?)

```bash
pacman -Sy
```

Upgrade packages

```bash
pacman -Syu
```

Remove packages

```bash
pacman -R <package-name>
```

