

## configuration files for marlin 2.0.x





taz 6 with 32 bit btt skr 1.4 turbo board, 

tmc2209 drivers, 

aux bed heater mosfet added, heats bed at full power (255) , lulzbot default is 208

no cooling part fan, 

hemera extruder, 

bltouch,

(or manual bed leveling enabled to do a manual mesh. )

sensorless homing on x and y. 

z uses the silver push button

no wipe, just heat up and print. 








## starting g-code: 

M75 ; start GLCD timer

M107 ; disable fans

G90 ; absolute positioning

M82 ; set extruder to absolute mode

G92 E0 ; set extruder position to 0

M140 S{first_layer_bed_temperature[0]} ; start bed heating up

M104 S{first_layer_temperature[0]} ; start heating extruder

G28 XY ; home X and Y

G28 Z ; home Z



M109 R{first_layer_temperature[0]}  ; wait for extruder to reach printing temp

M190 R{first_layer_bed_temperature[0]} ; wait for bed to reach printing temp

G1 Z2 E0 F75 ; prime tiny bit of filament into the nozzle

M117 TAZ 6 Printing... ; progress indicator message on LCD







