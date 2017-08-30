# 0MNACCSA4ENU {#0mnaccsa4enu}

INTRODUCTION

Thank you for choosing our product.

The accessories described in this manual are of the highest quality, carefully designed and built in order to ensure excellent performance.

This manual contains detailed instructions on how to install and use the product.

**This manual must be stored in a safe place and CONSULTED BEFORE USING THE DEVICE for proper usage instructions as well as maximum performance from the device itself.**

**NOTE:** Some images contained in this document are for informational purposes only and may not faithfully demonstrate the parts of the product they represent.

Symbols used in this manual:

|  | Warning | Indicates important information that must not be ignored. |
| --- | --- | --- |

|  | Information | Provides notes and useful suggestions for the User. |
| --- | --- | --- |

SAFETY

**This part of the manual contains SAFETY precautions that must be followed scrupulously.**

*   The device has been designed for professional use and is therefore not suitable for use in the home.
*   The device has been designed to operate only in closed environments. It should be installed in rooms where there are no inflammable liquids, gas or other harmful substances.
*   Take care that no water or liquids and/or foreign bodies fall into the device.
*   In the event of a fault and/or impaired operation of the device, do not attempt to repair it but contact the authorized service centre.
*   The device must be used exclusively for the purpose for which it was designed. Any other use is to be considered improper and as such dangerous. The manufacturer declines all responsibility for damage caused by improper, wrong and unreasonable use.

Environmental Protection

Our company devotes abundant resources to analyzing environmental aspects in the development of its products. All our products pursue the objectives defined in the environmental management system developed by the company in compliance with applicable standards.

Hazardous materials such as CFCs, HCFCs or asbestos have not been used in this product.

When evaluating packaging, the choice of material has been made favoring recyclable materials.

Please separate the different material of which the packaging is made and dispose of all material in compliance with applicable standards in the country in which the product is used.

**_disposing of the product_**

The device contains internal material which (in case of dismantling/disposal) are considered TOXIC, such as electronic circuit boards. Treat these materials according to the laws in force, contacting qualified centers. Proper disposal contributes to respect for the environment and human health.

© The reproduction of any part of this manual, even in part, is prohibited unless authorized by the manufacturer.

The manufacturer reserves the right to change the product described at any time without prior notice for improvement purposes.

COntents

description 6

Overview 6

Package contents 6

Front panel 7

Network port 7

Micro-USB port 7

Serial port 7

LED 7

GSM Modem 8

Reset button 8

Users 8

Network services 9

SSH 9

Serial network 9

Wake-on-LAN 9

HTTP 9

SNMP 9

UDP 9

Modbus TCP/IP 10

BACnet/IP 10

FTP 10

Email 10

Reports 10

Device values and events history log archive 11

Eventlog 11

Datalog (only for UPS devices) 11

Environmental sensors (optional) 12

Available sensors 12

INSTALLATION 12

CONFIGURATION 13

Overview 13

Configuration via HTTP/HTTPS 13

Configuration via USB 14

Configuration via SSH 14

Configuration menu description 15

Start menu 15

Setup 17

IP config 18

Web configuration 19

Network configuration 20

Device configuration 21

Data log 22

UDP Firewall 23

Wake on Lan address 24

SNMP 25

MODBus/BACNET 26

JSON 27

Date &amp; Time configuration 28

NTP &amp; Timezone configuration 29

Email configuration 30

Email logic 32

GSM Modem 33

Sensors 34

Sensors Config 35

Password recovery 37

Wi-Fi setup (optional card required) 38

Expert mode 39

Configuration of several devices 39

Firmware upgrade 40

Firmware upgrade via HTTP 40

Firmware upgrade via FTP 40

SNMP configuration 41

Modbus TCP/IP protocol 43

bacnet/IP configuration 47

SERIAL PORT configuration 49

TECHNICAL DATA 50

Network cable 50

Operating and storage conditions 50

description

Overview

_NetMan 204_ is an accessory that allows device management through a LAN (Local Area Network); the accessory supports all the main network protocols (SNMP v1, v2 and v3, TCP/IP, HTTP and MODBUS) and is compatible with Ethernet 10/100Mbps IPv4/6 networks. The device can therefore be integrated easily into medium and large-sized networks.

_NetMan 204_ also records device values and events in the history log archive and can manage optional environmental sensors (not supplied with the device, but provided separately)

Package contents

| NetMan 204 | USB cable |
| --- | --- |
|  |  |
|  |  |
| Quick start |
|  |

Front panel

|  | A: Network port |
| --- | --- |

Network port

_NetMan 204_ connects to 10/100 Mbps Ethernet networks by means of connector RJ45\. The LEDs built into the connector describe the status of the network:

*   Left LEDSOLID YELLOW: NetMan204 has detected a valid link.FLASHING YELLOW: NetMan204 is receiving or transmitting data packets.
*   Right LEDSOLID GREEN: NetMan204 is connected to a network operating at 100 Megabits per second.

Micro-USB port

_NetMan 204_ makes available an USB communication port through which it is possible to configure it (see paragraph “Configuration via USB”).

Serial port

_NetMan 204_ makes available a serial communication port to which you can connect environmental sensors (not supplied with the device, but provided separately).

LED

This led describes the status of _NetMan 204_:

*   SOLID RED: _NetMan 204_ is not communicating with the device (verify PRTK Code).
*   FLASHING RED: the DHCP server does not have assigned a valid IP address to _NetMan 204_.
*   OFF: regular working.

GSM Modem

_NetMan 204_ can send a notification SMS if one or more alarm conditions occur. The SMS can be sent to up to three recipients and they can be sent for seven different kinds of alarm.

An external GSM modem (optional accessory) and a SIM card are required. For more details, see paragraph “GSM Modem”

Reset button

The reset button allows to restart the _NetMan204_ or to load a default configuration with a predefined static IP address.

**To reset** _NetMan204_: keep press the reset button until the red led start flashing (ca. 2 seconds) and then release it.

**To load a configuration with predefined static IP address**: keep press the reset button; first the led starts flashing, then turns to solid red (ca. 10 seconds). When the led is solid red, release the reset button and the _NetMan 204_ will reboot with:

*   IP address: 192.168.0.204
*   Netmask: 255.255.0.0
*   SSH service enabled
*   HTTP service enabled

|  | HTTP and SSH service are enabled temporarily without changing the configuration saved in non-volatile memory. |
| --- | --- |

Users

