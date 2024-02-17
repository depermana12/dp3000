
# Panduan menggunakan VIA
Normal QMK firmware untuk mapping keymap membutuhkan modifikasi kode keymap.c di dalam build environment atau qmk configurator yang dicompile untuk menghasilkan file hex yang akan diflash. Cara ini cukup sulit dan tidak efisien untuk untuk beberapa pengguna.

VIA menutup gap tersebut dengan memberikan kemudahan pengguna untuk mengubah keymap tanpa harus flash firmware. Gui untuk mengatur lighting mode, speed, dan brightness. Programming macros.

Via adalah fitur yang berdiri dengan pondasi qmk firmware

## via configurator
VIA punya dua tipe configurator, web app dan desktop app. Panduan ini menggunakan web app agar lebih sederhana. Untuk desktop app sama saja seperti web app. 

Pastikan terkoneksi internet, dan gunakan browser yang mendukung web hid seperti chrome, safari, opera, edge.

1. buka alamat [VIA configurator](https://usevia.app/)
2. klik authorize device, pilih dp3000 lalu klik connect
   
![dp3000 macropad](https://i.imgur.com/XS7Pe97h.jpg)

1. Tampilan setelah terkoneksi

![dp3000 macropad](https://i.imgur.com/TYVrkC7h.jpg)

4. Pada tampilan di atas, pengguna dapat mengubah langsung setiap key di setiap layer. Jangan lupa juga untuk menambahkan key untuk berpindah layer

## Mapping rotary encoder

pengguna dapat melakukan mapping fungsi rotary encoder di setiap layer berbeda.

1. klik lingkaran rotary encoder
2. masukan fungsi untuk searah jarum jam, berlawan jarum jam, dan tombol rotary.

daftar fungsi [keycode qmk](https://docs.qmk.fm/#/keycodes)

![dp3000 macropad](https://i.imgur.com/6RNFG6Nh.jpg)

## Setting layer switching

![Imgur](https://i.imgur.com/hcUzpdEh.jpg)


Secara bawaan dp3000 macropad mendukung 4 layer, dimulai dari 0 sebagai base default layer

Setting pindah layer dapat dilakukan di via dengan mengatur keymap dengan `LAYERS` keycode yang disediakan diatas.

Agar sederhana, pengguna dapat menggunakan basic keycode:

1. ``MO(nomor_layer)`` Momentary Open berfungsi untuk mengaktifkan layer sementara, saat ditekan akan mengaktifkan layer, saat dilepas akan kembali ke layer sebelumnya
2. ``TO(nomor_layer)`` Turn On berfungsi untuk mengaktifkan layer

Fungsi lengkap dapat dilihat di [QMK docs layer switching](https://docs.qmk.fm/#/feature_layers?id=switching-and-toggling-layers)

![dp3000 macropad](https://i.imgur.com/CVwRCO8h.jpg)

Sebagai contoh gambar diatas adalah default keymap dp3000, berikut penjelasan cara pindah layer:

-  di layer 0 terdapat keycode `` MO(1)`` pada tombol rotary encoder, jadi saat tombol ditekan dan ditahan akan mengaktifkan layer 1
-  saat ada di layer 1, terdapat keycode untuk mengaktifkan layer ``TO(0)``, ``TO(2)``, ``TO(3)``
-  jadi saat menahan tombol ``MO(1)`` akan mengaktifkan layer 1, kemudian menekan tombol ``TO(2)``, Anda telah mengaktifkan dan berada pada layer 2
-  Indikator layer dapat dilihat pada tampilan oled

pengguna bisa mengubah dan mengatur layer switching sesuai kebutuhan dan kreatifitas

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

## Macro shortcut app

Pengguna dapat membuat makro untuk membuka aplikasi spesifik. Cara ini menggunakan shortcut key yang ditempelkan ke aplikasi, dan macro via menggunakan shortcut key tersebut untuk membuka aplikasi.

1. Pengguna harus membuat shortcut key aplikasi


https://github.com/depermana12/dp3000/assets/28618836/631b59ea-c8a3-4074-a2fc-ed78b944b77b


2. Pengguna membuat macro pada via menggunakan macro recorder, kemudian masukan shortcut key yang sudah dibinding dengan aplikasi


https://github.com/depermana12/dp3000/assets/28618836/0c5c954b-eac3-4e96-9dee-aa7475304d08


