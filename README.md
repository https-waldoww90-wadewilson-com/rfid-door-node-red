# rfid-door-node-red
A complete Node Red Web Control to monitor &amp; control multiple rfid-door hardware devices

This is a complete Node-Red flow to manage multiple marelab RFID-DOOR or ESP-RFID Door access controls over a Node-Red based home automatisation system. When you follow the tutrial here and configure the needed setting you get a Web GUI with the following functionality. The hole communication is done over MQTT. 

# GUI Overview 

## Dialog GUI to manage RFID devices
<img src="https://github.com/marelab/rfid-door-node-red/blob/master/images/gui-reader-list.png">

* New Devices are added automatic after they sync over MQTT
* The List starts with the device name as link to the device Gui
* The IP Adress of the device
* Del | Door open | Sync Users to device | Sync Users form device | Delete Device Button



## Dialog GUI to manage Users of the devices
<img src="https://github.com/marelab/rfid-door-node-red/blob/master/images/gui-user-list.png"/>
This list stores all users of all devices found by the rfid-door sync. If you press the bottom at the RFID Devices Tab "Sync Users form device" the rfid device sends all user data over MQTT to this List (Database). This list is a central DB based archive of all users from the devices. You can edit the User here for example rename or delete a user, but keep in mind until it is synced to the device this list is only persitent at the Database. To sync all devices with that list use the Sync Button at the end of the list. All Users get overwritten at the device, so the RFID device local stored list reflects the central stored DB List. 

## Dialog GUI to manage new Users 
<img src="https://github.com/marelab/rfid-door-node-red/blob/master/images/gui-unkonwn-user.png">
If you add new users to the system you got two ways. The one used over the Web Gui of the RFID device or over this tab. It woorks like that: 
* A unknown RFID chip is recognized by the reader
* This RIFID information is send oover MQTT to this list to be further added too the system by the Administrator 
* You select the unknown RFID in that list
* Add a name and the group for it 
* It will be stored in the central DB list and should show up under GUI to manage Users
* Then you just need to sync the User List to the devices 

after that the new User can open the door.


## Dialog GUI to List events and acess trys of the devices
If you enable logging over MQTT at the rfid devices this list gets filled like the list you can see at the local rfid devices. But keep in mind enabling MQTT logging disables local device logging. Its implemented like that to reduce the RFID device write cycles and to have a central logging space. Also in the central log you get the Door Name where the access or event happend.

<img src="https://github.com/marelab/rfid-door-node-red/blob/master/images/gui-access-log.png">

<img src="https://github.com/marelab/rfid-door-node-red/blob/master/images/gui-event-log.png">

You can scroll the list by << >> Buttons, per page 10 entrys are shown the sort order is last entry at top first at the end.



# Installation Instructions
This instruction is based on a Node-Red Installation for Rasberry PI but should also work on any Linux based system.

## Basic prepareations
You need the following tools to get the flow running:
- marelab rfid-door firmware 
- MySQL Database (stores devices, user & logs)
- MQTT Server

## Configure the marelab rfid-door device

## Install the marelab rfid-door-node-red flow

## Configure the marelab rfid-door-node-red flow