It is possible to access to _NetMan 204_ with three different users (admin / fwupgrade / user).

| **Username** | **Default password** | **Privileges** |
| --- | --- | --- |
| admin | admin | user with right to modify the configuration |
| fwupgrade | fwupgrade | user with right to upgrade the firmware |
| user | user | user with right to read and download the log files |

Network services

_NetMan 204_ implements a series of services based on the main network protocols. These services can be activated or deactivated according to requirements (see paragraph “Configuration”). A brief description for each of these is given below.

SSH

By means of a SSH client (available on all the main operating systems) a remote connection with _NetMan 204_ can be established to change its configuration (see paragraph “Configuration via SSH”).

Serial network

To emulate a point-to-point serial connection through the network (TCP/IP protocol) in order to use special function service software.

Wake-on-LAN

_NetMan 204_ can send “Wake-on-LAN” command for remote computers boot.

HTTP

Using the HTTP (Hyper Text Transfer Protocol), is possible to configure the _NetMan 204_ and the status of the device can be monitored by means of a web browser without having to install additional software. All the most popular web browsers are supported; only most recent version of browsers are supported.

SNMP

SNMP (Simple Network Management Protocol) is a communication protocol that allows a client (manager) to make requests to a server (agent). _NetMan 204_ is an SNMP agent.

To exchange information, manager and agent use an addressing technique called MIB (Management Information Base). There is a MIB file for each agent, defining which variables can be requested and the respective access rights. The agent can also send messages (TRAP) without a prior request from the manager, to inform the latter of particularly important events. SNMPv3 is the evolution of SNMP and introduces new important features related to security.

UDP

UDP (User Datagram Protocol) is a low level network protocol that guarantees speed in the exchange of data and low network congestion. It is the protocol used by the UPSMon software for monitoring and control of the device.

The UDP connection uses the UDP 33000 port by default but can be configured on other ports according to requirements.

Modbus TCP/IP

The device status can be monitored by means of the standard network protocol MODBUS TCP/IP. Modbus TCP/IP is simply the Modbus RTU protocol with a TCP interface that runs on Ethernet.

BACnet/IP

The device status can be monitored by means of the standard network protocol BACnet/IP.

BACnet (Building Automation and Control networks) is a data communication protocol mainly used in the building automation and HVAC industry (Heating Ventilation and Air-Conditioning).

FTP

FTP (File Transfer Protocol) is a network protocol used for file exchange. _NetMan 204_ uses this protocol for:

1.  download of files of the device values and events history log archive (Datalog and Eventlog);
2.  download and upload of configuration files;
3.  firmware upgrade.

In both cases a client FTP is required, configured with these parameters:

*   *   Host: hostname or _NetMan 204_ IP address;
    *   User: see chapter “Users”;
    *   Password: current password.

The connection can also be established using a web browser (all the most popular web browsers are supported), by inserting the hostname or IP address of the _NetMan 204_.

Email

_NetMan 204_ can send a notification e-mail if one or more alarm conditions occur. The e-mails can be sent to up to three recipients and they can be sent for seven different kinds of alarm.

SMTP (Simple Mail Transfer Protocol) is the protocol used to send the e-mails. The port is configurable. For more details, see paragraph “Configuration”

Reports

_NetMan 204_ can send periodic e-mails with an attachment containing the files of the device values and events history log archive.

This service can be used to periodically save the history log archives.

The “Email” service must be enabled in order to send reports; the reports are sent to all the addresses configured for this service (for more details see paragraph “Configuration”).

Device values and events history log archive

_NetMan 204_ records the device values (Datalog) and events (Eventlog) in a history log database.

Eventlog

The Eventlog service is always active and records all relevant device events in the ‘event.db’ file. The file can be downloaded via FTP or can be viewed through the web page without credentials.

With the “Email report” service, is sent a .csv with the event of the last day or week according to your setting. The data are saved in circular list mode; thus the most recent data are saved by overwriting the oldest data.

Datalog (only for UPS devices)

The Datalog service records the main data of the UPS in the ‘datalog.db’ file.

This service writes a record each hour at 00 minutes, which summarizes the data of the past hour: values are recorded at their minimum, maximum and medium. Records older than one year get overwritten with new records.

The file can be downloaded via FTP or can be viewed through the web page (only the most important values are shown on the web page) without credentials.

With the “Email report” service, the last records (last day or last 7 days according to your settings) will be sent in a .csv format.

Environmental sensors (optional)

It is possibile to connect to _NetMan 204_ the environmental sensors for monitoring temperature, humidity and digital input/output.

The information provided by these sensors can be showed with the device monitoring and control software or with a web browser.

The values provided by the sensors may also be requested with SNMP according to the RFC 3433 standard (MIB files on the download site).

Available sensors

*   **_Temperature_**: detects the environmental temperature in °C.
*   **_Humidity &amp; Temperature_**: detects the relative humidity in % and the environmental temperature in °C.
*   **_Digital I/O &amp; Temperature_**: detects the environmental temperature in °C and features a digital input and a digital output.

|  | It is possible to connect up to 3 environmental sensor to a _NetMan 204_ (for sensor installation please see the sensors’ manual). |
| --- | --- |

INSTALLATION

1.  Remove the cover of the device expansion slot by removing the two retaining screws.
2.  Insert _NetMan 204_ in the slot.
3.  Secure _Netman 204_ in the slot using the two screws removed previously.
4.  Connect the device to the network by means of connector RJ-45 (see “Specifications for the cabling of the network cable”)

CONFIGURATION

Overview

_NetMan 204_ can be configured via USB, via SSH or via HTTP.

|  | _NetMan 204_ comes provided as factory default with DHCP enabled  and with the following services active: SSH, HTTP, SNMP, UDP and FTP. |
| --- | --- |
|  |  |
|  | In order to change the configuration of _NetMan 204_, you have to log in as admin (default password “admin”). |
| 5 |  |
|  | _NetMan 204_ needs approx. 2 minutes to become operational from when it is powered up or after a reboot; before this time the device may not respond to commands that are sent to it. |

Configuration via HTTP/HTTPS

In order to change the configuration via http/https, you have to insert in your web browser the hostname or IP address of the _NetMan 204_ and then log in as admin (default password: &quot;admin&quot;).

|  | The HTTPS service uses TLS (transport layer security) in order to provide cryptographic security. However, the certificate used is self-signed and therefore the web browser may prompt a security alert; in this case you can ignore the alert and proceed with the configuration of _NetMan 204_. |
| --- | --- |

