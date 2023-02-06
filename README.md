# x250-hackintosh 

## Notes: My machine is broken due to a shortage of IC Power. So I can't update this repo.

Sebuah tutorial bahasa Indonesia untuk menginstall hackintosh (MacOS) di perangkat non-Apple. Dalam hal ini adalah our beloved Thinkpad X250.

## Disclaimer 1: Patch SSDT yang digunakan bukan punya saya, saya hanya menyatukan beberapa patch (repack) dari beberapa modder untuk memudahkan user x250 lain dalam hal instalasi hackintosh. Credits ada di deskripsi bawah.

## Disclaimer 2: Hanya karena spesifikasi laptop kita sama, bukan berarti langsung "bisa semua", atau bakalan "work semua". Mungkin akan muncul "minor" atau (mungkin) major bugs yang tidak dapat diprediksi sebelumnya. Resiko ditanggung penumpang~

## UPDATE May 2021
Saya udah gak update versi bootloader clover lagi, full migrasi ke OpenCore karena dokumentasi yang mudah dimengerti.

## High Sierra (Clover)
![High Sierra](https://user-images.githubusercontent.com/59009223/96335167-bd334e00-10a0-11eb-8634-17cf3452f582.png)

## Mojave (OC/Clover)
![Mojave](https://user-images.githubusercontent.com/59009223/103622044-b5c96580-4f68-11eb-82d3-bc549c76262c.png)

## Catalina (OC/Clover)
![Catalina](https://user-images.githubusercontent.com/59009223/93708288-289c0580-fb5f-11ea-875d-f49e47d31389.png)

## BigSur (OC)
![BigSur 2](https://user-images.githubusercontent.com/59009223/119263992-8495bd00-bc0b-11eb-9d12-b6d29343b3bb.png)

## Monterey Beta (OC)
![Monterey](https://user-images.githubusercontent.com/59009223/129425860-a5d6a76c-6924-4ba6-8057-9604e83203ca.png)

## Credits:
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
Versi Bootloader | R5106 / v0.7.2

Note: utk versi clover, diset ke R5106 karena klo di set ke latest version ga bisa booting utk bbrp user. Jadi, kalian bisa update sendiri yaa beserta kexts"nya

## Versi MacOS
- Monterey (Tested, OpenCore)
- Bigsur (Tested, OpenCore)
- Catalina (Tested, Clover)
- Mojave (Tested, Clover)
- High Sierra (Tested, Clover)

## What's Working?
- QE/CI Intel HD Graphics 5500 (High Sierra, Mojave, Catalina, BigSur)
- Power Management (High Sierra, Mojave, Catalina, BigSur)
- Sleep, Shutdown, Restart (High Sierra, Mojave, Catalina, BigSur)
- Audio Speaker & Earphone (High Sierra, Mojave, Catalina, BigSur)
- Bluetooth (Mojave, Catalina, BigSur)
- Trackpad, Trackball, Gestures (High Sierra, Mojave, Catalina, BigSur)
- Indikator baterai (High Sierra, Mojave, Catalina, BigSur)
- Camera (Mojave, Catalina, BigSur)
- Mini DP (to VGA/HDMI)
- etc

## Not Working?
- VGA port

## Bugs?
- Bluetooth ngadat saat dijalanin bareng wifi. Itu wajar, limitasi dari itlwm [source](https://openintelwireless.github.io/itlwm/FAQ.html#usage)
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
- Buka terminal, ketik ''sudo pmset -a hibernatemode 0''
- Buka folder files yang ada di flashdisk olarila tadi
- Salin Clover Configurator/OpenCore Configurator, Hackintool, DPCI Manager, ioregistryexplorer, ESP Mounter ke Applications. Tujuannya untuk memudahkan kalo mau patching".
- Buka ESP Mounter, pilih mount EFI (Flashdisk dan HDD/SSD), masukkan password. ![Mount EFI](https://user-images.githubusercontent.com/59009223/129425703-1bd88f89-7f36-4e18-b34d-f449e8c97e2f.png)
- Kemudian, copy file EFI dari repo ini (dari flashdisk), ke folder EFI di HDD/SSD kalian.
- Kalo udah selesai, berarti usb-nya bisa dicabut, dan skrg udah bisa boot tanpa flashdisk

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

## Grup Diskusi / Contact Person
- [Hackintosh Lover](https://t.me/HackintoshLover)
- [DM me on telegram](https://t.me/exxncss)

# Thank you, Terima kasih, 감사합니다, ありがとうございました, شكرا
