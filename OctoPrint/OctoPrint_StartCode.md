; This is code to run before sliced files on print initiation.
M140 S50 ; Set Bed temp to 50c
M190 S50 ; Wait for bed to hit 50c to level
G91 ; Set relative
G1 E-3 ; Retract Filament to prevent oozing
G90 ; Set Motor Absolute Positioning

G28 ; Home X/Y
G29 ; Determine Z Mesh
M420 S1 ; Use this to enable bed mesh while printing

G90 ; Set Motor Absolute Positioning
G0 Z0 ; Undo G29 Z+10mm Z height
G4 S4 ; Wait 4 Seconds
G0 Z-3.8 ; BLTouch Z-Offset
G4 S4 ; Wait 4 Seconds
G92 Z0 ; Set Z-Offset as new zero
M500 ; Save to EEPROM
G4 S4 ; Wait 4 Seconds

M190 S50 ; Wait for Bed to hit 50c
G0 Z20 ; Lift Nozzle before move
G0 X20 Y20 ; Move to start area for Nozzle purge to avoide dingleberrys in print area

