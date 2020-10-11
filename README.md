# x250-hackintosh

![Catalina 1](https://user-images.githubusercontent.com/59009223/93708288-289c0580-fb5f-11ea-875d-f49e47d31389.png)

![Catalina 2](https://user-images.githubusercontent.com/59009223/93708299-36ea2180-fb5f-11ea-86d6-8d3067f8540b.png)

## Update 9 Oktober 2020

Install macOS BigSur beta 9 Success via OpenCore!

![BigSur Beta 9 via OpenCore!](https://user-images.githubusercontent.com/59009223/95609787-80a49880-0a89-11eb-89f7-1cae45f74a5a.png)

Sebuah tutorial bahasa Indonesia untuk menginstall hackintosh (MacOS) di perangkat non-Apple. Dalam hal ini adalah our beloved Thinkpad X250.

## Disclaimer: Ini bukan buatan saya, saya hanya menyatukan beberapa patch (repack) dan re-share untuk memudahkan user x250 lain dalam hal instalasi hackintosh. Selain itu, semua resiko ditanggung penumpang. Cheers!

## Credit:
- Rehabman
- [banhbaoxamlan](https://github.com/banhbaoxamlan) <- for ssdt patches
- [CLAY-BIOS](https://github.com/CLAY-BIOS) <- for ssdt patches
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
Bootloader | Clover / OpenCore
Versi Bootloader | R5106 / v0.6.1

## Versi MacOS
- BigSur 11.0/10.16 Beta (Tested, OpenCore)
- Catalina 10.15.6 (Tested, Clover)
- Mojave 10.14.6 (Tested, Clover)
- High Sierra (Tested, Clover)

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
- Sediakan Flashdisk berukuran 16/32GB (disarankan). Usahakan dgn merk terkenal dan bukan abal-abal (KW).
- Mengerti setting BIOS
- DWYOR (Do With Your Own Risk), jgn nyalahin saya klo misalkan ada error, resiko ditanggung penumpang

## Buat installer MacOS
- Download EFI yang sudah disediakan disini (Cek tab releases)
- Download BalenaEtcher [disini](https://www.balena.io/etcher/)
- Download Installer macOS (High Sierra - BigSur) [disini](https://www.olarila.com/topic/6278-new-vanilla-olarila-images/)
- Ekstrak file installer yg udah didownload pake winrar/winzip. Jadi format raw
- Siapkan flashdisk, dan buat installer macOS dari balena etcher. Ikuti tutorial-nya, [disini](https://www.antonwibowo.com/cara-buat-usb-bootable-linux-balena-etcher/). Overall sama, bedanya cuma di file ISO yg kita install
- Selesai, lanjut

## Import EFI ke flashdisk
Sebenernya udah ada EFI dari olarila, tetapi kita harus pake EFI yang bener" pas agar stabil di x250. Cara ini hanya ditujukan kepada Windows user (hanya bisa dilakukan di windows). Untuk os lain, bisa search tutorial-nya digoogle.
- Download Minitool Partition Wizard [disini](https://www.partitionwizard.com/free-partition-manager.html)
- Download explorer++ [disini](https://explorerplusplus.com/)
- Siapkan EFI yang telah didownload dari sini (Cermati dalam memilih EFI-nya, karena terdapat 2 pilihan, Clover dan OpenCore. Cek tab release untuk download-nya).
- Ikutin tutorial youtube [disini](https://www.youtube.com/watch?v=zx6HKkWequI). Samakan step-nya, jgn sampai terlewat
- Delete EFI yang ada di flashdisk, terus timpa sama EFI yang ada di repo ini
- Siap untuk nginstall

## Cara Install
- Masuk BIOS, setting boot menu jadi flashdisk yang udah kita siapin tadi.
- Setting BIOS seperti gambar yang ada direpo ini, samain. klo optionnya ada yg ilang/gak sama, skip aja. Credit to [fraisdos125](https://www.tonymacx86.com/members/fraisdos125.250869/)
- Lanjut, klo udh yakin sama settingan BIOS, langsung save and restart. Jgn lupa, pastiin boot priority pertama itu flashdsik yang udah disiapkan buat instal macOS nanti.
- Install kyk biasa, ini harusnya udah hatam sih. Klo masih ga ngerti, bisa search tutorial installnya di youtube. Overall, sama.

## Post Install (Clover dan OpenCore)
- Buka folder files yang ada di flashdisk olarila tadi
- Salin Clover Configurator (Jika pakai Clover, klo OC gaperlu), Hackintool, DPCI Manager ke Applications. Tujuannya untuk memudahkan kalo mau patching".
- Abis itu, buka app Clover Configurator-nya
- Pergi ke tools, pilih mount EFI, masukkan password.
- Kemudian, copy file EFI dari repo ini (atau dari flashdisk), ke folder EFI di HDD/SSD kalian.
- Kalo udah selesai, berarti usb-nya bisa dicabut, dan skrg udah bisa boot tanpa flashdisk

### Install Kext (Clover)
- Copy kext dari folder EFI yang ada di repo ini (Clover/Kext/Other), ke dekstop. Terus, taro juga app kextbeastnya didesktop.
- Buka app-nya, next aja terus, pastiin pilih install ke Library/Extensions, jangan /System/Library/Extensions
- Reboot

### Install Kext (OpenCore)
- Tidak perlu, skip step ini

### Fix Wifi (Clover)
- Pergi kesini https://github.com/OpenIntelWireless
- Install itlwm.kext, bluetooth injector kext, sama heliport app
- Ikutin petunjuk selanjutnya

### Fix Wifi (OpenCore)
- Pergi kesini https://github.com/OpenIntelWireless
- Bisa pilih itlwm atau Airportitlwm. Saran, lebih baik pake itlwm karena Airportitlwm masih beta dan kurang stabil
- Install itlwm.kext, bluetooth injector kext, sama heliport app (Jangan lupa add di config.plist)
- Ikutin petunjuk selanjutnya

## Troubleshoot

#### Jack audio noise
- Option 1: Pastiin audio in/out-nya udah di set ke line out jika pakai earphone/headset. Jika tidak, set lagi ke Internal speaker
- Option 2: ~~Sleep dulu laptopnya, nanti normal lagi~~ Harusnya dengan option 1 udah bisa

## Grup Diskusi / Contact Person
- [Hackintosh Lover](https://t.me/HackintoshLover)
- [DM me on telegram](https://t.me/exxncss)

# Thank you, Terima kasih, 감사합니다, ありがとうございました, شكرا



