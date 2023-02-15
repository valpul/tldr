# network

> The network namespace is one of the largest namespaces of esxcli. Let’s explore the commands that can be useful for diagnostics.
> See also: `sample1`, `sample2`.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- Check the status of active network connections:

`esxcli network ip connection list`
>
> Checking active network connections in ESXi by using ESXCLI.

- View the list of installed network adapters:

`esxcli network nic list`
>
> Viewing the list of network adapters installed in an ESXi server.

- Display the information about network interfaces:

`esxcli network ip interface list`

- Display the information about IP addresses of the network interfaces that are present on the server:

`esxcli network ip interface ipv4 get`

- Display the network information for VMs:

`esxcli network vm list`
>
> Checking the network information for VMs

- View the domain search settings:

`esxcli network ip dns search list`

- View the DNS servers set in the network settings:

`esxcli network ip dns server list`

- List virtual switches and port groups:

`esxcli network vswitch standard list`

- Show statistics for the vmnic0 network interface:

`esxcli network nic stats get -n vmnic0`

- Check the firewall status and rule settings:

`esxcli network firewall get`

`esxcli network firewall ruleset list`
>
>Note: The default firewall policy is to drop traffic if the opposite rules are not set.

- You can temporary disable the firewall on an ESXi host for troubleshooting:

`esxcli network firewall set --enabled false`

- The firewall must be enabled with the command:

`esxcli network firewall set --enabled true`

> It is recommended to have the ESXi firewall enabled for security reasons.