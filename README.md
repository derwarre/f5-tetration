# F5 BIG-IP and Cisco Tetration Analytics
This repo provides information on how to configure BIG-IP devices in Cisco Tetration Solution. BIG-IP sends the flow information to the Tetration Sensors in IPFIX format this makes flows visible in Tetration Analytics software.

### Repo Details
Repo has two directories [irules](https://github.com/f5devcentral/f5-tetration/tree/master/irules/) and [scripts](https://github.com/f5devcentral/f5-tetration/tree/master/scripts). irules directory has  F5 BIG-IP irules for IPFIX. The irules facilitate sending the flow information to the Tetration Sensors. The scripts directory has the irule JSON payload and install and clean scripts.

### How to use this Repo
1. Clone the repo to your local machine
` git clone https://github.com/f5devcentral/f5-tetration.git`
2. Change directory to scripts
`cd f5-tetration/scripts/`
3. Run install script
``` sh install.sh
 Attention --->  Please Enter Contrl C to Quit this Program ....

 This script will automatically deploy the iRules required for Tetration  

Please enter BIG-IP Management IP :  X.X.X.X
Please enter BIG-IP ADMIN USER :  admin
Please enter BIG-IP PASSWORD :  xxxx
Irule Exists locally on your machine  .. hit enter...to proceed
Checking if irule Exists on BIG-IP ......
Checking if IPX Pool exists  on BIG-IP for Tetration Collector ....
IPFIX Pool is not configured on your BIG-IP  .....
Enter Pool Member or Sensor Address 100.1.1.1
Enter Pool Member or Sensor Address  100.1.1.2
Enter Pool Member or Sensor Address  100.1.1.3
Creating IPXPool on BIG-IP required for Tetration Collector ....... {
    "allowNat": "yes",
```
4. Attach irule to All Virtual Servers
```
You have following Virtual Server  t1 t2 t3 t5_dup
Do you wish to apply ipfix irule to all  Virtual Server  say y or n...?
y
Attaching irule to all Virtual Servers .....
```
5. IF you want to Select only specific Virtual Server then say 'n' on 4th step & proceed as follows
```You have following Virtual Server  t1 t2 t3 t5_dup
Do you wish to apply ipfix irule to all  Virtual Server  say y or n...?
n
Do you wish to attach iRule to the Virtual Server say y or n  t1 ...?
n
Do you wish to attach iRule to the Virtual Server say y or n  t2 ...?
y
```
