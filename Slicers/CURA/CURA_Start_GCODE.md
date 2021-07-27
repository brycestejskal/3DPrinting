; Setup
M220 S100 ;Reset Feedrate
M221 S100 ;Reset Flowrate

;Preheat bed and extruder before homing
M140 S{material_bed_temperature} ; Preheat bed and wait for final bed temp before homing
M104 S120 ; set temporary nozzle temp to prevent oozing during homing and auto bed leveling
M190 S{material_bed_temperature} ; Preheat bed and wait for final bed temp before homing
;M109 S120 ; Wait for preheat nozzle temp

; Home and safe move nozzle to origin
G28 ; Home
M420 ; load bed mesh
G92 E0 ;Reset Extruder
G1 Z2.0 F3000 ;Move Z Axis up
G1 X2 Y20 F5000.0 ;Move to start position

; Prepare Extruder
;M104 S180 ; Set Nozzle to 180 for a short retraction
;M109 S180 ; Wait for nozzle to reach temp
;G1 E-1.0 ; Retract 1mm
M104 S{material_print_temperature} ; Set final nozzle temp
M109 S{material_print_temperature} ; Wait for final nozzle temp
;G1 E1.0 ; Detract 1mm
;G92 E0 ;Reset Extruder
;M83 ; extruder relative mode

; primeline
G1 X2 Y20 Z0.28 F5000.0 ;Move to start position
G1 X2 Y200.0 Z0.28 F1500.0 E15 ;Draw the first line
G1 X2.3 Y200.0 Z0.28 F5000.0 ;Move to side a little
G1 X2.3 Y20 Z0.28 F1500.0 E30 ;Draw the second line
G92 E0 ;Reset Extruder
G1 Z2.0 F3000 ;Move Z Axis up