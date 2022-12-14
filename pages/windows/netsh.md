# netsh

> netsh Samples
> More information: <https://learn.microsoft.com/windows-server/administration/windows-commands/netsh>.

- Run the netsh lan command below to list all the wired network interfaces available on your Windows machine (dependent of the Wired AutoConfig Service dot3svc):

`netsh lan show interfaces`

- Gathering Information on Network Interfaces:

`netsh interface ipv4 show config`

- To roll back to using a dynamic IP address:

`netsh interface ip set address "Ethernet" dhcp`

- Now, run the below netsh interface command to manually set the following IP address 10.0.0.100/16 Gateway 10.0.0.1 settings:

`netsh interface ip set address "Ethernet" static 10.0.0.100 255.255.0.0 10.0.0.1`

- Manually set DNS:

`netsh interface ipv4 set dns name=YourIneterfaceName static 0.0.0.0 index=2`

- Set DNS to DHCP:

`netsh interface ipv4 set dnsservers name”YOUR INTERFACE NAME” source=dhcp`

- To disable the Ethernet interface on your Windows system:

`netsh interface set interface name="Ethernet" admin=disabled`

- The example below opens ICMP on the firewall:

`netsh advfirewall firewall add rule name="All ICMP V4" dir=in action=allow protocol=icmpv4`

- Example opening port 80 in this case:

`netsh advfirewall firewall add rule name= "Open Port 80" dir=in action=allow protocol=TCP localport=80`
