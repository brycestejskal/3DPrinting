# Complie/Flash Instructions

## First flash must be from SD card.

SSH in to pi

    cd ~/klipper/
    make menuconfig ; Configure as outlined by MCU manual for board
    make clean
    make    ;klipper.bin file is now reacy for you to grab with WIN-SCP to place on MicroSD card
    ls /dev/serial/by-id/*          ; Note the output. This may need to be ran again after initial flash.

Format SD card
Put klipper.bin on SD
Put SD in MCU sd slot
Turn power off, and turn power back on
Walk away for a few minutes.
Turn Power off, and turn power back on
You can pull the SD card to verify it is now klipper.cur but it is prolly already flashed just fine.

## Future flashing using DFU to update

SSH in to pi
    ls /dev/serial/by-id/*
    cd ~/klipper/
    make clean
    make
    sudo service klipper stop
    make flash FLASH_DEVICE=         ; after the = sign is  output from ls /dev/serial/by-id/* and starts with /dev/serial/by-id/
    sudo service klipper start