Once login has been effected, you can browse through the menus to configure the _NetMan 204_.

|  | In order to make a new configuration effective, it is necessary to save it. Some changes are applied immediately, while other require a reboot of the _NetMan 204_ (as required with a pop-up by your web browser). |
| --- | --- |

Configuration via USB

To configure _NetMan 204_ via USB it is necessary to:

*   Connect, with the USB cable provided, the micro-USB port with the USB port of a PC with Windows operating system.
*   If not previously installed, install the USB driver (after driver installation, a virtual COM named “NetMan 204 Serial” will be present in device manager).
*   Execute a terminal emulation program with the following settings:COMn **<sup>(1)</sup>**, 115200 baud, no parity, 8 databits, 1 stop bit, no flow control.

**<sup>(1) </sup> **COMn = COM port assigned to “NetMan 204 Serial” by device manager.

*   Press the “Enter” key of the PC.
*   At the login prompt, enter “admin”.
*   At the password prompt, enter the current password (default password: &quot;admin&quot;).

|  | During password’s typing, no character is shown. |
| --- | --- |

Once login has been effected, the screen of the start menu is displayed. From this screen it is possible to access the various menus to change _NetMan 204_ settings (see paragraph “Start menu” and following paragraphs).

Configuration via SSH

To configure _NetMan 204_ via SSH it is necessary to:

*   Execute a SSH client on a PC connected in a network to _NetMan 204_ set with the IP address of the device to be configured.
*   At the login prompt, enter “admin”.
*   At the password prompt, enter the current password (default password: &quot;admin&quot;).

|  | During password’s typing, no character is shown. |
| --- | --- |

|  | For proper configuration of _NetMan 204_, you must configure the SSH client so that the backspace key sends &quot;Control-H&quot;. |
| --- | --- |

Once login has been effected, the screen of the start menu is displayed. From this screen it is possible to access the various menus to change _NetMan 204_ settings (see paragraph “Start menu” and following paragraphs).

Configuration menu description

|  | In order to make a new configuration effective, it is necessary to save it in the flash memory; this action automatically reboot the _NetMan 204_. |
| --- | --- |

Start menu

Once login has been effected via SSH or USB, a screen like the following is displayed:

| /------------------------/ |
| --- |

| **Function** | **Description** |
| --- | --- |
| Setup | To enter main configuration menu |
| View status | To see the status of the device |
| Change password | To modify the password (see also **Password recovery**) |
| Service log | To generate a log file of the card (when requested by the service) |
| Wi-Fi setup | To configure Wi-Fi connection |
| Factory reset | Restore factory configuration |
| Expert mode | To enter Expert mode (more information at paragraph “_Expert mode_”) |

To move within this menu and the following menus, use the keys as described in the following table; the arrow or the cursor shows the current selection.

| **Key** | **Function** |
| --- | --- |
| Direction keys (Arrow up, down, right, left) | To move the cursor within the menus |
| Tab | Goes on to next option |
| Enter <sup>(1)</sup> | Choice of submenu |
|  | Confirmation of characters entered |
| Esc <sup>(1)</sup> | Exit main menu <sup>(2)</sup> |
|  | Return to previous menu |

<sup>(1) </sup> Some keys can have a different function depending on the menu.

<sup>(2) </sup> To exit from a menu a confirmation (‘Y’ or ‘N’) is required after pressing the ESC key.

Setup

The main configuration menu displays a screen like the following:

| /------------------------/ |
| --- |

From this main menu it is possible to access the various submenus, the function of each of which is shown in the table below.

| **Menu** | **Function** |
| --- | --- |
| IP config | To configure the network parameters |
| Wi-Fi setup | To configure Wi-Fi connection |
| Enable Sensors | To enable the environmental sensors |
| Sensors Config | To configure the environmental sensors |
| Expert mode | To enter Expert mode (more information at paragraph “_Expert mode_”) |
| Factory reset | Restore factory configuration |

IP config

| /------------------------/ |
| --- |

With this menu the main network parameters can be set as described in the following table.

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Hostname | Enter the _NetMan 204_ host name |
| IP address/DHCP | Enter the IP address for a static IP; enter “DHCP” for a dynamic IP |
| Netmask | Enter the netmask to be used together with the static IP address |
| Gateway | Enter the name or the address of the network gateway |
| Primary DNS | Enter the name or the address of the preferred DNS to be used |
| Secondary DNS | Enter the name or the address of the alternative DNS to be used |

|  | If a static IP address is assigned to the device, all the fields must be configured with the network parameters. If a dynamic IP address is assigned, just enter ‘dhcp’ in the “IP Address/DHCP” field and provide a hostname; all the other options should be ignored because these are automatically configured with DHCP |
| --- | --- |

After pressing “ESC” and “Y” to confirm exit from the menu, a screen similar to the image below is displayed. Press the “ENTER” key to return to the main menu and the configuration will be immediately applied.

| eth0 Link encap:Ethernet HWaddr 00:02:63:04:07:b1 |
| --- |

Web configuration

After setting up the network, all the settings are available on the web configuration when logged is as “admin” user. Is not possible to have multiple concurrent sessions.

|  | The login password must contain alphanumeric characters and these special characters: ,._+:@%/-. No other characters are allowed to avoid malicious script injections. |
| --- | --- |

Please note that user “fwupgrade” and “user” are not allowed to log in on the web page. Either use “admin” or enter without password.

Network configuration

On the web page, is possible to configure in depth the network services of _NetMan 204_.

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Hostname | Enter the _NetMan 204_ host name |
| Static IP/DHCP | Choose between static IP or dynamic IP |
| IP Address | Enter the IP address |
| Netmask | Enter the netmask to be used together with the static IP address |
| Gateway | Enter the name or the address of the network gateway |
| Primary DNS | Enter the name or the address of the preferred DNS to be used |
| Secondary DNS | Enter the name or the address of the alternative DNS to be used |
| Enable SSH protocol | Enables the SSH service |
| Enable FTP protocol | Enables the FTP protocol |
| Enable Serial network tunneling | Enables the serial network tunnelling protocol |
| Enable HTTP | Enables HTTP service |
| HTTP port | Enter the port where HTTP service is started (default: 80) |
| Enable HTTPS | Enable HTTPS service |
| HTTPS port | Enter the port where HTTPS service is started (default: 443) |
| Enable UDP | Enables UDP/UPSMon service |
| UDP port | Enter the port where the UDP/UPSMon service is started **<sup>(1)</sup>** |
| UDP Password | To change the password used for UDP/UPSMon communication |

