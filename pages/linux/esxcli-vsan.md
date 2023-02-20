# vsan

> Sample-Package files into zip/tar file in MATE desktop environment.
> See also: `sample1`, `sample2`.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

# Retrieve vSAN Information

- Verify which VMkernel adapters are used for vSAN communication:

`esxcli vsan network list`

- List storage disks that were claimed by vSAN:
`esxcli vsan storage list`

- Get vSAN cluster information:
`esxcli vsan cluster get`

# Manage a vSAN Cluster

> You can activate vSAN when you create host clusters or enable vSAN on existing clusters. 
>
>You can run these commands in the ESXi Shell for a host, or the command affects the target host that you specify as part of the ESXCLI connection options.

- Verify that the target host is joined to a vSAN cluster:

`esxcli vsan cluster get`

- Join the target host to a given vSAN cluster:

`esxcli vsan cluster join --cluster-uuid {{uuid}}`
>
> The UUID of the cluster is required.

- Remove the target host from the vSAN cluster:

`esxcli vsan cluster leave`



--
# Add and Remove vSAN Storage

- Add an HDD or data disk for use by vSAN:

`esxcli storage filesystem list` - list disks
`esxcli vsan storage add --disks {{device_name}}`
>
> Note The command expects an empty disk, which is partitioned or formatted. Specify a device name, for example, mpx.vmhba2:C0:T1:L0.

- Add an SSD disk for use by vSAN:

`esxcli vsan storage add --ssd {{device_name}}`
>
> Note The command expects an empty disk, which is partitioned or formatted. Specify a devicename, for example, mpx.vmhba2:C0:T1:L0.

- List the vSAN storage configuration. You can display the complete list, or filter to show only a single device.

`esxcli vsan storage list --device {{device}}`

- Remove disks or disk groups:
>
> Note You can remove disks or disk groups only when vSAN is in manual mode. For the automatic disk claim mode, the remove action is not supported.

- Remove an individual vSAN disk.
`esxcli vsan storage remove --disk {{device_name}}`
>
> Instead of specifying the device name, you can specify the UUID if you include the --uuid option.

- Remove a disk group's SSD and each of its backing HDD drives from vSAN usage:

`esxcli vsan storage remove --ssd {{device_name}}`
>
> Instead of specifying the device name, you can specify the UUID if you include the --uuid option.  Any SSD that you remove from vSAN becomes available for such features as Flash Read Cache.


