=======
Scripts
=======

The Configuration scripts are used to setup the environment for the application. These scripts are stored in ~/OpenXCAccessory/startup directory.

WiFi Setup
--------

* Modem

  * The script connects the modem to one of the Access Points (APs) specified in the "wpa_supplicant" file.
  * The script opens an “OPENXC_AP” access point with 20.0.0.1 IP address for the V2X device to connect to the modem, in topology 3.
  
* V2X

  * The script connects the V2X device to one of the APs specified in the "wpa_supplicant" file, in topology 2.
  * The script connects to “OPENXC_AP” from modem, in topology 3. 
   
* RSU

  * The script connects the RSU to one of the APs specified in the "wpa_supplicant" file.
   
.. note:: 
 The scripts reset the hardware (Modem and V2X) if the required connector is not connected.

Cohda Setup
--------

The "Cohda_setup.sh" script performs the following functions for the setting the Cohda environment and the necessary IP setup for the
802.11p based network.

* Enable Cohda HW.
* Download Firmware.
* Install llc kernel object with TCP/IP and UDP/IP support.
* Bring up Cohda interface and assign IP address.
* Create IP neighborhood for other Cohda devices (this is a pre-assigned network configuration).

  * Each Cohda device is assigned a unique 10.0.0.XX address and a unique MAC address based on the last four characters of the Bluetooth MAC address, found through a lookup table in the script.
  * All the Cohda devices in the supplied population (50 units) are added to the current device neighborhood.
  
  
