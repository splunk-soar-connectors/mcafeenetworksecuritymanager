[comment]: # "Auto-generated SOAR connector documentation"
# McAfee Network Security Manager

Publisher: Martin Ohl  
Connector Version: 1\.0\.9  
Product Vendor: McAfee  
Product Name: NSM  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 3\.0\.251  

This app supports multiple containment actions on the McAfee NSM


The asset requires the user to configure a Sensor ID. Leave it blank and run Test Connectivity. The
action will display a list of Sensor IDs configured on the NSM server. Set the required value and
run Test Connectivity again to complete configuration.


### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a NSM asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**ip** |  required  | string | IP Address or Hostname
**verify\_server\_cert** |  required  | boolean | Verify server certificate
**user** |  required  | string | Username \(Super User\)
**pw** |  required  | password | Password
**sensor\_id** |  optional  | numeric | Sensor ID

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[block ip](#action-block-ip) - Block an IP  
[unblock ip](#action-unblock-ip) - Unblock an IP  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'block ip'
Block an IP

Type: **contain**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to block | string |  `ip` 
**duration** |  required  | Duration time \(sec\) of quarantine \(15, 30, 45, 60, 240, 300, \.\.\., 999\) | numeric | 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.parameter\.duration | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'unblock ip'
Unblock an IP

Type: **correct**  
Read only: **False**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**ip** |  required  | IP to unblock | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.ip | string |  `ip` 
action\_result\.status | string | 
action\_result\.message | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 