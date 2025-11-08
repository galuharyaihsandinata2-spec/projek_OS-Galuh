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

Gambar : https://drive.google.com/file/d/1GNAaADfanIQ6iMeH0IGLsCeUd71TDgF8/view?usp=sharing

 1. Pesan Error mv

- Banyak pesan error seperti:  
    ```
  mv: './documents/doc2.txt' and 'documents/doc2.txt' are the same file
    ```
- Penjelasan:
  Perintah mv mencoba memindahkan file ke lokasi yang sama dengan nama file asalnya, sehingga file sumber dan tujuan sama persis. Oleh karena itu, mv menolak operasi tersebut karena tidak ada perubahan.

2. Output Informasi Setelah Proses
- Terdapat output:  
    ```
  === Membuat Laporan ===
  === Proyek Selesai! ===
    ```
- Penjelasan:
  Ini kemungkinan adalah output dari script yang menandakan proses sudah selesai dan laporan sudah dibuat.

3. Daftar Isi Direktori Setelah Proses
- Perintah:  
    ```
  ls
    ```
- Output:  
  
  archives  documents  images  logs  project_os_auto.sh
  
- Penjelasan:
  Menampilkan folder-folder dan file skrip yang ada di direktori kerja saat ini.

4. Menghapus File project_os_auto.sh
- Perintah:  
    ```
  rm project_os_auto.sh
    ```
- Menghapus file project_os_auto.sh dari direktori.

5. Membuka dan Mengedit File search_files.sh

- Perintah:  
    ```
  nano search_files.sh
    ```
- Penjelasan:  
  Membuka editor teks nano untuk membuat atau mengedit file skrip bernama search_files.sh.

6. Memberi Hak Eksekusi pada File search_files.sh

- Perintah:  
    ```
  chmod +x search_files.sh
    ```
- Memberikan permission execute sehingga file bisa dijalankan sebagai skrip.

7. Menjalankan Skrip search_files.sh

- Perintah:  
    ```
  ./search_files.sh
    ```
- Error yang Muncul:  
    ```
  ./search_files.sh: line 5: cd: /home/hozz/project_file_manajement: No such file or directory
    ```
- Penjelasan:
  Pada baris ke-5 dari skrip search_files.sh terdapat perintah cd yang mencoba berpindah ke direktori /home/hozz/project_file_manajement  
  Namun direktori tersebut tidak ada (salah ketik atau direktori belum dibuat).  
  Perhatikan nama direktori ada salah ketik "manajement" (seharusnya mungkin "management").

Gambar : https://drive.google.com/file/d/1eqJkQocZ-Ql49ayY5MMUcaSqdfnSlgef/view?usp=sharing

1. Error pada Baris 5 script search_files.sh

- Pesan error:  
    ```
  ./search_files.sh: line 5: cd: /home/hozz/project_file_management: No such file or directory
    ```
- Penjelasan:
  Script mencoba berpindah ke direktori /home/hozz/project_file_management namun direktori tersebut tidak ada.  
  Ini mengakibatkan perintah cd gagal dan mungkin mempengaruhi jalannya script selanjutnya.

2. Tampilan Menu Pilihan Pencarian File

- Tampil sebagai teks:  
    ```
  === PENCARIAN FILE ===
  1. Cari berdasarkan nama
  2. Cari berdasarkan ukuran
  3. Cari berdasarkan isi konten
  Pilih opsi (1/2/3):
    ```

- Penjelasan:
  Script menawarkan tiga opsi pencarian file berdasarkan:  
  1. Nama file  
  2. Ukuran file  
  3. Isi konten file

3. Contoh Pencarian Berdasarkan Nama (Opsi 1)

- Input yang diberikan:  
    ```
  files1.txt
    ```
- Output hasil pencarian:  
    ```
  ./documents/file1.txt
    ```
- Penjelasan:
  Pencarian berhasil menemukan file yang cocok sesuai pola yang dimasukkan.

