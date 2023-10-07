# Daftar isi

- [Daftar isi](#daftar-isi)
- [Panduan menggunakan VIA](#panduan-menggunakan-via)
  - [via configurator](#via-configurator)
  - [Tab alat via configurator](#tab-alat-via-configurator)
  - [Manual load json](#manual-load-json)
  - [Mapping rotary encoder](#mapping-rotary-encoder)
  - [Control RGB lighting](#control-rgb-lighting)
  - [Macro](#macro)

# Panduan menggunakan VIA
Normal QMK firmware untuk mapping keymap membutuhkan modifikasi kode keymap.c di dalam build environment atau qmk configurator yang dicompile untuk menghasilkan file hex yang akan diflash. Cara ini cukup sulit dan tidak efisien untuk untuk beberapa pengguna.

VIA menutup gap tersebut dengan memberikan kemudahan pengguna untuk mengubah keymap tanpa harus flash firmware. Gui untuk mengatur lighting mode, speed, dan brightness. Programming macros.

Via adalah fitur yang berdiri dengan pondasi qmk firmware

## via configurator
VIA punya dua tipe configurator, web app dan desktop app. Panduan ini menggunakan web app agar lebih sederhana. Untuk desktop app sama saja seperti web app. 

Pastikan terkoneksi internet, dan gunakan browser yang mendukung web hid seperti chrome, safari, opera, edge.

1. buka alamat [VIA configurator](https://usevia.app/)
2. klik authorize device, pilih dp3000 lalu klik connect

> - Untuk firmware dp3000 rev1 sudah auto-connect dengan VIA, dapat langsung terdeteksi ketika klik `authorize device`
> - Untuk firmware dp3000 rev2 masih harus manual load json agar dapat terdeteksi. (auto-connect masih proses, ETA akhir November saat breaking changes q4 qmk)
> - baca [panduan load json untuk dp3000 rev2](#manual-load-json)
   
![dp3000 macropad](https://i.imgur.com/XS7Pe97h.jpg)

1. Tampilan setelah terkoneksi

![dp3000 macropad](https://i.imgur.com/TYVrkC7h.jpg)

4. Pada tampilan di atas, pengguna dapat mengubah langsung setiap key di setiap layer. Jangan lupa juga untuk menambahkan key untuk berpindah layer

## Tab alat via configurator

- Tampilan bawaan ada 3 tab, yaitu `CONFIGURE`, `KEY TESTER`, dan `SETTINGS`. 
- Tab `DESIGN` dapat diaktifkan dengan menuju tab `SETTINGS` kemudian toggle show design tab

![dp3000 macropad](https://i.imgur.com/6lF5fMDh.jpg)

## Manual load json
Untuk firmware dp3000 rev2 sedang dalam proses untuk dapat auto-connect, karena belum ditambahkan ke official via database (auto-connect ETA akhir november 2023)

Jadi saat ini masih harus manual upload json file dp3000-rev2, file json ini bersisi definisi agar via dapat mengenali macropad dp3000. Pengguna hanya perlu sekali upload saja. Berikut panduannya

1. download file [dp3000-rev2.json](https://drive.google.com/uc?id=1wcIDpMSniR9_wCjKMlnjyhLKqqTzrHiz&export=download)
2. buka web [https://usevia.app](https://usevia.app/)
3. Pada tab `SETTINGS` toggle untuk mengaktifkan **Show Design tab**

![dp3000 macropad](https://i.imgur.com/ei5MmHch.jpg)

4. menuju tab `DESIGN` klik load untuk mengupload file dp3000-rev2.json

![dp3000 macropad](https://i.imgur.com/53dmCSch.jpg)

5. setelah terdeteksi, silahkan menuju tab `CONFIGURE` untuk mulai mapping

## Mapping rotary encoder

pengguna dapat melakukan mapping fungsi rotary encoder di setiap layer berbeda.

1. klik lingkaran rotary encoder
2. masukan fungsi untuk searah jarum jam, berlawan jarum jam, dan tombol rotary.

daftar fungsi [keycode qmk](https://docs.qmk.fm/#/keycodes)

![dp3000 macropad](https://i.imgur.com/6RNFG6Nh.jpg)

## Control RGB lighting

![dp3000 macropad](https://i.imgur.com/mpVepRph.jpg)

dp3000 punya dua opsi lighting

- rev1 mendukung rgb_matrix, pada menu via bernama `BACKLIGHT`
- rev2 mendukung rbglight, pada menu via bernama `UNDERGLOW`

Beberapa kontrol pengaturan led seperti:
- Brightness untuk mengatur tingkat  cahaya led
- Effect untuk mengubah mode led
- Effect speed untuk mengubah kecepatan pada beberapa mode led
- Color untuk statis satu warna

## Macro
Macro adalah program untuk menjalankan serangkaian perintah dengan sekali tekan key. Digunakan untuk mengotomatisasi perintah atau shortcut sehingga menghemat waktu dan key.

sebagai contoh pengguna dapat membuat perintah copy ctrl+c ke dalam salah satu tombol. Pengguna juga dapat membuat perintah untuk membuat output teks ke dalam salah satu tombol.

Via punya dua metode untuk memprogram macro

1. Macro recorder

Metode ini akan merekam kombinasi tombol yang ditekan oleh pengguna

![dp3000 macropad](https://i.imgur.com/abDotLZh.jpg)

2. Manual macro entry

Pengguna dapat memasukan fungsi kode keycode qmk sesuai contoh pada via

![dp3000 macropad](https://i.imgur.com/mhaOZPZh.jpg)

## Macro buka app

Pengguna dapat membuat makro untuk membuka aplikasi spesifik. Cara ini menggunakan shortcut key yang ditempelkan ke aplikasi, dan macro via menggunakan shortcut key tersebut untuk membuka aplikasi.

1. Pengguna harus membuat shortcut key aplikasi


https://github.com/depermana12/dp3000/assets/28618836/631b59ea-c8a3-4074-a2fc-ed78b944b77b


2. Pengguna membuat macro pada via menggunakan macro recorder, kemudian masukan shortcut key yang sudah dibinding dengan aplikasi


https://github.com/depermana12/dp3000/assets/28618836/0c5c954b-eac3-4e96-9dee-aa7475304d08


