# LokisAsicTester 

Большой сборник TestJIG или TestFixtures в одном удобном месте

# Как использовать
Взять контрольную плату от S17Pro, зашить официальный образ sd картой и записать этот проект на sd.
Веб интерфейс доступен по локальной сети, пароль root/root.
Можно добавлять конфигурации паттернов в /config, инструмент tools в /testtool и паттерны в корень как требкет testJIG и при перезагрузке прошивка все подхватит и добавит в выпадающее меню

# Известные проблемы и нюансы
- Если сменить через скрипт пароль у root. все ломается, sd недоступна по ssh
- Прошить и считать EEPROM можно для 19 серии только из ch0 разьема
- Для работы PT2 нужно чтобы был пройден PT1 тест
- Возможно нужно выбрать Bootloader S19 и перезагрузиться кнопкой для корректной работы

# Мною добавлено
- Паттерны PT1, PT2 и tool S19J для теста плат BHB42701 на чипах BM1362

# Еще
Можно пересобрать образ из под linux и добавить в управление к примеру остановку всех процессов:
- Extract image:
dd if=uramdisk.image.gz bs=64 skip=1 of=ramdisk.image.gz
gunzip ramdisk.image.gz 
sudo mount -o loop ramdisk.image /mnt/tmp

- Make modifications

- Repack image:
sudo umount /mnt/tmp
gzip -v9 ramdisk.image
mkimage -A arm -O linux -C gzip -a 0 -e 0 -T ramdisk -n LokisAsicTester -d ramdisk.image.gz uramdisk.image.gz

# LokisAsicTester
This is a compilation of all test binaries found in different Antminer Firmwares and Testfirmwares.

# Installation
- [Download](https://github.com/LOKisGithub/LokisAsicTester/archive/refs/heads/main.zip) the whole repository or clone it via git
- Copy the contents to a SD card (needs to be FAT32 formatted)
- Boot S17 controlboard or Universaltestfixture with SD card

# Usage
You can prepare your config files and save them to the configs folder on the SD card. The WebUI will pickup all configs and show them in a dropdown, so you can easily chose between different config-files.

- Boot your testfixture or S17+ Controlboard from SD
- point your browser to [lokisAsicTester.local](http://lokisAsicTester.local) (login is root/root)
- setup your test config and binaries
- hit the test button (IP-report button) or start the test from the WebUI


