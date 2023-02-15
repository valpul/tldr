# software

> Software packages intended for ESXi are usually distributed as VIB files (vSphere installation bundle). A VIB file is similar to a container with zipped packages that can be installed in the system, with a descriptor and a signature file. In turn, VIBs are usually distributed as files packed into an archive file in the standard ZIP format. You may need to include VIBs into an ESXi image in order to use the appropriate hardware or install VIBs in an existing system for applying a security patch.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- You can view the list of VIB packages installed on your ESXi host:

`esxcli software vib list`

- You can install a VIB with ESXCLI (the ESXi host must be in maintenance mode):

`esxcli software vib install -d /vmfs/volumes/datastore1/patches/patch_name.zip`