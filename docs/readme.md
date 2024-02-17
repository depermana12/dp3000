# Introduction dp3000

dp3000 macropad  didesain full feature dan compact, tidak terlalu banyak switch

sekaligus jadi dev board

untuk nyoba fitur hardware dan firmware. Itu kenapa dp3000 didesain punya beberapa opsi

opsi lighting underglow atau rgbmatrix

opsi hot-swap socket

opsi ukuran modul oled

opsi firmware via, vial

## Embedded ATmega32u4

Dilihat lebih detil, dp3000 tidak memakai shield promicro... tapi ic promicro dipasang langsung di pcb dp3000

jadi lebih slim dan seksi

minimalis, elegan

alias manfaatin promicro yang port micro usbnya copot (type c pride)

biar ga mubazir

sayang 70rban

## Dev board

Untuk yang suka ngoprek firmware, atau lagi sambil belajar C, ini macropad cocok banget.

source code qmk terlampir

compiled .hex yang tinggal flash jg ada

firmware rev1 dan rev 2 sudah merged dengan repo qmk dan via

jadi sudah auto-detect untuk digunakkan langsung lewat web https://usevia.app

pcb juga mendukung untuk dimodif, hotswap socket bisa diganti ke varian choc socket

Oled bisa diganti ke ukuran 128x64

`rgb_matrix` bisa digabung `rgblight` underglow, dengan menyolder kabel jumper (tutorialnya menyusul)

icsp header

