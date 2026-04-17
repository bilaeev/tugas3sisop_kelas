# Tugas Sisop 3
## Task 1
1. Siapkan 1 folder berisi 10 file sembarang di laptop/komputer Anda.  
2 Copy ke-10 file tersebut ke media penyimpanan eksternal (HP, Flashdisk, HDD, atau SD Card).  
3. Compress 10 file tadi menjadi satu file zip atau rar.  
4. Copy file zip tersebut ke media penyimpanan eksternal yang sama.  

> Screenshot saat proses transfer (copy) sedang berlangsung pada langkah 2 dan langkah 4.

LANGKAH 2  
<img width="285" height="113" alt="Screenshot 2026-04-16 060651" src="https://github.com/user-attachments/assets/c56d62cb-bb06-4cd7-83ef-c5fcd7bab20f" />

LANGKAH 4  
<img width="285" height="110" alt="Screenshot 2026-04-16 060844" src="https://github.com/user-attachments/assets/81bc7186-c370-4362-9acb-f54fb70a22a3" />  

> Soal : Berdasarkan hasil tersebut apakah ada perbedaan waktu? Jelaskan mengapa dan jelaskan mana yang lebih efisien.
1. Hasil Pengamatan :  
Terdapat perbedaan waktu antara:  
- Langkah 2 (copy 10 file satuan) = lebih lama.  
- Langkah 4 (copy file zip) = lebih cepat.
  
2. Alasan Terjadinya Perbedaan :  
- Jumlah File vs Ukuran File.  
  * Saat copy 10 file terpisah, sistem harus membaca file satu per satu, membuat 10 proses penyalinan, mengatur metadata tiap file (nama, tanggal, izin, dll).  
  * Saat copy 1 file zip, sistem hanya menyalin 1 file saja, lebih sedikit overhead.
- Overhead Sistem File.  
  * Banyak file kecil = lebih banyak aktivitas pada sistem file.
  * 1 file besar = lebih “streaming” = proses lebih lancar.  
- Kecepatan Transfer Storage.  
Media seperti flashdisk/HDD cenderung lebih lambat saat menangani banyak file kecil, lebih optimal untuk file besar berurutan.  

3. Mana yang Lebih Efisien?  
= Lebih efisien file ZIP (langkah 4), karena waktu transfer lebih cepat, beban kerja sistem lebih ringan, lebih praktis (1 file saja).  

4. Hubungan dengan Memory Management  
Ada hubungannya, tapi tidak langsung besar, penjelasannya:  
- Saat copy file:  
Sistem menggunakan RAM sebagai buffer, data dibaca -> masuk RAM -> ditulis ke media tujuan.  
- Banyak file kecil:  
RAM sering bolak-balik load data kecil, lebih banyak proses (context switching), lebih “ribet” untuk memory management.  
- 1 file besar (ZIP):  
Data mengalir lebih stabil (streaming), penggunaan RAM lebih efisien, lebih sedikit interrupt/proses tambahan.

5. Kesimpulan:
   Copy banyak file kecil lebih lambat dibanding 1 file besar (ZIP), penyebab utamanya adalah overhead sistem file & jumlah proses. Sehingga file ZIP lebih efisien untuk transfer. Kemudian memory management berpengaruh dalam buffering, tapi bukan faktor utama.  







## Task 2
1. Buka Browser anda dan buka 10 tab dan buka apa saja, buka task manager dan lihat alokasi memory dan CPUnya.  
2. Buka Browser 10 Browser (bukan tab) dan buka setiap browser sama persis dgn sebelumnya. lakukan langkah yang sama.
   
> Screenshot hasil task manager langkah 1 dan langkah 2

LANGKAH 1 (10 TAB DALAM 1 BROWSER)  
<img width="648" height="156" alt="Screenshot 2026-04-16 061732" src="https://github.com/user-attachments/assets/90159710-a869-453f-b387-591a41555fa8" />  

LANGKAH 2 (10 BROWSER TERPISAH)  
<img width="648" height="164" alt="Screenshot 2026-04-17 073151" src="https://github.com/user-attachments/assets/325dd49f-9297-47f9-a07a-a007c19dc289" />  

> Soal : Analisa mana yang lebih berat dan berikan penjelasan!  
1. Hasil Pengamatan :  
- Terdapat perbedaan penggunaan resource antara:  
Langkah 1 (10 tab dalam 1 browser) = lebih ringan.  
Langkah 2 (10 browser terpisah) = lebih berat.

2. Alasan terjadinya perbedaan :  
- Manajemen Proses.  
  * 1 browser dengan 10 tab masih dalam satu aplikasi utama, sehingga beberapa resource bisa digunakan bersama (shared process).  
  * 10 browser berarti membuka 10 aplikasi terpisah, masing-masing memiliki proses sendiri sehingga lebih banyak memakan CPU dan memory.  
- Penggunaan Memory (RAM).  
  * Pada 10 tab, beberapa komponen seperti engine browser, cache, dan library digunakan bersama.  
  * Pada 10 browser, setiap browser memuat engine sendiri-sendiri sehingga penggunaan RAM meningkat drastis.  
- Penggunaan CPU.  
  * Banyak browser berarti lebih banyak proses aktif yang berjalan bersamaan.  
  * Hal ini menyebabkan CPU bekerja lebih keras dibandingkan hanya menangani tab dalam satu browser.  
