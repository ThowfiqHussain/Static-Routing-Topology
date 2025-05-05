Router1>en
Router1#conf t
Router1(config)#int g0/0
Router1(config-if)#ip address 192.168.1.1 255.255.255.0
Router1(config-if)#ip address 192.168.1.1 255.255.255.0

Router1(config)#int g0/1
Router1(config-if)#ip address 10.0.0.1 255.0.0.0
Router1(config-if)#no shut
exit

ip route 192.168.2.0 255.255.255.0 10.0.0.2
do write
exit

Router2>en
Router2#conf t
Enter configuration commands, one per line.  End with CNTL/Z.
Router2(config)#int g0/0
Router2(config-if)#ip address 192.168.2.1 255.255.255.0
Router2(config-if)#no shut

Router2(config-if)#exit
Router2(config)#int g0/1
Router2(config-if)#ip address 10.0.0.2 255.0.0.0
Router2(config-if)#no shut

Router2(config-if)#exit
Router2(config)#int g0/1
Router2(config-if)#ip address 10.0.0.2 255.0.0.0
Router2(config-if)#no shut
EXIT

