# begian 1 : file operations

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
  ```
  
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
    [bakmie@noodles] $ rm README.md 
    ```

  - Hapus **folder** dan seisinya

    ```bash
    [bakmie@noodles] $ rm -r ./folder-sampah
    ```
    
  - Hapus folder dan seisinya (no confirmation)
    
    ```bash
    [bakmie@noodles] $ rm -rf ./folder-sampah
    ```
    

- **mv**	: **pindah** file / folder. Dapat digunakan untuk rename file / folder

  ```bash
  mv <source file/folder> <destination file/folder>
  ```
  Contoh: 

  ```bash
  [bakmie@noodles] $ mv README.md ./folder-github 
  ```

- **touch**	: create new file

  ```bash
  touch <nama-file>
  ```
  Contoh: 

  ```bash
  [bakmie@noodles] $ touch tabel-fisdas.csv
  ```

- **mkdir**	: create new folder

  ```bash
  mkdir <folder-name>
  ```
    Contoh: 

  ```bash
  [bakmie@noodles] $ mkdir folder-kuliah
  ```