- Overhead Aplikasi.  
  * Setiap browser memiliki overhead (startup process, extension, rendering engine).  
  * Membuka 10 browser = 10 kali overhead, sedangkan 10 tab hanya menambah beban kecil di dalam satu aplikasi.
    
3. Mana yang Lebih Berat?  
= Yang lebih berat adalah langkah 2 (membuka 10 browser), karena penggunaan RAM lebih besar, CPU lebih terbebani, dan jumlah proses sistem lebih banyak.

4. Hubungan dengan Memory Management  
Ada hubungannya dan cukup signifikan, penjelasannya:  
- Pada 10 tab dalam 1 browser:  
  * Memory management lebih efisien karena banyak resource yang di-share.  
  * Sistem hanya mengatur satu aplikasi utama dengan beberapa sub-proses.  
- Pada 10 browser terpisah:  
  * Setiap browser meminta alokasi memory sendiri-sendiri.  
  * Terjadi pemborosan RAM karena tidak ada sharing resource.  
  * Memory management menjadi lebih kompleks karena harus menangani banyak proses independen.  
- Dampak ke sistem:  
  * RAM lebih cepat penuh pada 10 browser.  
  * Jika RAM hampir habis, sistem bisa menggunakan virtual memory (paging) yang membuat kinerja semakin lambat.  

5. Kesimpulan:  
Penggunaan 10 tab dalam satu browser lebih efisien dibanding membuka 10 browser karena lebih hemat resource dan lebih optimal dalam memory management.





## Task 3
1. Copy 1 file besar bebas diatas 500MB ke penyimpanan eksternal (HP, Flashdisk, HDD, atau SD Card).  
2. Pindahkan ke colokan yang ada di laptop seperti USB Type A dan USB Type C (jangan pada tempat yang sama).  
3. Screenshot bukti hasil setiap lubang USB yang anda test.

> Screenshot bukti hasil setiap lubang USB yang anda test.

USB TYPE A (USB 2.0)  
<img width="1904" height="995" alt="WhatsApp Image 2026-04-17 at 12 57 09" src="https://github.com/user-attachments/assets/75548906-f5c1-4d52-99ce-2ccc5ba24342" />  

USB TYPE C (USB 3.1)  
<img width="1909" height="973" alt="2WhatsApp Image 2026-04-17 at 12 56 48" src="https://github.com/user-attachments/assets/3ea45b86-014d-4e53-833b-625747aa6b95" />  

> Soal : Jelaskan perbedaan hasil dari setiap lubang USB yang anda test  
1. Hasil Pengamatan :  
Terdapat perbedaan kecepatan transfer antara:  
USB Type A (USB 2.0) = lebih lambat.  
USB Type C (USB 3.1) = lebih cepat.  
2. Alasan terjadinya perbedaan :  
- Versi USB.  
  * USB Type A yang digunakan adalah versi USB 2.0 dengan kecepatan maksimal sekitar 480 Mbps.  
  * USB Type C yang digunakan adalah versi USB 3.1 dengan kecepatan bisa mencapai hingga 5–10 Gbps.  
- Bandwidth (kecepatan transfer data).  
  * USB 2.0 memiliki bandwidth kecil sehingga proses transfer file besar membutuhkan waktu lebih lama.  
  * USB 3.1 memiliki bandwidth jauh lebih besar sehingga transfer file lebih cepat.  
- Teknologi dan jalur data.  
  * USB 3.1 memiliki jalur data lebih banyak (full duplex) dibanding USB 2.0.  
  * Hal ini membuat proses kirim data lebih efisien dan stabil.  
- Efisiensi transfer file besar.  
  * File besar (>500MB) lebih terasa perbedaannya karena membutuhkan kecepatan transfer tinggi.  
  * Port yang lebih cepat akan menghemat waktu secara signifikan.  
3. Mana yang Lebih Efisien?  
= USB Type C (USB 3.1) lebih efisien karena memiliki kecepatan transfer lebih tinggi, waktu lebih singkat, dan performa lebih optimal untuk file berukuran besar.  
4. Hubungan dengan Memory Management :  
Ada hubungannya, tetapi tidak terlalu dominan, penjelasannya :
- Saat proses transfer file:  
  * Sistem menggunakan RAM sebagai buffer untuk menampung data sementara sebelum dikirim ke perangkat tujuan.  
- Pada USB Type C (lebih cepat):  
  * Data mengalir lebih cepat dari RAM ke perangkat eksternal.  
  * Buffer di RAM cepat dikosongkan sehingga lebih efisien.  
- Pada USB Type A (lebih lambat):  
  * Data tertahan lebih lama di buffer RAM karena kecepatan kirim rendah.  
  * Bisa terjadi antrian data (bottleneck) antara proses baca dan tulis.  
- Dampak ke sistem:  
  * Jika transfer berlangsung lama dan RAM terbatas, sistem bisa menggunakan virtual memory.  
  * Hal ini dapat memperlambat kinerja sistem secara keseluruhan.  
5. Kesimpulan:  
Perbedaan port USB sangat mempengaruhi kecepatan transfer file. USB Type C (USB 3.1) lebih cepat dan efisien dibanding USB Type A (USB 2.0). Memory management berperan dalam proses buffering data, tetapi bukan faktor utama yang menentukan kecepatan transfer.
