# d15rup7or OSCPpreparation Cheatsheet
The following cheatsheet was prepared for my OSCP journey

## Port Redirection
If the VM uses NAT, it doesn't have its own IP address on the external network. Instead, it receives a virtual IP in a separate private network (RFC1918 IP range) from the VBox virtual DHCP server. As a result, the machines are not routable and accessible from the outside.

![](https://raw.githubusercontent.com/d15rup7or/OSCPpreparation/master/img/NAT-network.png)
To make a NATed VM reachable from the outside, we've got to implement a PORT REDIRECT on the virtual gateway mapping a request from on a given port to be redirected to the virtual IP on the given port or another<br>

```
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/HostPort" 8080
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/GuestPort" 8000
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/Protocol" TCP
```
The above is for Intel network cards. With PCnet switch to `pcnet` instead of `e1000`.<br>
Mind to change the `NAME_OF_VM` to the name of your VM

We can check the config with `VBoxManage getextradata "NAME_OF_VM" enumerate`. To remove the config 

```
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/HostPort"
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/GuestPort"
VBoxManage setextradata "NAME_OF_VM" "VBoxInternal/Devices/e1000/0/LUN#0/Config/pythonhttp/Protocol"
```

After this the webserver on the network
