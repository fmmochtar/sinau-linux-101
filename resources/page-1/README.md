# bagian 1 : file operations

Bagian ini menjelaskan tentang operasi file dan direktori umum pada Linux.

### playing with list of files and directories

Perintah dasar yang biasanya digunakan untuk melihat isi direktori, dan lain-lain adalah:

- **pwd**	: melihat posisi direktori yang sedang dikunjungi saat ini

  ```bash
  pwd
  ```

  Contoh: 

  ```bash
  [bakmie@noodles:~] $ pwd
  /home/bakmie
  ```


- **ls**	: lihat daftar isi pada direktori / folder

  ```bash
  ls
  ```

  Contoh: 

  ```bash
  [bakmie@noodles:~] $ ls 
  README.md	file3.txt
  ```

  Arguments:

  -l : tampilkan dalam bentuk list

  -a : tampilkan semua (termasuk hidden files/folders)

  -h : tampilkan dalam bentuk human-readable formats (berlaku untuk file/folder size)

  Contoh dengan argumen:

  ```bash
  # tampilkan dalam bentuk list, dan human-readable
  ls -lh
  ```

  ```bash
  # tampilkan dalam bentuk list, show all hidden files and folders
  ls -la
  ```

  ```bash
  # tampilkan dalam bentuk list, show all hidden files and folders, human readable
  ls -lah
  ```

  

- **cd**	: berpindah direktori

  ```bash
  cd <desirable directory>
  ```
  Contoh: 

  - Short length, simplified

    ```bash
    [bakmie@noodles:~] $ cd ./folder-github
    [bakmie@noodles:~/folder-github] $
    ```

  
  - Full length
  
    ```bash
    [bakmie@noodles:~] $ cd /home/bakmie/folder-github
    [bakmie@noodles:~/folder-github] $
    ```
  


### file operation

Perintah dasar yang digunakan untuk operasi file dan folder antara lain:

- **cp**	: copy file / folder

  ```bash
  cp <source file/folder> <destination file/folder>
  ```

  Contoh: 

  ```bash
  [bakmie@noodles:~] $ cp README.md text.txt 
  ```

- **rm**	: hapus file / folder

  ```bash
  rm <source file/folder>
  ```
  Contoh: 

  - Hapus **file**

    ```bash
    [bakmie@noodles:~] $ rm README.md 
    ```

  - Hapus **folder** dan seisinya

    ```bash
    [bakmie@noodles:~] $ rm -r ./folder-sampah
    ```
    
  - Hapus folder dan seisinya (no confirmation)
    
    ```bash
    [bakmie@noodles:~] $ rm -rf ./folder-sampah
    ```
    

- **mv**	: **pindah** file / folder. Dapat digunakan untuk rename file / folder

  ```bash
  mv <source file/folder> <destination file/folder>
  ```
  Contoh: 

  ```bash
  [bakmie@noodles:~] $ mv README.md ./folder-github 
  ```

- **touch**	: create new file

  ```bash
  touch <nama-file>
  ```
  Contoh: 

  ```bash
  [bakmie@noodles:~] $ touch tabel-fisdas.csv
  ```

- **mkdir**	: create new folder

  ```bash
  mkdir <folder-name>
  ```
    Contoh: 

  ```bash
  [bakmie@noodles:~] $ mkdir folder-kuliah
  ```

### writing and/or editing text files

Biasanya, distro Linux memberikan bawaan teks editor dengan tampilan command line. Contoh yang biasanya kita temukan adalah **nano** dan **vi** / **vim**.

Bagi pemula, **nano** merupakan text editor yang cukup user-friendly karena memiliki control yang mudah dipahami oleh user.

-   Contoh: 

  ```bash
  [bakmie@noodles:~] $ nano .bashrc
  ```

**Basic controls:**

Ctrl + \ : Find and replace

Ctrl + O : save file

Ctrl + X : exit



**Vi** / **Vim** biasanya digunakan bagi pengguna Linux yang sudah memiliki skill menengah - mahir. Untuk menggunakannya, sangat diperlukan panduan awal agar dapat memahami penggunaan program tersebut.

-   Contoh: 

  ```bash
  [bakmie@noodles:~] $ vim .bashrc
  ```



**Basic controls:**

Ctrl + C : Command mode / Exit insert mode

Insert / i : Edit (Insert mode)

a : Edit (Append mode)



Save / Exit

| `:qa`          | Tutup file                             |
| -------------- | -------------------------------------- |
| `:qa!`         | Exit, tutup semua file tanpa perubahan |
| `:w`           | Save                                   |
| `:wq` */* `:x` | Save dan exit                          |
| `:q`           | Exit                                   |
|                |                                        |
|                |                                        |



Untuk lebih lengkapnya, dapat melihat cheat sheet nya pada link berikut: https://devhints.io/vim

