PRINT_START BED_TEMP=[bed_temperature_initial_layer_single] EXTRUDER_TEMP=[nozzle_temperature_initial_layer] Chamber=[chamber_temperature] 
; Note, the default does not have the _TEMP. This was overridden in ORCA.
; In the future, the printer CFG should be updated to remove _TEMP and the ORCA code reverted. Initial attempt concluded there are other areas outside of PRINT_START that reference the var.

; You can use following code instead if your PRINT_START macro support Chamber and print area bedmesh
; PRINT_START EXTRUDER=[nozzle_temperature_initial_layer] BED=[bed_temperature_initial_layer_single] Chamber=[chamber_temperature] PRINT_MIN={first_layer_print_min[0]},{first_layer_print_min[1]} PRINT_MAX={first_layer_print_max[0]},{first_layer_print_max[1]}