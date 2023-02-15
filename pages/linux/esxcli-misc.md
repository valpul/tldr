# misc

> The vm namespace can be used for operations on running virtual machines processes.
> More information: <https://developer.vmware.com/docs/13492/esxi-7-0-u2-esxcli-command-reference/reference.html>.

- Opening the ESXi DCUI the console remotely via SSH

`dcui`
>Press Ctrl+C to go back to the command prompt.

- Convert a thick provisioned virtual disk to a thin provisioned virtual disk by using vmkfstools:

'vmkfstools -i /vmfs/volumes/vmfs_datastore/vm_name/thick_disk.vmdk -d thin /vmfs/volumes/vmfs_datastore/vm_name/new_thin_disk_name.vmdk'
>
>Among ESXi shell commands, vmkfstools is a powerful command for performing storage operations as well as managing storage devices, VMFS volumes, and virtual disks. Read more about thick and thin provisioning as well as virtual disk shrinking.

- Open the ESXi task manager:

`esxtop`
>
>After opening the task manager with the esxtop command, you can switch between tabs by pressing the appropriate keys:

- C - CPU

- I – interrupt

- M – memory

- N – network

- D – disk adapter

- U – disk device

- V – disk VM

- P – power management

- Find the file in the current directory:

`find . -name filename.txt`
>
>Replace the . character with the name of the directory in which you would like to locate a file, and replace filename.txt with your file name. 

- For example, if you wish to find a diskname.vmdk file in the /vmfs/volumes/ directory, run the command:

`find /vmfs/volumes/ -name diskname.vmdk`

- Open the interactive VMware console:

`vsish`

- Show loaded vmkernel drivers:

`vmkload_mod --list`

- Check the settings of the swap partition:

`esxcli sched swap system get`

- You can list users by using one of the following commands:

`esxcli system account list`

`cat /etc/passwd or less/etc/passwd`
> 
>Using ESXi shell commands to list existing system users
> 
>Creating a new user; there are at least two methods of creating a new ESXi user by using ESXi shell commands.
>
> Using the adduser command

- If you type the adduser command in the ESXi console, you will get the message:

`-sh: adduser: not found`

- You should define the full path to the appropriate busybox binary to run this command:

`/usr/lib/vmware/busybox/bin/busybox adduser`
>
>Now you can see the usage options for this command.

- Finally, run the exact command to add an ESXi system user:

`/usr/lib/vmware/busybox/bin/busybox adduser -s /bin/sh -G root -h / user1`

- Where:

- -s /bin/sh is a shell used after user login;

- -G root – the group name whose member is a new user (the root group);

- -h / is a home directory (the root directory) of a new user;

- user1 is the user name.
>
>Enter a new password and confirm the password when prompted.
>
>Using ESXi shell commands to add a new user in ESXi
>
>Using ESXCLI

- As an alternative, you can add a new user just with the one command by using esxcli:

`esxcli system account add -d="NAKIVO user" -i="nakivo" -p="Password-Test321" -c="Password-Test321"`

- Where:

- -d means the displayed description

- -p is the password set for the new user

- -c is the password confirmation
>
> Which method of creating a new user in the command line is better? The single command used in the second method may appear to be the optimal method for creating a new user, but it is not entirely true on account of security reasons. If you’ve been attentive, you should be able to remember the warning message displayed right after logging in to the ESXi shell:
>
> All commands run on the ESXi shell are logged and may be included in support bundles. Do not provide passwords directly on the command line. Most tools can prompt for secrets or accept them from standard input.

- If security is a concern for you, enter commands without including passwords as plain text into the commands. If a password is needed, it is usually prompted and can be entered in the standard console input. For example, if you would likr to create a new user with ESXCLI, use a command like:

`esxcli system account add -d="user2" -i="user2" -p -c`
>
> A password will be prompted separately and will not be displayed in the console while entering the password.
>
> Using ESXCLI to add a new user in ESXi