TARGET=led_blinking
FAMILY=-mthumb -mcpu=cortex-m4

AS=arm-none-eabi-as
LD=arm-none-eabi-ld
OBJ=arm-none-eabi-objcopy
DUMP=arm-none-eabi-objdump

AFLAGS=-mthumb -mcpu=cortex-m4 -g
LFLAGS=-T $(TARGET).ld -o
OFLAGS=-Obinary
DFLAGS=-D

$(TARGET).bin: $(TARGET).axf
	$(OBJ) $(OFLAGS) $(TARGET).axf $(TARGET).bin
	
$(TARGET).axf: $(TARGET).o
	$(LD) $(LFLAGS) $(TARGET).axf $(TARGET).o
	
$(TARGET).o: $(TARGET).s    
	$(AS) $(AFLAGS) $(TARGET).s -o $(TARGET).o	
 
clean: 
	rm -f $(TARGET).axf *.o *.bin *.list
	
list:
	$(DUMP) $(DFLAGS) $(TARGET).axf > $(TARGET).list