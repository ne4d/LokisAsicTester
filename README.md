# LokisAsicTester 

Большой сборник TestJIG или TestFixtures в одном удобном месте

# Как использовать
Взять контрольную плату от S17Pro, зашить официальный образ sd картой и записать этот проект на sd.
Веб интерфейс доступен по локальной сети, пароль root/root.

# Известные проблемы и нюансы
- Если сменить через скрипт пароль у root. все ломается, sd недоступна по ssh
- Прошить и считать EEPROM можно для 19 серии только из ch0 разьема
- Для работы PT2 нужно чтобы был пройден PT1 тест
- Возможно нужно выбрать Bootloader S19 и перезагрузиться кнопкой для корректной работы

# Мною добавлено
- Паттерны PT1, PT2 и tool S19J для теста плат BHB42701 на чипах BM1362
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


