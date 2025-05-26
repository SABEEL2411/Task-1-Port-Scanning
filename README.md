Task 1 : Port Scanning 
In this task I have scanned port on my own IP address by the following steps bellow :
Step-1: In terminal put the command - ifconfig
Step-2: After that you will get output like this 
{
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.0.109  netmask 255.255.255.0  broadcast 192.168.0.255
        inet6 2406:b400:b5:7f10:a00:27ff:fe32:4fe1  prefixlen 64  scopeid 0x0<global>
        inet6 2406:b400:b5:7f10:f17d:a815:a2ca:506a  prefixlen 64  scopeid 0x0<global>
        inet6 fe80::a00:27ff:fe32:4fe1  prefixlen 64  scopeid 0x20<link>
        ether 08:00:27:32:4f:e1  txqueuelen 1000  (Ethernet)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
}
in the above output ip adress is 192.168.0.109 ( Note : this is my ip your might be different 
Step-3:Scan the IP address with Nmap with the command - { nmap -sS 192.168.0.109/24 } make sure to put /24 at the of the IP address to get a proper output with open ports
you can see your output in terminal
open ports are :
23/tcp   filtered telnet
80/tcp   open     http
1900/tcp open     upnp

Optional Content
Step-4: I have open wireshark and capture the packets then again scan the IP address 
in wireshark I found some packet captured in it .
I took the screenshots of that captured packets and posted in my repository 
