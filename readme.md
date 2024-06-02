Пишем свою простейшую программу для ARM Cortex-M3
https://habr.com/ru/company/embox/blog/421833/

# Утилиты
## Установить пакет GNU toolchain 
Для Debian:

```shell
sudo apt install gcc-arm-none-eabi
```

## Установить Quemu. Эмулятор 

```shell
sudo apt install qemu-system-arm
```

Запустить QENU эмулятор в консоли:

```shell
qemu-system-arm -M lm3s811evb -kernel $(FILE).elf -nographic
```
