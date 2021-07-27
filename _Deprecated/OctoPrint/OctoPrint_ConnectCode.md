; This is the code to be ran on printer connection to OctoPrint
G28 ; Home
M420 S ; Enable bed levelig after G28 Home
; The following is disabled. Enable once Z-offset crashing resolved
; M140 S50 ; Set Bed temp to 50c
; M190 S50 ; Wait for bed to hit 50c to level
; G29 ; Bed leveling z mesh
; m500 ; Save z mesh to EEPROM
; M140 S8 ; Set bed heater above mintemp threshold for standby