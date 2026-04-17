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
= Lebih efisien: file ZIP (langkah 4), karena waktu transfer lebih cepat, beban kerja sistem lebih ringan, lebih praktis (1 file saja).  

4. Hubungan dengan Memory Management  
Ada hubungannya, tapi tidak langsung besar, penjelasannya:  
- Saat copy file:  
Sistem menggunakan RAM sebagai buffer, data dibaca -> masuk RAM -> ditulis ke media tujuan.  
- Banyak file kecil:  
RAM sering bolak-balik load data kecil, lebih banyak proses (context switching), lebih “ribet” untuk memory management.  
- 1 file besar (ZIP):  
Data mengalir lebih stabil (streaming), penggunaan RAM lebih efisien, lebih sedikit interrupt/proses tambahan.  