**<sup>(1)</sup>** This port must be the same as configured in the UPSMon software

Device configuration

| **Field** | **Parameters to be inserted** |
| --- | --- |
| PRTK Code | Enter the PRTK code indicated at the back of the device |
| Name | Enter the identifying name of the device |

Data log

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable Data log | Enables the datalog service |
| Backup UPS data log at boot | At boot _NetMan 204_ downloads the data log of the device for quick access |

UDP Firewall

With this menu the IP addresses or hostnames of the devices enabled for communication with _NetMan 204_ can be configured. The character “*****” can be used for one or more fields of the IP address to indicate that all values between 0 and 255 are accepted in that field. The following table provides some possible configuration examples.

| **IP Access** | **Description** |
| --- | --- |
| *.*.*.* | All the devices present on the network are enabled to communicate with _NetMan 204_ (default configuration) |
| 10.1.10.* | The devices with addresses between 10.1.10.0 and 10.1.10.255 are enabled to communicate with _NetMan 204_ |
| myserver.mydomain | Hostname of the device enabled to communicate with _NetMan 204_ |

Wake on Lan address

With this menu is possible to insert up to 8 MAC address to execute Wake-on-LAN, and the delay times for each Wake-on-LAN. The Wake-on-LAN is sent at _NetMan 204_ boot and when the mains returns from black-out.

|  | Please make sure that the target PC supports this function and that is properly configured. |
| --- | --- |

SNMP

For configuring SNMP, is possible to use the wizard web page for a simple configuration. Advanced configuration requires to edit snmp.conf (please see chapter “SNMP configuration”).

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable SNMP protocol | Enables the SNMP service |
| Contact | Enter the string to be associated with these SNMP variable |
| Name | Enter the string to be associated with these SNMP variable |
| Location | Enter the string to be associated with these SNMP variable |
| Battery replacement notification | Enter the date to be notified when battery should be replaced |
| Configuration mode | Choose between wizard configuration or to upload a configuration file |
| SNMP version | Choose between SNMPv1/v2 or SNMPv3 |
| Get community | Enter the community for read access |
| Set community | Enter the community for write access |
| Trap community | Enter the community for traps |
| Trap receiver | Enter the IP addresses to which traps are sent |
| Username | Enter the USM username |
| Auth | Enter the authentication algorithm |
| Priv | Enter the privacy algorithm |
| AuthPassword | Enter the authentication password |
| PrivPassword | Enter the privacy password |
| Permissions | Choose the permissions for each users |

MODBus/BACNET

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable MODBUS | Enables the MODBUS protocol |
| Enable BACNET | Enables the BACNET protocol |
| BACNET Address (Number) | Enter the BACNET address of the device |
| BACNET Client (IP) | Enter the IP address of the bacnet client |

JSON

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable JSON | Enables the JSON notification service |
| Monitoring host IP | Enter the IP address to which send the JSON traps |
| Host port | Enter the port where traps will be sent |
| Notification interval (minutes) | Enter the interval between JSON trap sending |
| Send notification on event | Choose the even upon which the trap will be sent |

Date &amp; Time configuration

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Date | Enter the current date |
| Hour | Enter the current hour |
| Minutes | Enter the current minutes |

NTP &amp; Timezone configuration

With this menu is possible to schedule the NTP synchronization. Is possible to specify the time and frequency for performing a synchronization. For each field is possible to enter the precise condition or leaving ‘*’ which means always.

| **Field** | **Parameters to be inserted** |
| --- | --- |
| NTP server address (IP) | Enter the name or address of the NTP server |
| Hour of a day | Enter the hour when the synchronization should occur, or ‘*’ |
| Day of week | Enter the day of week when the synchronization should occur, or ‘*’ |
| Day of month | Enter the day of month when the synchronization should occur, or ‘*’ |

|  | Only for UPS with PRTK code SENTR.., if a valid NTP server is configured, _NetMan 204_ will synchronize the clock of the UPS every time the NTP synchronization occurs. |
| --- | --- |

Email configuration

This menu may be used to configure the addresses to which to send the alarm notification and report e-mails and other parameters of the e-mail service as described in the following table.

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable Email | Enables the Email service |
| Mail host | Enter the name or the address of the SMTP server to be used to send e-mails. **<sup>(1)</sup>** |
| SMTP port | The IP port used by the SMTP protocol |
| Sender address | Enter the address from which the e-mails are sent. **<sup>(2)</sup>** |
| Username | If the server requires authentication, insert the “User name”. |
| Password | If the server requires authentication, insert the password. |
| Transport | It is possible to choose between plain, SSL or TLS. |
| Email #1 | Enter the e-mail addresses to which to send the alarm notifications and reports (see note). |
| Email #2 |  |
| Email #3 |  |
| Device events | Choose the event upon which the email will be sent |
| Send report every day | Sends the email report every day at 00:00. |
| Send report every week | Sends the email report every Monday at 00:00. |

**<sup>(1) </sup> **Ensure that the SMTP server accepts connections on the configured port.

**<sup>(2)</sup>** Do not use the “space” character in this field

After inserting the data and saving, the service can be tested. If the test is performed, a test email is sent to all the configured email addresses.

|  | Report e-mails are sent to all the addresses inserted; for alarm notification e-mails see paragraph “_Email logic_”. |
| --- | --- |

Email logic

The following table describes the meaning of the events. These can vary depending on the device connected.

| **Event** | **Meaning** |
| --- | --- |
| Device Lock | Device is locked or in a severe failure state |
| Ovrload/Ovrtemp | Device in overload or in overtemperature |
| General Failure | Failure of the device |
| On bypass | Operation from bypass |
| Input blackout | The input source is in blackout |
| Battery low | Battery low |
| Communic lost | Communication between the _Netman 204_ and the device has been interrupted |

GSM Modem

This menu may be used to configure the GSM modem in order to send SMS.

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable SMS | Enables the SMS service |
| GSM carrier | Enter the phone number of the carrier |
| SMS #1 | Phone numbers that will receive SMS |
| SMS #2 |  |
| SMS #3 |  |
| Device events | Choose the events upon which the SMS will be sent |

Sensors