4. Pencarian Ukuran (Opsi 2) dengan Input '10mb'

- Input ukuran:  
    ```
  10mb
    ```
- Pesan error yang muncul:  
    ```
  find: Invalid argument `10mb' to -size
    ```
- Penjelasan:
  Perintah find menganggap parameter 10mb untuk opsi -size tidak valid.  
  Format yang benar untuk ukuran file di find biasanya seperti +10M (lebih besar dari 10MB) atau -10M (kurang dari 10MB).  
  Huruf harus sesuai dengan format c, k, M, G tanpa tambahan b (byte) dan huruf harus kapital untuk megabytes (M).

5. Catatan lain pada tampilan

- Terdapat pengulangan jalannya script dengan prompt input dan output yang mirip, menunjukkan user mencoba menjalankan script berulang kali dengan opsi dan input berbeda.

Rekomendasi Perbaikan Script search_files.sh

- Perbaiki baris cd agar menuju direktori yang benar dan pastikan direktori tersebut ada, misalnya:  
    ```
  cd /home/hozz/project_file_manajement
  
  diubah menjadi  
  
  cd /home/hozz/project_file_manajemen
    
  (atau direktori yang memang ada).
  ```
- Perbaiki validasi input ukuran untuk find -size, contoh input yang benar:  
  - +10M untuk file lebih besar dari 10 Megabytes  
  - -500k untuk file kurang dari 500 Kilobytes

- Tambahkan validasi input di script agar memberi pesan error yang jelas jika format input salah.

Gambar : https://drive.google.com/file/d/1MKG1q45i1H6pW5Kmjj5K-Rnag1Ipqap-/view?usp=sharing

1. Error Awal saat Jalankan Skrip

- Pesan error:  
   ```
  find: Invalid argument '-500kb' to -size
   ```
- Penjelasan:  
  Perintah find tidak mengenali argumen -500kb sebagai ukuran yang valid pada opsi -size.  
  Format ukuran yang benar untuk find -size adalah seperti -500k (tanpa huruf b), dengan huruf ukuran berupa c, k, M, G dll dan tanpa tambahan b.

2. Error Baris 5 Skrip

- Pesan error:  
   ```
  ./search_files.sh: line 5: cd: /home/hozz/project_file_management: No such file or directory
   ```
- Penjelasan:  
  Perintah cd gagal karena direktori /home/hozz/project_file_management tidak ada. Skrip bergantung pada direktori yang ada agar pencarian berjalan pada lokasi tersebut.

3. Tampilan Menu Pencarian File

- Ditampilkan opsi pencarian file:  
   ```
  === PENCARIAN FILE ===
  1. Cari berdasarkan nama
  2. Cari berdasarkan ukuran
  3. Cari berdasarkan isi konten
  Pilih opsi (1/2/3):
   ```
- Pengguna memilih opsi 2 (berdasarkan ukuran).

4. Input Batas Ukuran File

- Input yang dimasukkan:  
   ```
  -500k
   ```
- Penjelasan:  
  Artinya mencari file dengan ukuran kurang dari 500 Kilobytes.

5. Hasil Pencarian File Berdasarkan Ukuran

- Daftar file yang ditemukan (ukuran < 500KB) di berbagai folder: 
  - File .log di folder logs/
  - File .txt di folder documents/
  - File .jpg di folder images/
  - File .pdf di folder archives/
 
Gambar : https://drive.google.com/file/d/1ULUeOwt-LPaOKy_vFqPy7pejcvz_gMno/view?usp=sharing

1. Menjalankan Script search_files.sh

- Perintah:  
  ```
  ./search_files.sh
  
