# hardware

> By using the hardware namespace, you can view the full information about installed devices.
> See also: `sample1`, `sample2`.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- To check the amount of memory installed on the ESXi server:

`esxcli hardware memory get`

- To view the detailed information about installed processors:

`esxcli hardware cpu list`

- To view installed PCI devices, run the following ESXCLI command:

`esxcli hardware pci list | more`

- To display PCI device passthrough configuration:

`esxcli hardware pci pcipassthru list`

- To configure PCI device for passthrough:

`esxcli hardware pci pcipassthru set --apply-now | -a`

- If the flag above is present, the change takes effect immediately; otherwise the change takes effect after a host reboot. This flag causes the device to be unbound from its native driver and bound to the VMkernel's PCI passthrough driver(or vice-versa depending on the setting of the --enable parameter).

- The bus ID of the PCI device (e.g., 0000:0a:00.1). (required) below:

`esxcli hardware pci pcipassthru set --device-id | -d`

- To enable or disable passthrough of the device. (required)

`esxcli hardware pci pcipassthru set --enable | -e`
