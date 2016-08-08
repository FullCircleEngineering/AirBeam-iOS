# AirBeam Firmware for iOS modifications

## Original source code
This firmware was modified from the original source code available from AirCastingAndroidClient/arduino/aircasting/AirBeamFirmware_11_14_15.

The original firmware was released under the GNU Affero General Public License v3.

## The RN4020 BTLE module
This firmware was modified to work with the modified AirBeam hardware.  The AirBeam hardware was modified to use the RN4020 BTLE module instead of the current BlueTooth Standard (SPP) module.  The RN4020 is unique in that is does not use a standard BTLE characteristic, rather abstracts on BTLE to create a pseudo-SPP serial interface.  
In other words, you can stream ASCII characters to the RN4020 as you would a BlueTooth Standard (SPP) module, and capture those characters on the other side of your connection as if it were a serial/SPP connection.
The implications: Serial data can be streamed to the RN4020 module just as they are being done currently with the BlueTooth Standard module.  No special communication/configuration is necessary firmware side to accomodate BTLE.
  
## Modifications for iOS
No significant modifications occured for use with iOS other than changing the configuration options in the ```setup(){}``` section to configure the rn4020 using AT commands (refer to the rn4020 user guide).
**The data output has not changed** from the 11/14/15 version of the firmware, accept to stream the data as newline delimited blocks of comma delimited fields (instead of the old version of character-heavy JSON).

#TO DO
The firmware is incomplete as of 08/08/2016.  Additional code needs to be added to the ```setup(){}``` section to capture the RN4020 UID, e.g. AirBeam-04A35T67
This UID needs to be included in each data block export so that the data can be associated with a specific device/UID.
  
