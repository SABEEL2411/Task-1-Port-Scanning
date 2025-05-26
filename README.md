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


INTERVIEW QUESTIONS AND ANSWERS :
1. What is an open port?
A:An open port is a network port that is accepting connections. It means a service is actively listening on that port, allowing communication from other devices. Open ports can be entry points for legitimate traffic or potential attacks.

2. How does Nmap perform a TCP SYN scan?
A:Nmap uses a TCP SYN scan (also called "half-open" scanning) by sending a SYN packet to a target port:
  * If it replies with SYN-ACK, the port is open.
  * If it replies with RST, the port is closed.
  * If there is no response or it's filtered, the port may be blocked.
    Nmap doesn't complete the handshake, making it fast and stealthy.

3. What risks are associated with open ports?
A: Open ports can expose services that:
   * Have vulnerabilities
   * Are misconfigured
   * Shouldn’t be accessible from the network/internet
     Attackers can exploit these to gain unauthorized access, run exploits, or steal data.

4. Explain the difference between TCP and UDP scanning.
A: * TCP scanning is connection-oriented. It relies on a handshake process (SYN, SYN-ACK, ACK).
   * UDP scanning is connectionless. It sends UDP packets and checks for no response or ICMP "port unreachable" replies.
     UDP scans are slower and harder to interpret but useful for services like DNS, SNMP, and DHCP.

5. How can open ports be secured?
A: * Close unused ports.
   * Use firewalls to block unnecessary traffic.
   * Implement access controls.
   * Regularly update software to fix vulnerabilities.
   * Use port-knocking or VPNs for sensitive services.

6. What is a firewall's role regarding ports?
A: A firewall controls inbound and outbound traffic based on rules. It can:
   * Block or allow traffic on specific ports.
   * Prevent unauthorized access to services.
   * Detect and stop port scans or suspicious behavior.

7. What is a port scan and why do attackers perform it?
A: A port scan is a method of probing a system to discover open ports and services.
   Attackers use it to:
   * Map a target’s network.
   * Find vulnerable services.
   * Plan further attacks or exploitation.

8. How does Wireshark complement port scanning?
A: Wireshark captures and analyzes live network traffic. It complements Nmap by:
   * Showing actual packet exchanges during scans.
   * Helping confirm what ports responded and how.
   * Detecting unusual activity or scan patterns.





