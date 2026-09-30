# camera board

a wrist-worn capture board: 720p30 video and IMU to local storage, short Wi-Fi preview to a phone, and radio time sync with other nodes. an always-on nRF54L15 supervisor runs the device; the RV1103 linux domain is powered only while capturing or previewing. camera sensor and its rails are TBD and out of scope for this brief.
board
• 4-layer, 0.8 to 1.0 mm finished, standard through vias, no HDI.
• stackup: L1 signals and components, L2 solid ground, L3 power pours and slow signals, L4 signals and components.
• double-sided placement. outline TBD after placement study; target is wristband-sized, battery stacked under the board.
• controlled impedance: 50 Ω RF, 90 Ω USB diff, 100 Ω MIPI diff, all on L1 over L2.
components
ref
part
package
role
U1
Rockchip RV1103G1
QFN88
application SoC, 64 MB SiP DDR2, H.264
U2
8 GB SD NAND, industrial (XTX / CS class)
LGA-8, 6 x 8 mm
boot and footage
U3
AIC8800DC (fallback RTL8723DS)
chip-down or module
Wi-Fi for preview
U4
Nordic nRF54L15
QFN48
supervisor, BLE 5, radio time sync
U5
Nordic nPM1300
QFN32, 5 x 5 mm
charger, power path, 1.8 V always-on rail, LED drivers, ship mode
U6
Bosch BMI270
LGA-14, 2.5 x 3.0 mm
IMU on nRF SPI
U7
TPS6282x-class buck, 2 A
1.5 x 1.5 mm QFN
0.9 V RV1103 core
U8
TPS6282x-class buck, 1 to 2 A
1.5 x 1.5 mm QFN
1.8 V DDR2 and IO
U9
TI TPS63802
2 x 3 mm QFN
3.3 V buck-boost
U10
SN74AXC-family translator with Ioff
small QFN
always-on to switched domain buffer
U11
low-capacitance USB ESD array
SOT-563 or DFN
D+/D- protection
U12
VBUS TVS / OVP
DFN
VBUS protection
Y1
24 MHz crystal
2016 or 3225
RV1103 reference
Y2, Y3
32 MHz and 32.768 kHz crystals
per Nordic reference
nRF clocks
ANT1, ANT2
2.4 GHz chip antennas
per vendor
Wi-Fi and nRF
J1
USB-C receptacle, USB 2.0, 16-pin
mid-mount
charge, offload, flashing
J2
camera FPC connector
TBD with sensor
camera
J3
battery connector or solder pads
TBD
450 mAh Li-Po with protection and 10 k NTC
S1
tactile switch
micro SMT
record and power
D1
RGB LED
1.6 x 1.6 mm
status, driven by nPM1300 or nRF