| **Field** | **Parameters to be inserted** |
| --- | --- |
| Enable sensors | Enables the sensor service |
| Contact logic | Choose between normally open or normally closed |
| Ouput contact | Choose the output signal to be activated on event |
| Temperature high [°C] | Enter the high temperature threshold |
| Temperature low [°C] | Enter the low temperature threshold |
| Temperature hysteresis [°C] | Enter the temperature hysteresis |
| Humidity high [%RH] | Enter the high humidity threshold |
| Humidity low [%RH] | Enter the how humidity threshold |
| Humidity hysteresis [%RH] | Enter the humidity hysteresis |

|  | As well as being configured, the sensors must also be activated to function correctly (see paragraph “_Sensors config_”). |
| --- | --- |

Sensors Config

|  | To enter on the “Sensors config” menu is necessary to enable the “Sensors” service and to reboot the _NetMan 204_. |
| --- | --- |

| Sensor list |
| --- |

Enter on the “Config sensor” menu, connect the first sensor and press “C”. After some instants the device will be recognized and the device will be given an identifier number [1]. Connect the next sensor, if present, and press “N”. After some instants the device will be recognized and the device will be given an identifier number [2]. Repeat the procedure for all the sensors and when the configuration is finalized press “Y”.

| Sensor list |
| --- |

|  | For proper working of the devices, it is necessary to add just one device for each iteration and wait that it is recognized by _NetMan 204_. |
| --- | --- |

Example: how to connect a _Temperature_ sensor, a _Humidity &amp; Temperature_ sensor and a _Digital I/O &amp; Temperature_ sensor in exactly this order.

| Sensor list |
| --- |

Connect the first sensor (_Temperature_), and press “C”.

| Sensor list |
| --- |

Wait until the first sensor is identified and then connect the second sensor (_Humidity &amp; Temperature_), and press “N”.

| Sensor list |
| --- |

Wait until the second sensor is identified and then connect the third sensor (_Digital I/O &amp; Temperature_), and press “N”.

| Sensor list |
| --- |

Press “Y” to confirm.

Password recovery

If the default password for the admin user is changed and forgotten, it is possible to recover it with the unlock key provided by the service department of the manufacturer.

To obtain the unlock key, you must send to the service department the service code of your _NetMan 204_. This code can be read via USB, via SSH or via HTTP.

Via USB or SSH, log in to _NetMan 204_ with user &quot;user&quot; and password &quot;user&quot;.

Via HTTP when you insert an incorrect password you are offered a link to a password recovery. Click the link to start the recovery.

In both case a message like this will be shown:

To restore the default password, please enter the unlock key.

If you don&#039;t know it, please send to service this code:

204:XX:XX:XX:XX:XX:XX

|  | Please note that the unlock key is valid only for the corresponding service code which is specific for every _NetMan 204_. |
| --- | --- |

Wi-Fi setup (optional card required)

|  | For Wi-Fi connection, an optional card is required. The Wi-Fi card is not provided with _NetMan 204_ but it has to be purchased separately. |
| --- | --- |

After installing the optional Wi-Fi card, you can access to the &quot;Wi-Fi setup&quot; menu.

|  | For _NetMan 204_, Wi-Fi is an exclusive alternative to cabled Ethernet: only one at time can be used. Therefore, after enabling Wi-Fi, it is not more possible to use cabled Ethernet. |
| --- | --- |

After selecting Wi-Fi setup you get this prompt:

| Wi-Fi Configuration |
| --- |

Insert &#039;n&#039; to use Ethernet or &#039;y&#039; to use Wi-Fi. In the latter case, a list of available Wi-Fi access points will be shown with the following request:

| Please insert the SSID you want to connect without quotes |
| --- |

Type the SSID of the desired Wi-Fi access point.

| Please insert the password for &lt;Wi-Fi access point&gt; |
| --- |

Here you insert the authentication password for Wi-Fi.

| OK, you want to connect to &lt;Wi-Fi access point&gt; with password &lt;Wi-Fi password&gt;. |
| --- |

After confirmation, you will return to the Main setup. At the next boot the _NetMan 204_ will use Wi-Fi instead of Ethernet.

Expert mode

Expert mode enables the configuration of advanced parameters that should be set by skilled technicians. These commands are supported:

help prints the help

get shows all values

set &lt;VAR&gt; &lt;VALUE&gt; set VAR to VALUE

delete &lt;VAR&gt; removes VAR

sendtrap &lt;TRAPCODE&gt; send a test SNMP trap

testemail send a test email

reboot reboot the _NetMan 204_

erasefram erase the FRAM module

clearlog clear data log and event log

exit closes the connection

Configuration of several devices

If several _NetMan 204_ have to be configured with similar parameters, you can configure the first _NetMan 204_, then connect via FTP with the admin user, download all the configuration files in the folder /cfg, and upload all them via FTP in the folder /cfg of all devices to be configured.

Firmware upgrade

The _NetMan 204_ firmware can be updated via HTTP or via FTP.

Firmware upgrade via HTTP

Connect via HTTP to the _NetMan 204_ to be upgraded inserting in your web browser the hostname or IP address and then log in as admin (default password: “admin”). Then click on the “Administration” page.

Drag and drop the upgrade file. When the upgrade file is uploaded, the _NetMan 204_ will reboot automatically.

Firmware upgrade via FTP

Connect via FTP with the user “fwupgrade” (default password “fwupgrade”) and copy the updated firmware on the /fwupgrade folder. Then restart the card by pressing the reset button

SNMP configuration

For configuring SNMP, is possible to use the wizard web page for a simple configuration. Advanced configuration requires to edit snmp.conf. This file can be downloaded and uploaded from the web page or via FTP with user “admin” (default password: “admin”).

Each line of the file is parsed by _NetMan 204_ and must begin with one of these keyword:

*   #: for comment, the line is skipped.
*   addUser: for adding a new user and setting the passwords
*   addGroup: for putting a user into a group
*   addAccessEntry: for enabling access privileges to a group
*   addView: for adding privileges
*   addManager: for adding SNMP Manager which will receive SNMP traps.

The correct syntax for addUser is:

addUser &lt;userName&gt; &lt;authProtocol&gt; &lt;privProtocol&gt; &lt;authPassword&gt; &lt;privPassword&gt;

&lt;userName&gt; is the name of the user.

&lt;authProtocol&gt; is the protocol for authentication of this user during SNMP sessions. Possible values are:

*   noauth (no authentication will be used)
*   md5 (MD5 will be used for authentication)
*   sha (SHA will be used for authentication)

&lt;privProtocol&gt; is the protocol for privacy of this user during SNMP sessions. Possible values are:

*   nopriv (no privacy will be used)
*   des (DES will be used for privacy)

&lt;authPassword&gt; is the password for authentication. It must be set to * when not used.

&lt;privPassword&gt; is the password for privacy. It must be set to * when not used.

The correct syntax for addGroup is:

addGroup &lt;securityModel&gt; &lt;userName&gt; &lt;groupName&gt;

&lt;securityModel&gt; is the security model. When using authentication and/or privacy, securityModel must be USM. Possible values are:

*   USM (User-based Security Model with SNMPv3)
*   v2 (SNMPv2)
*   v1 (SNMPv1)

&lt;userName&gt; is the name of the user, must match one of the user name defined with addUser.

&lt;groupName&gt; is the name of the group.

Please note that a userName can be assigned to only one group.

The correct syntax for addAccessEntry is:

addAccessEntry &lt;groupName&gt; &lt;contextName&gt; &lt;securityModel&gt; &lt;securityType&gt; &lt;contextMatch&gt; &lt;readView&gt; &lt;writeView&gt; &lt;notifyView&gt;

&lt;groupName&gt; is the name of the group to which this access right applies, must match one of the group name defined with addGroup.

&lt;contextName&gt; is the name of the context.

&lt;securityModel&gt; is the security model that must be used in order to gain access to this access right, must match the security model defined with addGroup.

&lt;securityType&gt; is the minimum security level that must be used to gain access to this access right. Possible values are:

*   noauthnopriv (no authentication and no privacy)
*   authnopriv (authentication but no privacy)
*   authpriv (authentication and privacy)

&lt;contextMatch&gt; the type of match required. Possible values are:

*   exact (the context name must exactly match the value in contextName)
*   prefix (the context name must match the first few starting characters of the value in contextName)

&lt;readView&gt; the authorized MIB view name used for read access, must match one of the view name.

&lt;writeView&gt; the authorized MIB view name used for write access, must match one of the view name.

&lt;notifyView&gt; the authorized MIB view name used for notify access, must match one of the view name.

The correct syntax for addView is:

addView &lt;viewName&gt; &lt;subtree&gt; &lt;mask&gt; &lt;included&gt;

&lt;viewName&gt; is the name of the view.

&lt;subtree&gt; is the OID subtree which when combined with the corresponding instance of MASK defines a family of view subtrees.

&lt;mask&gt; the mask for filtering OID.

&lt;included&gt; the OID can be included or excluded. Possible values are:

*   included (for including)
*   excluded (for excluding)

The correct syntax for addManager is:

addManager &lt;security&gt; &lt;ipAddress&gt; &lt;credentials&gt; &lt;securityType&gt;

&lt;security&gt; is the security type for the notification. Possible values are:

*   USM (User-based Security Model with SNMPv3)
*   V2 (SNMPv2)
*   v1 (SNMPv1)

&lt;ipAddress&gt; is the IP address of the SNMP manager.

&lt;credentials&gt; is either the user name (when using USM security) or the trap community (when using v1 security)

&lt;securityType&gt; is either:

*   noauthnopriv (for SNMPv1 and SNMPv2)
*   authpriv (for SNMPv3)

addManager do not allow duplicate entries (one ipAddress can receive only one trap).

A sample snmp.conf is provided; the default users authorized are:

| **Name** | **Auth protocol** | **Priv protocol** | **Auth password** | **Priv password** |
| --- | --- | --- | --- | --- |
| unsecureUser | Noauth | nopriv |  |  |
| MD5 | md5 | nopriv | MD5UserAuthPassword |  |
| SHA | Sha | nopriv | SHAUserAuthPassword |  |
| MD5DES | md5 | des | MD5DESUserAuthPassword | MD5DESUserPrivPassword |
| SHADES | Sha | des | SHADESUserAuthPassword | SHADESUserPrivPassword |

Modbus TCP/IP protocol

**_This service is active on the TCP port 502\. The supported function are listed below, together with the accessible registers._**

Supported function

| **SUPPORTED FUNCTION** | **FUNCTION DESCRIPTION** | **ACCESSIBLE DATA AREA** |
| --- | --- | --- |
| 1 (0x01) | BIT READING | STATES |
| 2 (0x02) |  | STATES |
| 3 (0x03) | REGISTERS READING | ALL |
| 4 (0x04) |  | ALL |
| 6 (0x06) | SINGLE REGISTER WRITING | COMMANDS |
| 16 (0x10) | MULTIPLE REGISTER WRITING | COMMANDS |

UPS: Tables of states, measurements, nominal data and commands

| REGISTER<sup>(1)</sup> | UPS - STATES | BIT<sup>(2)</sup> |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  | **NUMBER** | **ADDRESS** |
| 1 | 0 |  | 1 | 0 |
|  |  | Test in progress [0=No / 1=YES] | 2 | 1 |
|  |  |  | 3 | 2 |
|  |  | Shutdown active [0=No / 1= YES] | 4 | 3 |
|  |  |  | 5 | 4 |
|  |  | Battery charged [0=No / 1= YES] | 6 | 5 |
|  |  | Battery charging [0=No / 1= YES] | 7 | 6 |
|  |  | Bypass bad [0=No / 1= YES] | 8 | 7 |
|  |  |  | 9 | 8 |
|  |  | Normal operation [0=No / 1= YES] | 10 | 9 |
|  |  |  | 11 | 10 |
|  |  | On bypass [0=No / 1= YES] | 12 | 11 |
|  |  | Battery low [0=No / 1= YES] | 13 | 12 |
|  |  | Battery working [0=No / 1= YES] | 14 | 13 |
|  |  | UPS locked [0=No / 1= YES] | 15 | 14 |
|  |  | Output powered [0=No / 1= YES] | 16 | 15 |
| 2 | 1 |  | 1728 | 1627 |
|  |  | Input Mains present [0=No / 1= YES] | 29 | 28 |
|  |  | Alarm temperature [0=No / 1= YES] | 30 | 29 |
|  |  | Alarm overload [0=No / 1= YES] | 31 | 30 |
|  |  | UPS failure [0=No / 1= YES] | 32 | 31 |
| 3 | 2 |  | 3348 | 3247 |
| 4 | 3 |  | 4963 | 4862 |
|  |  | Communication lost with UPS [0=No / 1= YES] | 64 | 63 |
| 58 | 47 |  | 65128 | 64127 |

