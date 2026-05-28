

|**==========================================================Router==========================================================**|
|-|
|Router>en<br />Router#config t<br /><br />Router(config)#int se1/0<br />Router(config-if)#ip add 20.0.0.1 255.0.0.0<br />Router(config-if)#no shut<br />Router(config-if)#ex<br /><br />Router(config)#int fa0/0.10<br />Router(config-subif)#encapsulation dot1Q 10<br />Router(config-subif)#ip add 192.168.40.1 255.255.255.0<br />Router(config-subif)#no shut<br />Router(config-subif)#ex<br /><br />Router(config)#int fa0/0<br />Router(config-if)#no shut<br />Router(config-if)#ex<br /><br />Router(config)#router ospf 102<br />Router(config-router)#network 192.168.40.0 0.0.0.255 area 20<br />Router(config-router)#network 20.0.0.0 0.255.255.255 area 20<br />Router(config-router)#ex<br /><br />Router(config)#ip dhcp pool Support <br />Router(dhcp-config)#network 192.168.40.0 255.255.255.0<br />Router(dhcp-config)#default-router 192.168.40.1<br />Router(dhcp-config)#dns-server 8.8.8.8<br />Router(dhcp-config)#ex<br /><br />|
|**==========================================================Switch==========================================================**|
|Switch>en<br />Switch#config t <br /><br />Switch(config)#vlan 10<br />Switch(config-vlan)#name Support<br />Switch(config-vlan)#ex<br /><br />Switch(config)#int range fa0/1-2<br />Switch(config-if-range)#switchport mode access <br />Switch(config-if-range)#switchport access vlan 10<br />Switch(config-if-range)#ex<br /><br />Switch(config)#int fa0/3<br />Switch(config-if)#switchport mode trunk<br />Switch(config-if)#switchport trunk allowed vlan 10<br />Switch(config-if)#ex<br />Switch(config)#<br /><br />|



