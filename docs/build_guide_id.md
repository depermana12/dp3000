# Merakit dp3000 macropad
## Daftar komponen
![](https://i.imgur.com/3XJABrnh.jpg)

|Komponen            |Jumlah| Keterangan
|--------------------|------|-----------
PCB dp3000 |1   | sudah terpasang ic atmega32u4 dan komponen seperti di gambar
case dp300 | 1 | 6 layer akrilik 3mm, sudah termasuk 4 spacer dan 8 baut m3
oled 128x32 | 1 | pixel putih
knob 20mm | 2 | warna silver
kunci L | 1| ukuran 2mm
spacer pcb | 4 | custom resin spacer mounting  PCB ke case
rubber feet | 4 |



## Cara memasang case

Ada 6 lembar akrilik yang akan ditumpuk, urutan pertama dimulai dari kiri atas sesuai pada gambar. Langkah di bawah hanya demonstrasi saja, jangan lupa untuk melepas lapisan pelindung akrilik.

![](https://i.imgur.com/rpznpwih.jpg)

1. Pasang 4 buah mounting spacer pada PCB

![](https://i.imgur.com/wLQgcOHh.jpg)

2. Pasang mounting PCB sesuai ke lubang base akrilik

![](https://i.imgur.com/lJ1YW16h.jpg)

3. Pasang lembar akrilik ke-2 dan ke-3, ratakan lembar akrilik kemudian masukan spacer kuningan

![](https://i.imgur.com/3e7hSEWh.jpg)

4. Pasang Oled display
5. pasang lembar akrilik ke-4 sampai terakhir, pasang 2 buah switch untuk mengunci sementara PCB, pasang 4 baut di atas dan di bawah

![](https://i.imgur.com/Tf542vYh.jpg)

## Oled display

![dp3000 macropad](https://i.imgur.com/lirC7oLh.jpg)

dp3000 secara bawaan mendukung display oled berukuran 128x32. Pengguna dapat mengganti modul oled bawaan ke oled ukuran 128x64, perubahan yang diperlukan :

1. Pastikan modul oled 128x64 punya pinout yang sama, GND, VCC, SCL/SCK, SDA
2. penyolderan pin header female tipe bulat pada pcb dp3000, dan menggunakan pin bekas dioda atau yang seukuran pada pin oled, sehingga level ketinggiannya sama seperti oled bawaan
3. tambahkan kode `#define OLED_DISPLAY_128X64` pada `config.c` 
4. pada `dp3000.c` ganti `oled_write_raw_P(dp3000_logo, sizeof(dp3000_logo));` menjadi:

```
oled_set_cursor(0, (oled_max_lines() - 4) / 2);
oled_write_raw_P(dp3000_logo, sizeof(dp3000_logo));
 ```
4. compile dan flash

Atau silahkan langsung flash firmware dp3000 untuk oled 128x64, [download firmware khusus oled 128x64](https://drive.google.com/drive/folders/1Phvml8fCjT0DUVdHI3QOJoKWOjEaGGep?usp=drive_link)

Ada tambahan beberapa animasi untuk oled_128x64 seperti contoh bongo cat dll.

![dp3000](https://i.imgur.com/yOeAUYdh.jpg)
# Flashing firmware

## Tipe revisi firmware dp3000
dp3000 punya 2 tipe revisi firmware, yang membedakan hanya pada lighting
- rev1 mendukung `rgb_matrix` backlight
- rev2 mendukung `rgblight` underglow
  
## Cara masuk mode bootloader
dp3000 menggunakan bootloader Caterina. Untuk masuk bootloader ada 3 cara:

1. tombol reset fisik  di depan rotary encoder sebelah kiri, tekan 2 kali
2. tekan dan tahan tombol rotary encoder sebelah kanan, lalu tekan tombol rotary encoder sebelah kiri
3. dalam keaadan kabel type c tidak terpasang, tekan dan tahan tombol rotary encoder sebelah kiri, lalu pasang kabel type c. Setelah terkoneksi, lepaskan tombol rotary.

Mode bootloader Caterina akan aktif kurang lebih selama 8 detik

## Cara flashing menggunakan qmk toolbox
Ada beberapa metode untuk flashing, menggunakan GUI dan CLI. Panduan ini hanya akan membahas penggunaan GUI QMK Toolbox.

1. download qmk toolbox dan firmware
   - download aplikasi [qmk toolbox versi terbaru](https://github.com/qmk/qmk_toolbox/releases)
   - download [firmware dp3000 macropad](https://drive.google.com/drive/folders/1hYmq0JSfdpY_xRYRoUmOEOPrWqblNjE2?usp=drive_link)


2. buka qmk_toolbox.exe, install driver
3. open untuk mencari firmware yang akan diflash
4. ceklis auto-flash

![](https://i.imgur.com/Y8OFb1G.jpg)

5. masuk mode bootloader dengan salah satu cara diatas, qmk toolbox akan mendeteksi dan langsung melakukan flash, tunggu sampai flash complete

![](https://i.imgur.com/H3ZOQBz.jpg)

6. Selamat Anda sudah berhasil flashing firmware

> Setiap habis flashing firmware dari versi rgb matrix ke versi underglow atau sebaliknya, lepas dan pasang kembali kabel type c untuk menghilangkan efek lighting sebelumnya.