**<sup>(1) </sup> **_The register number_ **_n_** _must be addressed_ **_n-1_** _in the data packet_

**<sup>(2) </sup> **_The bit number_ **_n_** _must be addressed_ **_n-1_** _in the data packet._

| **REGISTER<sup>(1)</sup>** | **UPS - MEASUREMENTS** | **UNIT** |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 911 | 810 |  |  |
| 12 | 11 | Input mains star voltage V1 | V |
| 13 | 12 | Input mains star voltage V2 | V |
| 14 | 13 | Input mains star voltage V3 | V |
| 15 | 14 | Input current phase L1 | 0.1*A |
| 16 | 15 | Input current phase L2 | 0.1*A |
| 17 | 16 | Input current phase L3 | 0.1*A |
| 18 | 17 | Input frequency | 0.1*Hz |
| 1921 | 1820 |  |  |
| 22 | 21 | Bypass mains star voltage V1 | V |
| 23 | 22 | Bypass mains star voltage V2 | V |
| 24 | 23 | Bypass mains star voltage V3 | V |
| 25 | 24 | Bypass frequency | 0.1*Hz |
| 26 | 25 | Output star voltage V1 | V |
| 27 | 26 | Output star voltage V2 | V |
| 28 | 27 | Output star voltage V3 | V |
| 2931 | 2830 |  |  |
| 32 | 31 | Output current phase L1 | 0.1*A |
| 33 | 32 | Output current phase L2 | 0.1*A |
| 34 | 33 | Output current phase L3 | 0.1*A |
| 35 | 34 | Output peak current phase L1 | 0.1*A |
| 36 | 35 | Output peak current phase L2 | 0.1*A |
| 37 | 36 | Output peak current phase L3 | 0.1*A |
| 38 | 37 | Load phase L1 | % |
| 39 | 38 | Load phase L2 | % |
| 40 | 39 | Load phase L3 | % |
| 41 | 40 | Output active power phase L1 | 0.1 kW |
| 42 | 41 | Output active power phase L2 | 0.1 kW |
| 43 | 42 | Output active power phase L3 | 0.1 kW |
| 44 | 43 | Output frequency | 0.1*Hz |
| 4547 | 4446 |  |  |
| 48 | 47 | Battery voltage | 0.1*V |
| 49 | 48 | Positive battery voltage | 0.1*V |
| 50 | 49 | Negative battery voltage | 0.1*V |
| 51 | 50 | Battery current | 0.1*A |
| 52 | 51 | Remaining Battery Capacity | % |
| 53 | 52 |  |  |
| 54 | 53 | Remaining back-up time | Minutes |
| 5558 | 5457 |  |  |
| 59 | 58 | Total output energy (32 bit) | Least Significant Register | 0.1 kWh |
| 60 | 59 |  | Most Significant Register |  |
| 61 | 60 |  |  |
| 62 | 61 | Internal UPS temperature | °C |
| 63 | 62 | Sensor 1 temperature | °C |
| 64 | 63 | Sensor 2 temperature | °C |
| 6572 | 6471 |  |  |

**<sup>(1) </sup> **_The register number_ **_n_** _must be addressed_ **_n-1_** _in the data packet._

|  | Some measures may not be available for all the UPS. In this case, the relative register remains at 0xFFFF value. |
| --- | --- |

| REGISTER<sup>(1)</sup> | UPS – NOMINAL DATA | UNIT |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 7377 | 7276 |  |  |
| 78 | 77 | Output nominal voltage (star) | V |
| 79 | 78 | Output nominal frequency | 0.1*Hz |
| 80 | 79 | Output nominal power | 100*VA |
| 8183 | 8082 |  |  |
| 84 | 83 | Battery nominal capacity (battery expansion included) | Ah |
| 85 | 84 | Battery benches | (1 or 2) |
| 86 | 85 | Battery type | Integer |
| 87112 | 86111 |  |  |

| **REGISTER<sup>(1)</sup>** | **UPS - COMMANDS** | **UNIT** |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 113 | 112 | Command code **<sup>(2)</sup>** | Integer |
| 114 | 113 | Shutdown delay time | Seconds |
| 115 | 114 | Restore delay time | Minutes |
| 116 | 115 |  |  |
| 117 | 116 | Command result **<sup>(3)</sup>** | Integer |
| 118 | 117 |  |  |

| **REGISTER<sup>(1)</sup>** | **DIAGNOSTIC** | **UNIT** |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 119 | 118 | Counter of processed correct messages | Integer |
| 120 | 119 | Counter of processed NOT correct messages | Integer |

**<sup>(1) </sup> **_The register number_ **_n_** _must be addressed_ **_n-1_** _in the data packet._

**<sup>(2) </sup> **_Refer to “Command codes” paragraph_

**<sup>(3) </sup> **_Command result = Command code if command is handled from the UPS_

_Command result = Command code + 100 if command is NOT handled from the UPS_

_Command result = 0 if Command code is wrong_

| **REGISTER<sup>(1)</sup>** | **SPECIAL FLAGS (SENTR UPS) <sup> (2)</sup>** | **UNIT** |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 121 | 120 | Byte 1 of “s = xx..” code / Byte 2 of “s = ..xx” code | Flag |
| 122 | 121 | Byte 1 of “c = xx..” code / Byte 2 of “c = ..xx” code | Flag |
| 123 | 122 | Byte 1 of “b = xx..” code / Byte 2 of “b = ..xx” code | Flag |
| 124 | 123 | Byte 1 of “r = xx..-..” code / Byte 2 of “r = ..xx-..” code | Flag |
| 125 | 124 | Byte 3 of “r = ....-xx” code / Byte 1 of “i = xx..-..” code | Flag |
| 126 | 125 | Byte 2 of “i = ..xx-..” code / Byte 3 of “i = ....-xx” code | Flag |
| 127 | 126 | Byte 1 of “a = xx..-....” code / Byte 2 of “a = ..xx-....” code | Flag |
| 128 | 127 | Byte 3 of “a = ....-xx..” code / Byte 4 of “a = ....-..xx” code | Flag |

| **REGISTER<sup>(1)</sup>** | **NETMAN DATA** | **UNIT** |
| --- | --- | --- |
| **NUMBER** | **ADDRESS** |  |  |
| 129 | 128 | Firmware version | Integer |
| 130÷131 | 129÷130 |  |  |

**<sup>(1) </sup> **_The register number_ **_n_** _must be addressed_ **_n-1_** _in the data packet._

