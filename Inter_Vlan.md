# Intenetworking

	Connecting 
	Switch 2		Router
	Fa0/7		Gig0/0
	fa0/8		Gig0/1

 	Ip router interface 
Vlan 10	Gig0/0	192.168.10.1
Vlan 20	Gig0/1	192.168.20.1

Gateway : 192.168.10.1
        : 192.168.20.1

	Fix router: 

	Enable 
	conf t
	Interface gig0/0
	Ip address 192.168.10.1. 255.255.255.0
	No shutdown 
	Exit
	Interface gig0/1
	Ip address 192.168.20.1 255.255.255.0
	No shutdown 
	Exit 
	End 
	Write memory
	Show ip interface brief

	Fix switch 2

	Enable
	Conf t
	Interface fa0/7
	Switchport mode access 
	Switchport access vlan 10
	No shutdown 
	Exit
	Interface fa0/8
	Switchport mode access
	Switchport access vlan 20
	No shutdown
	Exit 
	End 
	Write memory
	Show ip interface brief

