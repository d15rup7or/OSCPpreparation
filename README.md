# OSCPpreparation Cheatsheet
The following cheatsheet was prepared while pursuing OSCP


## Port Redirection
When in NAT the VMs have got a virtual IP in a private network (RFC1918 IP range) - not routable and accessible from the outside

To make a NATed machine reachable we've got to implement a PORT REDIRECT on the virtual gateway <br>

```
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/HostPort" 8080
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/GuestPort" 8000
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/Protocol" TCP
```
This config is for Intel network cards. With PCnet switch to `pcnet` instead of `e1000`

After this the webserver on the network
