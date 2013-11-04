# OpenWrt-libnfc
Patches and notes of libnfc library in OpenWrt.

## Compile

	make menuconfig
	//Choose libnfc (Libraries --> libnfc)
	// Choose app and eg(Utilities --> libnfc-bin, Utilities --> libnfc-examples)


## PN532
To use PN532 with OpenWrt, a configure file need to be configured.

	make -p /etc/nfc/devices.d
	vi /etc/nfc/libnfc.conf

In put the content below:(replace `/dev/ttyUSB0` with the right device of yours)

	allow_autoscan = true
	allow_intrusive_scan = false
	log_level = 1
	device.name = "PN532 Module"
	device.connstring = "pn532_uart:/dev/ttyUSB0"

## Test
Read tag:
	
	nfc-list
