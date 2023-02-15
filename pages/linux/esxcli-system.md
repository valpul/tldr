# settings

> In this section, you can see the commands of the system esxcli namespace.
> See also: `sample1`, `sample2`.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- Check the precise ESXi version and build number, including the number of installed updated and patches:

`esxcli system version get`

- Check the hostname of an ESXi server:

`esxcli system hostname get`

- Check the ESXi installation time:

`esxcli system stats installtime get`

- Check the SNMP configuration:

`esxcli system snmp get`

- Enter the ESXi host to the maintenance mode:

`esxcli system maintenanceMode set --enable yes`

- Exit the maintenance mode:

`esxcli system maintenanceMode set --enable no`
> 
> After entering an ESXi host to the maintenance mode, you can shut down or reboot the host:

- Power off an ESXi host:

`esxcli system shutdown poweroff`

- The command for rebooting the host is similar:

`esxcli system shutdown reboot`
> 
> You can also set a delay and write a reason of rebooting the host to be saved in system logs.

- In this example, the delay is 60 seconds:

`esxcli system shutdown reboot -d 60 -r “Installing patches”`
> 
> Another command is to set the custom welcome message instead of a standard background screen with a shaded inactive main menu where the “F2 Customize System/View Logs F12 Shut Down/Restart” tip and the IP address to manage the host are displayed. 

- The custom message can be used for hiding information about your ESXi host on the display connected to the ESXi host when a user is not logged in

`esxcli system welcomemsg set -m="Welcome to NAKIVO! Press F2"`

- Verify whether the welcome message is already set:

`esxcli system welcomemsg get`