**<sup>(2) </sup> **_In order to decode these registers, please refer to the UPS manual._

UPS: Commands codes

| **CODE** | **COMMAND** |
| --- | --- |
| 1 (0x0001) | Command Shutdown |
| 2 (0x0002) | Command Shutdown and Restore |
| 3 (0x0003) | Delete Command (code 1, 2, 12) |
| 12 (0x000C) | UPS on Bypass |
| 20 (0x0014) | Test Battery |
| 22 (0x0016) | Test Panel |

bacnet/IP configuration

| **OBJECT** | **DESCRIPTION** | **UNIT** |
| --- | --- | --- |
| Analogue Input 0 | Input voltage line 1 | V |
| Analogue Input 1 | Input voltage line 2 | V |
| Analogue Input 2 | Input voltage line 3 | V |
| Analogue Input 3 | Input current line 1 | A |
| Analogue Input 4 | Input current line 2 | A |
| Analogue Input 5 | Input current line 3 | A |
| Analogue Input 6 | Input frequency | Hz |
| Analogue Input 7 | Bypass voltage line 1 | V |
| Analogue Input 8 | Bypass voltage line 2 | V |
| Analogue Input 9 | Bypass voltage line 3 | V |
| Analogue Input 10 | Bypass frequency | Hz |
| Analogue Input 11 | Output voltage line 1 | V |
| Analogue Input 12 | Output voltage line 2 | V |
| Analogue Input 13 | Output voltage line 3 | V |
| Analogue Input 14 | Output current line 1 | A |
| Analogue Input 15 | Output current line 2 | A |
| Analogue Input 16 | Output current line 3 | A |
| Analogue Input 17 | Output peak current line 1 | A |
| Analogue Input 18 | Output peak current line 2 | A |
| Analogue Input 19 | Output peak current line 3 | A |
| Analogue Input 20 | Output power line 1 | W |
| Analogue Input 21 | Output power line 2 | W |
| Analogue Input 22 | Output power line 3 | W |
| Analogue Input 23 | Output frequency | Hz |
| Analogue Input 24 | Output load line 1 | % |
| Analogue Input 25 | Output load line 2 | % |
| Analogue Input 26 | Output load line 3 | % |
| Analogue Input 27 | Battery voltage | V |
| Analogue Input 28 | Battery current | A |
| Analogue Input 29 | Battery capacity | % |
| Analogue Input 30 | UPS temperature | °C |
| Analogue Input 31 | Autonomy | min |
| Analogue Input 32 | Nominal power | VA |
| Binary Input 0 | Mains status | Present / Not present |
| Binary Input 1 | Bypass status | Active / Not active |
| Binary Input 2 | Battery status | Working / Not working |
| Binary Input 3 | Battery level | Low / Not low |
| Binary Input 4 | UPS locked | Locked / Not locked |
| Binary Input 5 | UPS fail | Fail / Not fail |
| Binary Input 6 | Load | Overload / Normal |
| Binary Input 7 | Temperature | Overtemperature / Normal |
| Binary Input 8 | Bypass bad | Bad / Not bad |
| Binary Input 9 | Replace battery | Replace / Not replace |
| Binary Input 10 | Shutdown | Active / Not active |
| Binary Input 11 | Shutdown imminent | Imminent / Not imminent |
| Binary Input 12 | Communication status | Lost / OK |
| Analog Input 33 | System status group 1 |  |
| Analog Input 34 | System status group 2 |  |
| Analog Input 35 | System status group 3 |  |
| Analog Input 36 | Bypass module alarms |  |
| Analog Input 37 | Power module 1 alarms |  |
| Analog Input 38 | Power module 2 alarms |  |
| Analog Input 39 | Power module 3 alarms |  |
| Analog Input 40 | Power module 4 alarms |  |
| Analog Input 41 | Power module 5 alarms |  |
| Analog Input 42 | Power module 6 alarms |  |
| Analog Input 43 | Power module 7 alarms |  |
| Analog Input 44 | Bypass module status |  |
| Analog Input 45 | Power module 1 status |  |
| Analog Input 46 | Power module 2 status |  |
| Analog Input 47 | Power module 3 status |  |
| Analog Input 48 | Power module 4 status |  |
| Analog Input 49 | Power module 5 status |  |
| Analog Input 50 | Power module 6 status |  |
| Analog Input 51 | Power module 7 status |  |

SERIAL PORT configuration

| **RJ-12 – SERIAL port** |
| --- |
|  |
| **POSITION** | **DESCRIPTION** |
| 1 | +5V<sub>DC</sub> |
| 2 | GND |
| 3 | Environmental sensors bus |
| 4 | GND |
| 5 | RXD |
| 6 | TXD |

| **NetMan 204** |  | **Modem** |
| --- | --- | --- |
| **RJ-12** |  | **DB-25** | **DB-9** | **DESCRIPTION** |
| **POSITION** | **DESCRIPTION** |  | **POSITION** | **POSITION** |  |
| 1 | +5V<sub>DC</sub> | **LEAVE UNCONNECTED** |  |  |  |
| 2 | GND |  |  |  |  |
| 3 | Environmental sensors bus |  |  |  |  |
| 4 | GND | **CONNECT TO** | 7 | 5 | GND |
| 5 | RXD | **CONNECT TO** | 3 | 2 | TXD |
| 6 | TXD | **CONNECT TO** | 2 | 3 | RXD |

TECHNICAL DATA

Network cable

To connect the device to the Ethernet (10Base-T) or Fast Ethernet (100Base-T) network, a UTP (Unshielded Twisted Pair) or STP (Shielded Twisted Pair) cable with RJ45 connectors is required. The cable must conform to the standard IEEE 802.3u 100Base-T with 2 pairs of UTP cables of category 5 or higher. The cable between the adaptor and the hub must not be more than 100m and not less than 2.5m.

| **NETWORK CABLE CONNECTIONS** |
| --- |
| **Signal** | **Pin # to Pin #** |
| TX+ | 1 1 |
| TX- | 2 2 |
| RX+ | 3 3 |
| RX- | 6 6 |

|  | Pins 1 and 2 must be connected to one twisted pair, pins 3 and 6 to another. |
| --- | --- |

Operating and storage conditions

| Operating temperature range | [°C] | 0 ÷ +40 |
| --- | --- | --- |
| Storage temperature range | [°C] | -5 ÷ +50 |
| Maximum operating relative humidity | [%] | 80 |
| Maximum storage relative humidity | [%] | 90 |