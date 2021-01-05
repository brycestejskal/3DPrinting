; This is code to run before sliced files on pint initiation.
M140 S50 ; Set Bed temp to 49c
M190 S45 ; Wait for bed to hit 45c to level
G91 ; Set relative
G1 E-3 ; Retract Filament to prevent oozing
G90 ; Set Motor Absolute Positioning

G28 ; Home X/Y
; M420 S ; Use this to recall bed mesh from connectcode instead of running g29 every print

G29 ; Determine Z Mesh
G90 ; Set Motor Absolute Positioning
G0 Z0 ; Undo G29 Z+10mm Z height
G4 S4 ; Wait 4 Seconds
G0 Z-3.6 ; BLTouch Z-Offset
G4 S4 ; Wait 4 Seconds
G92 Z0 ; Set Z-Offset as new zero
M500 ; Save to EEPROM

M190 S49 ; Wait for Bed to hit 49c
G0 Z20 ; Lift Nozzle before move
G0 X20 Y20 ; Move to start area for Nozzle purge
; M104 S160 ; Preheat Nozzle to 180c
; M109 S160 ; Wait Until Nozzle is 180c
; G0 Z0 ; 
