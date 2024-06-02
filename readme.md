

# Утилиты
### Установить пакет GNU toolchain 
Debian:

```shell
$ sudo apt install gcc-arm-none-eabi
```

### Установить Quemu эмулятор 
Debian:

```shell
$ sudo apt install qemu-system-arm
```
### Установить отладчик OpenOCD
Debian:

```shell
sudo apt-get install openocd
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
Пишем свою простейшую программу для ARM Cortex-M3
https://habr.com/ru/company/embox/blog/421833/