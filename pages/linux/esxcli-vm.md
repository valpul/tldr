# vm

> The vm namespace can be used for operations on running virtual machines processes.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- Check the list of running VMs and display their World IDs:

`esxcli vm process list`

>Checking the World ID of the VM processes running on an ESXi host
>
>You can kill the unresponsive virtual machine with ESXi shell commands. Using ESXCLI, in this case, can be helpful when a VM cannot be shut down via GUI, such as the GUI of VMware vSphere Client, VMware Host Client or VMware Workstation.

- Shut down the VM by using the World ID displayed in the output of the esxcli vm process list command ex 75498.

`esxcli vm process kill -w 75498 -t soft`

- If the soft command type was not helpful, consider performing an immediate shut down of the VM by using the hard method.

`esxcli vm process kill -w 75498 -t hard`
>
>There are three available command options for the kill command:

>soft - a correct signal is sent in the guest operating system to shut down a VM correctly;

>hard - a VM is shut down immediately;

>force - VM is powered off similarly to how a computer is powered off when unplugging the power cable. Only use this type of powering off the VM if the previous two types were unsuccessful.