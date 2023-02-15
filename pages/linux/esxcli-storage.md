# storage

> The storage namespace allows you to check and edit storage settings.
> See also: `sample1`, `sample2`.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- Check the information about mounted VMFS volumes:

`esxcli storage vmfs extent list`

- View mappings of VMFS file systems to disk devices:

`esxcli storage filesystem list`

- List all the iSCSI paths on the system:

`esxcli storage core path list`

- Display the list of mounted NFS shares:

`esxcli storage nfs list`
>
>How do you check SMART with esxcli? S.M.A.R.T. is useful for disk diagnostics and for preventing disk failure. You can read the S.M.A.R.T. data and, if you discover that something is wrong with your disk, you can make a timely decision to replace the disk.

- First, list all storage devices and locate the unique device name (see the screenshot below):

`esxcli storage core device list`

- Then, use the command to get the S.M.A.R.T. data of that disk device:

`esxcli storage core device smart get -d naa.50026b7267020435`
>
>Where naa.50026b7267020435 is the name of the device used in this example.