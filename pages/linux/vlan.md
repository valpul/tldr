# VLAN installation in Ubuntu

> This page is for Ubuntu using IP command

- Install:

`sudo apt install vlan`

- If the module is not loaded after installation you can use the following command to load 8021q module:

`modprobe --first-time 8021q`

- Verify that module is loaded by using the following command:

`modinfo 8021q`

- Get a list of NICs

`ip a`

- Sample dynamic vlan creation:

`sudo ip link add link enp1s0 name enp1s0.100 type vlan id 100`

- Sample dynamic vlan configuration:

`sudo ip addr add 192.168.100.2/24 dev enp1s0.100`