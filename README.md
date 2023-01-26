# pcb-RF-BM-2652

RFStar ZigBee modules development board PCB (designed by Vedga)

Sorry, me forget to route NRESET signal from module to the J3 connector. Use pullup resistor R1 with capacitor or connect NRESET via J1 debug port.

## Connect to the XDS110 (module must be powered from external source)

### Module (J1 male) <=> XDS110 (20 pin female header)
- [1] <=> [8] GND
- [3] <=> [11] TCK
- [4] <=> [1] SWDIO/TMS
- [7] <=> [2] NTRST
- [2] <=> [5] VTRef (optional, may be omitted)

## Connect to Banana PI M1

### Module (J3 male) <=> Banana PI M1
- [1] <=> [2 GPIO J12] 3.3V
- [2] <=> [10 GPIO CON3] /dev/ttyS2 RxD
- [6] <=> [] BSL
- [16] <=>
- [19] <=> [8 GPIO CON3] /dev/ttyS2 TxD
- [21] <=> [8 GPIO J12] GND

#### /boot/armbianEnv.txt
```
verbosity=1
bootlogo=false
console=both
disp_mode=1920x1080p60
overlay_prefix=sun7i-a20
rootdev=UUID=fc4defda-2429-486b-8c7c-35517c9f0f29
rootfstype=ext4
overlays=uart2 uart3 uart4 uart5 uart6 uart7
param_uart3_pins=b
usbstoragequirks=0x2537:0x1066:u,0x2537:0x1068:u
```
