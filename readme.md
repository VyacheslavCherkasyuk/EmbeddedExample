

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
sudo apt-get install openocd
```
MacOS
```shell
brew install open-ocd
```

# Компиляция, сборка, запуск и отладка проекта
Отдельная папка - это отдельный пример проекта. В каждой папке есть make файл для компиляции и сборки проекта.
Пример использования make команд:

```shell
$ make
$ make clean
$ make list
```
Запустить QENU эмулятор в консоли:

```shell
$ qemu-system-arm -M lm3s811evb -kernel "Название файла".elf -nographic
```

# Источники
Статья на хабре "Пишем свою простейшую программу для ARM Cortex-M3"
https://habr.com/ru/company/embox/blog/421833/

Компилятор - https://developer.arm.com/downloads/-/gnu-rm