- Error yang muncul:  
  ```
  ./search_files.sh: line 5: cd: /home/hozz/project_file_management: No such file or directory
  
- Penjelasan:  
  Baris ke-5 script mencoba berpindah direktori ke /home/hozz/project_file_management, namun direktori tersebut tidak ditemukan atau belum dibuat.  
  Jadi, cd gagal, tapi script tetap berjalan.

- Setelah error tersebut, ditampilkan menu pencarian file:  
  ```
  === PENCARIAN FILE ===
  1. Cari berdasarkan nama
  2. Cari berdasarkan ukuran
  3. Cari berdasarkan isi konten
  Pilih opsi (1/2/3):
  
- Pengguna memilih opsi 3 (cari berdasarkan isi konten), dan diminta memasukkan kata kunci pencarian.

- Contoh input kata kunci:
  ```  
  - file1.txt pada percobaan pertama  
  - yes pada percobaan kedua  

- Hasil Pencarian: 
  Hasil pencarian ditampilkan (walaupun direktori tidak ditemukan, kemungkinan script mencari di direktori kerja saat ini).

2. Membuat dan Menjalankan Script generate_report.sh

- Perintah membuat/mengedit file:  
  ```
  nano generate_report.sh
  
- Memberikan izin eksekusi pada file:  
  ```
  chmod +x generate_report.sh
  
- Menjalankan script:  
  ```
  ./generate_report.sh
  
- Error yang muncul saat script dijalankan:  
  ```
  ./generate_report.sh: line 5: cd: /home/hozz/project_file_management: No such file or directory
  
- Meskipun ada error, script tetap menyatakan laporan telah selesai dibuat dan disimpan dalam file report.txt.

3. Melihat Isi File report.txt

- Perintah:  
  ```
  cat report.txt
  
- Hasil tampilan:  
  ```
  === LAPORAN FILE SISTEM ===
  Tanggal: Sat Nov  8 09:37:06 AM UTC 2025
  
- Artinya:  
  File laporan berhasil dibuat dan berisi header laporan yang menunjukkan tanggal pembuatan laporan.

Gambar : https://drive.google.com/file/d/120K1ZTztl7Y-IwGAPwNjM9IoB7qi_Ax2/view?usp=sharing

1. Pesan Selesai Pembuatan Laporan*

- Teks:  
    ```
  === Selesai! Laporan disimpan di report.txt ===
  
- Penjelasan:  
  Menandakan bahwa proses pembuatan laporan file sistem sudah selesai dan hasilnya disimpan ke file report.txt.

2. Menampilkan Isi File report.txt

- Perintah:  
    ```
  cat report.txt
  
- Output berisi laporan sistem file dengan format sebagai berikut:

3. Isi Laporan File Sistem:

- Header: 
  
  === LAPORAN FILE SISTEM ===
  Tanggal: Sat Nov  8 09:37:06 AM UTC 2025
  
  Menampilkan tanggal dan waktu pembuatan laporan.

- Jumlah File dan Folder: 
    ```
  --- Jumlah File dan Folder ---
  41
  
  Total ada 41 file dan folder yang terhitung di dalam direktori kerja.

- Ukuran Total Folder: 
    ```
  --- Ukuran Total Folder ---
  44K
  .
  
  Total ukuran folder saat ini dan isinya adalah 44 Kilobytes.

- Daftar 10 File Terbesar: 
    ```
  --- Daftar 10 File Terbesar ---
  4.0K    ./search_files.sh
  4.0K    ./report.txt
  4.0K    ./logs/file20.log
  4.0K    ./images/file11.jpg
  4.0K    ./generate_report.sh
  4.0K    ./documents/file1.txt
  0       ./logs/file19.log
  0       ./images/file15.jpg
  0       ./images/file14.jpg
  0       ./images/file13.jpg
  
  Menampilkan 10 file terbesar (berukuran 4.0K dan beberapa file 0 byte).

- Statistik Berdasarkan Ekstensi File: 
  
  --- Statistik Berdasarkan Ekstensi ---
  TXT: 11
  JPG: 5
  PDF: 3
  LOG: 2
  
  Statistik jumlah file berdasarkan ekstensi (type file) di dalam direktori.
    

