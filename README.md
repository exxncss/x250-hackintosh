# x250-hackintosh

![Catalina 1](https://user-images.githubusercontent.com/59009223/93708288-289c0580-fb5f-11ea-875d-f49e47d31389.png)

![Catalina 2](https://user-images.githubusercontent.com/59009223/93708299-36ea2180-fb5f-11ea-86d6-8d3067f8540b.png)

Sebuah tutorial bahasa Indonesia untuk menginstall hackintosh (MacOS) di perangkat non-Apple. Dalam hal ini adalah our beloved Thinkpad X250.

## Special note: Ini bukan buatan saya, saya hanya menyatukan beberapa patch (repack) dan re-share untuk memudahkan user x250 lain dalam hal instalasi hackintosh. Selain itu, semua resiko ditanggung penumpang. Cheers!

## Credit:
- Rehabman
- [banhbaoxamlan](https://github.com/banhbaoxamlan) <- for ssdt patch
- tonymacx86
- Insanelymac
- r/hackintosh
- [Hackintosh Lover](https://t.me/HackintoshLover)

## Hardware

Spesifikasi | Keterangan
----------- | -----------
Processor | Intel Core i5-5300U
Integrated Graphics | Intel HD Graphics 5500
Memory | SK-Hynix 8GB DDR3L
Storage 1 | 128GB Toshiba SSD Sata
Storage 2 | 256GB Midasforce M2.2242 SSD
Wireless Card | Intel AC-7265 Dual Band + Bluetooth
Bootloader | Clover
Versi Bootloader | R5106

## Versi MacOS
- Catalina 10.15.6 (Tested)
- Mojave 10.14.6 (Tested)
- High Sierra (Tested)

## What's work?
- QE/CI Intel HD Graphics 5500
- Power Management
- Sleep, Shutdown, Restart
- Audio (Speaker & Earphone)
- Bluetooth
- Trackpad, Trackball, Gestures
- Indikator baterai
- etc

## Not work?
- VGA
- SD Card Reader

## Bug?
- ~~Bluetooth kadang ga jalan setelah sleep (untung"an, kadang jalan, kadang nggak).~~ Fix pake itlwm kext
- ~~Wifi (Bisa diakalin, pake heliport + kext itlwm, tapi harus load manual setiap abis booting. Selain itu, harus input ssid dan password manual buat hidden SSID. Soal koneksi, aman. Sama kyk windows).~~ Fix pake itlwm kext
- Noise di jack 3.5mm saat colok earphone (fix dgn cara disleep/di set line out-nya ke earphone/headset yg dicolok).

## Persiapan
- Kesabaran yang berlebih (Install hackintosh gabisa dikejar" waktu, harus sabar, chill. Butuh waktu lebih. So, enjoy it).
- Sediakan Flashdisk berukuran 16/32GB (untuk Catalina). Usahakan dgn merk terkenal dan bukan abal-abal (KW).
- Mengerti setting BIOS
- DWYOR (Do With Your Own Risk), jgn nyalahin saya klo misalkan ada error, resiko ditanggung penumpang

## Buat installer MacOS
- Download BalenaEtcher [disini](https://www.balena.io/etcher/)
- Download Installer macOS Catalina [disini](https://drive.google.com/file/d/1-IyiYhgCpOV0o9JoVR6C8heogNLX5DKw/view)
- Ekstrak file installer yg udah didownload pake winrar/winzip. Jadi format raw
- Siapkan flashdisk 16GB, dan buat installer macOS dari balena etcher. Ikuti tutorial-nya, [disini](https://www.antonwibowo.com/cara-buat-usb-bootable-linux-balena-etcher/). Overall sama, bedanya cuma di file ISO yg kita install
- Selesai, lanjut

## Import EFI ke flashdisk
Sebenernya udah ada efi dari olarila, tetapi kita harus pake EFI yang bener" pas agar stabil di x250. Cara ini hanya ditujukan kepada Windows user (hanya bisa dilakukan di windows). Untuk os lain, bisa search tutorial-nya digoogle.
- Download Minitool Partition Wizard [disini](https://www.partitionwizard.com/free-partition-manager.html)
- Download explorer++ [disini](https://explorerplusplus.com/)
- Siapkan EFI yang telah didownload dari sini
- Ikutin tutorial youtube [disini](https://www.youtube.com/watch?v=zx6HKkWequI). Samakan step-nya, jgn sampai terlewat
- Delete EFI yang ada di flashdisk, terus timpa sama EFI yang ada di repo ini
- Siap untuk nginstall

## Setting BIOS
Sebelum install, jgn lupa buat setting BIOS. Settingannya bisa lihat direpo ini. 
Jangan lupa, samain biar gaada error

Note: Kalo ada settingan yang gak sama/gak ada bisa di skip aja.

Credit to [fraisdos125](https://www.tonymacx86.com/members/fraisdos125.250869/)

## Cara Install
- Masuk BIOS, setting boot menu jadi flashdisk yang udah kita siapin tadi.
- Setting BIOS seperti gambar yang ada direpo ini, samain. klo optionnya ada yg ilang/gak sama, skip aja.
- Lanjut, klo udh yakin sama settingan BIOS, langsung save and restart. Jgn lupa, pastiin boot priority pertama itu flashdsik yang udah disiapkan buat instal macOS nanti.
- Install kyk biasa, ini harusnya udah hatam sih. Klo masih ga ngerti, bisa search tutorial installnya di youtube. Overall, sama.

## Post Install
- Buka folder app pendukung yang udah didownload dari repo ini.
- Salin Clover Configurator ke Applications
- Abis itu, buka app-nya
- Pilih mount EFI, masukkan password.
- Kemudian, copy file EFI dari repo ini (atau dari flashdisk), ke folder EFI di HDD/SSD kalian.
- Kalo udah selesai, berarti usb-nya bisa dicabut, dan skrg udah bisa boot tanpa flashdisk

### Install Kext
- Copy kext dari folder EFI yang ada di repo ini (Clover/Kext/Other), ke dekstop. Terus, taro juga app kextbeastnya didesktop.
- Buka app-nya, next aja terus, pastiin pilih install ke Library/Extensions, jangan /System/Library/Extensions
- Reboot

### Fix Wifi
- Pergi kesini https://github.com/OpenIntelWireless
- Install itlwm.kext, bluetooth injector kext, sama heliport app
- Ikutin petunjuk selanjutnya

## Troubleshoot

#### Jack audio noise
- Option 1: Pastiin audio in/out-nya udah di set ke line out
- Option 2: Sleep dulu laptopnya, nanti normal lagi

## Grup Diskusi / Contact Person
- [Hackintosh Lover](https://t.me/HackintoshLover)
- [DM me on telegram](t.me/exxncss) (Sorry for slow response)



