# Утилиты

### Установить пакет GNU embedded toolchain

Debian

```shell
$ sudo apt install gcc-arm-none-eabi
```

MacOS

```shell
$ brew install --cask gcc-arm-embedded
```

Brew не устанавливает самостатятельно toolchain а скачивает пакет установщика для Mac OS и сохраняет в `/usr/local/Caskroom`. Необходимо перейти в папку, найти пакет установщика, запустить установщик.

### Установить Quemu эмулятор

Debian

```shell
$ sudo apt install qemu-system-arm
```

MacOS

```shell
$ brew install qemu
```

### Установить отладчик OpenOCD

Debian

```shell
$ sudo apt-get install openocd
```

MacOS

```shell
$ brew install open-ocd
```

### Установить утилиту для отображения списка usb устройств
MacOS
```shell
$ brew install lsusb
```
Вывод в консоле для отладочной платы STM32F4Discovery может быть как на примере ниже:

```shell
Bus 020 Device 038: ID 0483:3748 STMicroelectronics STM32 STLink  Serial: Tÿp?IHVER?
```

# Полезные расширения для Visual Studio Code

Подсветка синтаксиса для ассемблера ARM - https://marketplace.visualstudio.com/items?itemName=dan-c-underwood.arm
Подсветка синтаксиса для линковщика (LD) - https://marketplace.visualstudio.com/items?itemName=ZixuanWang.linkerscript

# Компиляция, сборка, запуск и отладка проекта

Отдельная папка - это отдельный пример проекта. В каждой папке есть make файл для компиляции и сборки проекта.
Пример использования make команд:

```shell
$ make
$ make clean
$ make list
```

Запустить с помощью QEMU эмулятора:

```shell
$ qemu-system-arm -M lm3s811evb -kernel "Название файла".elf -nographic
```
### Залить прошивку с помощью stlink
stlink

```shell
$ st-flash write "Название файла прошивки".bin 0x8000000
```

### Отладка
1. Необходимо запустить утилиту st-util из пакеты stlink.
2. Далее запустить arm-none-eabi-gdb "Название файла".axf.
3. Ввести команду tar extended-remote :4242 для подключения к микроконтроллеру.

Команды gdb для отладки:
   load
   next
   step
   run
   finish
   break
   clear
   info registers
   x/fx адрес

# Источники

Статья на хабре "Пишем свою простейшую программу для ARM Cortex-M3"
https://habr.com/ru/company/embox/blog/421833/

Компилятор - https://developer.arm.com/downloads/-/gnu-rm
Отладчик stlink - https://github.com/stlink-org/stlink
Отладчик openOCD - https://openocd.org
