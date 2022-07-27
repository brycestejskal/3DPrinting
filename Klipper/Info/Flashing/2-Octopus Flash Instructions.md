# Complie/Flash Instructions

## First flash must be from SD card.

1. SSH in to pi
2. Run 
```
    cd ~/klipper/
    make menuconfig ; Configure as outlined by MCU manual for board
    make clean
    make    ;klipper.bin file is now reacy for you to grab with WIN-SCP to place on MicroSD card
    ls /dev/serial/by-id/*          ; Note the output. This may need to be ran again after initial flash.
```

3. Pull firmware klipper.bin down to computer via WinSCP
4. Rename klipper.bin to firmware.bin
4. Format a different SD card  
4. Put firmware.bin on the deifferent SD
4. Turn power off  
5. Put SD in MCU sd slot  
6. Turn power back on  
7. Walk away for a few minutes.  
8. Turn Power off, and turn power back on  ;You can pull the SD card to verify it is now firmware.cur but it is prolly already flashed just fine.  
9. SSH in to pi
10. Run 
```
    
    
    make menuconfig ; Configure as outlined by MCU manual for board
    make clean
    make    ;klipper.bin file is now reacy for you to grab with WIN-SCP to place on MicroSD card
    ls /dev/serial/by-id/*          ; Note the output. This may need to be ran again after initial flash.
```
11. Note new serial and update printer.cfg in fluiddpi interface.


## Future flashing using DFU to update

1. SSH in to pi
2. Run
```
    ls /dev/serial/by-id/*
    cd ~/klipper/
    make clean
    make
    sudo service klipper stop
    make flash FLASH_DEVICE=         ; after the = sign is  output from ls /dev/serial/by-id/* and starts with /dev/serial/by-id/
    sudo service klipper start
```
