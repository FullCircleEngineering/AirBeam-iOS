# AirBeam-Hardware(PCB)-iOS

## Original source code
These design files were modified from the original source file available from https://github.com/vitiral/Airbeam.

## Modifications for iOS
MODIFIED: 07/08/2016 Nick Masson nicholas.b.masson@gmail.com

The original source files were modified to remove the old BlueTooth Classic module and replace it with the [RN4020 BTLE module](http://www.microchip.com/wwwproducts/en/RN4020).
The RN4020 takes a 3.3V TX/RX connection akin to the old BTClassic module.  It communicates with it's master via AT commands (reference the user guide).
Unlike other BTLE modules, it does use a standard BTLE profile for sending/receiving data.  It uses the Microchip-specific MLDP profile, which allows for a transparent serial-like connection (essentially a BTClassic connection using SPP).  As such, ASCII data can be streamed to the RN4020 over UART as with the BTClassic SPP method.

The 5-pin header wiring was also modified to remove a GPIO connection and replace it with the V_charger connection.  i.e. you can now use the 5-pin header to charge the LiPo battery with an unregulated 5VDC input (analagous to charging via the USB port).  This allows for more robust connections when integrating the AirBeam in to other control/embedded systems.

## ***IMPORTANT***

#Testing
The revised PCB was printed, populated and tested.  All BTLE functionality was verified and working.  As such, the Gerber Files included here should be verified for production.

#BOM
***NO CHANGES*** have been made to the BOM between the original and modified files directories.  The possition of all components on the board, however, is the exact same as before **accept** the RN4020 module.
The old BOM and pick'n'place possitions should be the same; the only change necessary is repalcing the BTClassic module possition with the possition of the RN4020 module.
  
