# PROJECT_OS-Galuh Dinata
Project_Based_Learning_Perintah_Dasar_Linux (latihan 1)

# TUGAS PROYEK : LANGKAH IMPLEMENTASI

Gambar : https://drive.google.com/file/d/1YkAtXQ8oGQvMlXe-ZNWMh-_35dPt9OQ4/view?usp=sharing

Dari gambar tersebut kita membuat File dengan nama : project_file_manajement
```
commands : mkdir project_file_manajement
```
Lalu kita masuk ke file dengan nama : project_file_manajement
```
commands : cd project_file_manajement
```
Lalu membuat file baru dengan nama : documents images archives logs
```
commands : mkdir  documents images archives logs
```
Ada juga Ls untuk melihat file.

Lalu kita menggunakan Touch untuk membuat file dari 1 - 20 dengan isi txt, jpg, pdf, dan log.
```
commands : touch file{1..10}.txt file{11..15}.jpg file{16..18}.pdf file{19..20}.log
```
Echo itu memasukan kata ke dalam file.
```
commands : echo "ini adalah document contoh" > file1.txt
commands : echo "data gambar" > file11.jpg
commands : echo "log sistem contoh" > file20.log
```
Lalu ada commands ls -r dan ls -R, apa bedanya? Mengurutkan daftar isi dalam direktori secara terbalik (reverse order) menurut nama file/direktori
Untuk ls -R adalah menampilkan daftar isi direktori secara rekursif, artinya menampilkan isi direktori saat ini serta isi dari semua subdirektori di bawahnya.

Gambar : https://drive.google.com/file/d/1osCl8pzgyrSFb3hvxz75d8B5-Vi74mDZ/view?usp=sharing


1. Direktori yang Ada:
```
- ./documents
- ./images
- ./logs
- archives (dari hasil perintah terakhir ls)
- documents
- images
- logs
```
2. Fungsi Perintah find yang Digunakan:

- Perintah Umum:  
  find . -maxdepth 1 -type f -name "<pattern>" -exec mv {} <directory>/ \;
  
  Penjelasan:
  - find . : mencari di direktori saat ini (root kerja sekarang).  
  - -maxdepth 1 : hanya mencari di dalam direktori saat ini, tidak turun ke subdirektori.  
  - -type f : mencari hanya file (bukan direktori).  
  - -name "<pattern>" : mencari file dengan nama yang sesuai pola, misalnya dengan ekstensi tertentu.  
  - -exec mv {} <directory>/ \; : untuk setiap file yang ditemukan, menjalankan perintah mv (move) untuk memindahkan file tersebut ke direktori tujuan.

3. Penjelasan Perintah-perintah Spesifik:
- Baris 1:  
  find . -maxdepth 1 -type f -name "*.txt" -exec mv {} documents/ \;  
  memindahkan semua file dengan ekstensi .txt ke folder documents/.

- Baris 2:  
  find . -maxdepth 1 -type f -name "*.jpg" -exec mv {} images/ \;  
  memindahkan semua file dengan ekstensi .jpg ke folder images/.

- Baris 3:  
  find . -maxdepth 1 -type f -name "*.pdf" -exec mv {} archives/ \;  
  memindahkan semua file dengan ekstensi .pdf ke folder archives/.

- Baris 4:  
  find . -maxdepth 1 -type f -name "*.log" -exec mv {} logs/ \;  
  memindahkan semua file dengan ekstensi .log ke folder logs/.

4. Perintah ls: 
Setelah memindahkan file sesuai jenisnya, perintah ls digunakan untuk menampilkan isi direktori saat ini, yang berisi folder-folder sesuai dengan tujuan pemindahan file.

1. Membuat Direktori dengan nama organize_files.sh

- Perintah:
  ```
  mkdir organize_files.sh
  ```
- Penjelasan:
  Membuat sebuah direktori baru dengan nama organize_files.sh.  
  (Catatan: biasanya ekstensi .sh digunakan untuk file script, tapi di sini digunakan sebagai nama direktori.)

2. Memberi Hak Eksekusi pada organize_files.sh

- Perintah:
  ```
  chmod +x organize_files.sh
  ```
- Penjelasan: 
  Memberikan hak akses eksekusi ke direktori atau file bernama organize_files.sh.  
  Namun, chmod +x untuk direktori tidak umum dan tidak terlalu berguna. Biasanya digunakan pada file script.

3. Mengetikkan Baris Shebang Bash

- Perintah: 
  ```
  #!/bin/bash
  ```
- Penjelasan:
  Ini adalah baris shebang yang biasanya ditempatkan di awal file skrip shell untuk menunjukkan interpreter yang digunakan (bash).

4. Menampilkan Isi Direktori dengan ls

- Perintah:
  ```
  ls
  ```
- Hasil:  
  Menampilkan isi direktori saat ini, yaitu:  
  
  archives  documents  images  logs  organize_files.sh
  
  Menunjukkan adanya folder-folder tersebut dan sebuah item bernama organize_files.sh (dalam konteks sebelumnya dibuat sebagai direktori).

5. Menghapus Direktori organize_files.sh

- Perintah: 
  ```
  rmdir organize_files.sh
  ```
- Penjelasan:
  Menghapus direktori organize_files.sh yang sebelumnya dibuat.  
  (rmdir hanya bisa menghapus direktori yang kosong.)

6. Memastikan Isi Direktori Setelah Penghapusan

- Perintah:
  ```
  ls
  ```
- Hasil:  
  
  archives  documents  images  logs
  
  Direktori organize_files.sh sudah tidak ada lagi.

7. Membuka Editor Nano untuk Membuat/Mengedit File project_os_auto.sh

- Perintah:  
```  
  nano project_os_auto.sh
  ```
- Penjelasan: 
  Membuka editor teks nano untuk membuat atau mengedit file script bernama project_os_auto.sh.

8. Memberi Hak Eksekusi pada project_os_auto.sh

- Perintah:  
  ```
  chmod +x project_os_auto.sh
  ```
- Penjelasan:  
  Memberikan hak akses eksekusi agar file script tersebut dapat dijalankan.

 9. Menjalankan Script project_os_auto.sh dengan Hak Sudo

- Perintah:
  ```
  sudo ./project_os_auto.sh
  ```
- Penjelasan: 
  Menjalankan script project_os_auto.sh dengan hak akses administratif (superuser).  
  Pengguna diminta memasukkan password.

  

