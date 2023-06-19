

## Old Marlin

echo:Filament settings: Disabled
echo:  M200 D1.75
echo:  M200 D0

echo:; Maximum feedrates (units/s):
echo:  M203 X500.00 Y500.00 Z10.00 E50.00

echo:; Maximum Acceleration (units/s2):
echo:  M201 X500 Y500 Z100 E5000

echo:; Acceleration (units/s2): P<print_accel> R<retract_accel> T<travel_accel>
echo:  M204 P500.00 R1000.00 T500.00

echo:; Advanced: S<min_feedrate> T<min_travel_feedrate> B<min_segment_time_ms> X<max_xy_jerk> Z<max_z_jerk> E<max_e_jerk>
echo:  M205 S0.00 T0.00 B20000 X8.00 Y8.00 Z0.40 E5.00

echo:; PID settings:
echo:  M301 P23.81 I1.93 D73.64

## New Marlin

echo:; Filament settings (Disabled):
echo:  M200 S0
echo:  M200 T0 D1.75
echo:  M200 T1 D1.75

echo:; Max feedrates (units/s):
echo:  M203 X500.00 Y500.00 Z5.00 E25.00

echo:; Max Acceleration (units/s2):
echo:  M201 X500.00 Y500.00 Z100.00 E5000.00

echo:; Acceleration (units/s2) (P<print-accel> R<retract-accel> T<travel-accel>):
echo:  M204 P500.00 R500.00 T500.00

echo:; Advanced (B<min_segment_time_us> S<min_feedrate> T<min_travel_feedrate> J<junc_dev>):
echo:  M205 B20000.00 S0.00 T0.00 J0.08

echo:; Hotend PID:
echo:  M301 P21.73 I1.54 D76.55

echo:; Tool-changing:
echo:  M217 Z2.00


##  Orbiter v1.5
M350 E16 ;micro stepping set to 16
M92 E690 ;steps/mm - you may need to finetune it
M201 E600 or E800 ;acceleration mm/s^2
M203 E30, E60 or E120 ;max speed mm/s
M205 E10 ;E jerk mm/s
M906 T0 E350 or E850 ; TMC motor RMS current mA
M907 E350 or E850 ; motor RMS current mA
M900 T0 K0.22 L0.4 ; linear advance values TBD
M900 T0 S0
M207 S1.5 F3600 or F7200 Z0.2 ;firmware retraction
M500 ;save settings to EEPROM




## From me. for orbiter

M201 E600
M203 E30
M205 E10
M350 E16
M217 Z0
M500




### extruder debugging/calibration

M82 enable direct extrusion
M302 P1 enable cold extrusion
G1 E15

#### endstop debugging

M119 - State of endstops
G28 [X Y Z] - home axis