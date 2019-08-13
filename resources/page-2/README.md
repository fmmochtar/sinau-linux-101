# begian 2 : users, file permissions, ownership

### basic of user accounts

Perintah dasar ini terdiri dari login, dan menggunakan sudo.

- Login dengan username tertentu

    ```bash
    su <username>
    ```

    Perintah di atas dan di bawah sekilas memiliki efek yang sama, namun bila memerlukan variabel yang telah dikonfigurasi pada user tersebut, maka gunakan perintah di bawah ini.

    ```bash
    su - <username>
    ```

- sudo

  Perintah **sudo** memiliki efek yang sama seperti **Run as Administrator** pada Windows, yaitu menjalankan suatu baris operasi sebagai **root**.

  ```bash
  sudo <command>
  ```

  

### create, delete users, and change passwords

Perintah dasar yang digunakan untuk urusan user account pada Linux adalah:

- **adduser**	: membuat user baru

  ```bash
  adduser <username-baru>
  ```

  Contoh: 

  ```bash
  [root@noodles:/home/bakmie] # adduser netlab
  ```


- **deluser**	: hapus user yang ada pada sistem tersebut

  ```bash
  deluser <username>
  ```

  Contoh: 

  ```bash
  [root@noodles:/home/bakmie] # deluser netlab
  ```
  
- **passwd**	: memberikan atau mengubah password pada suatu user

  ```bash
  passwd <username>
  ```

  Contoh: 

  ```bash
  [bakmie@noodles:~] $ sudo passwd netlab
  ```
  
  ```
  [root@noodles:~] # passwd netlab
  ```
  

### file / folder permissions and ownerships

Pada Linux, terdapat suatu permission dan ownership pada file untuk menentukan siapa user yang memiliki akses pada file maupun folder tersebut.

#### permission groups

Tiap file dan direktori memiliki 3 kelompok permission berdasarkan user, yaitu:

- owner	: hanya berlaku untuk pemilik file / direktori, tidak ada impact pada user lainnya.
- group	: hanya berlaku pada group yang telah di-*assign* pada file / direktori, tidak ada impact pada user lainnya.
- all users : berlaku untuk semua user lain pada sistem.

#### permission types

Tiap file atau direktori memiliki 3 jenis *permission*, yaitu:

- read	: kapabilitas user untuk melakukan read file / direktori
- write	: kapabilitas user untuk melakukan write file / direktori
- execute : kapabilitas user untuk melakukan eksekusi file biner (executable files)

**rwxrwxrwx**

- **r**ead = 4
- **w**rite = 2
- e**x**ecute = 1



- **chmod**	: ganti permission

  ```bash
  chmod [R][W][X] <file/folder>
  ```

  ```
  chmod [a/u/g/o][+/-/=][r/w/x] <file/folder>
  ```

  Contoh: 

  ```bash
  [bakmie@noodles:~] $ chmod 775 text.txt 
  ```
    ```bash
  [bakmie@noodles:~] $ chmod u=rwx,g=rx,o=r text.txt 
    ```
  
  ```bash
  [bakmie@noodles:~] $ chmod a+rwx text.txt 
  ```

- **chown**	: ganti ownership pada file/direktori

  ```bash
  chown <username>:<group> <file/folder>
  ```
  Contoh: 

  - Pada sebuah **file**

    ```bash
    [bakmie@noodles] $ chown bakmie:bakmie README.txt
    ```

  - Pada sebuah **direktori** dan seisinya

    ```bash
    [bakmie@noodles] $ chown -R bakmie:bakmie ./folder-github
    ```
    
  
