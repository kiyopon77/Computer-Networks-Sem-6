* **star1ping (2960 Switch)**



Cisco Packet Tracer PC Command Line 1.0

C:\\>ping 192.168.10.1



Pinging 192.168.10.1 with 32 bytes of data:



Reply from 192.168.10.1: bytes=32 time=7ms TTL=128

Reply from 192.168.10.1: bytes=32 time=2ms TTL=128

Reply from 192.168.10.1: bytes=32 time=4ms TTL-128

Reply from 192.168.10.1: bytes=32 time=2ms TTL=128



Ping statistics for 192.168.10.1:

 	Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),

Approximate round trip times in milli-seconds:

 	Minimum 2ms, Maximum 7ms, Average = 3ms



*Observations (Star Topology)*



1. *The ping was very stable with an average latency of about '3ms'.*
2. *In simulation mode, the 2960 Switch only sent paclets to destination port. It did not 'flood' the network.*
3. *This is the most efficient layout for performance.*



=========================================================================================



* **bus1ping (pt Hub)**



Cisco Packet Tracer PC Command Line 1.0

C:\\>ping 192.168.10.1



Pinging 192.168.10.1 with 32 bytes of data:



Reply from 192.168.10.1: bytes=32 time=6ms TTL=128

Reply from 192.168.10.1: bytes=32 time<1ms TTL=128

Reply from 192.168.10.1: bytes=32 time=3ms TTL=128

Reply from 192.168.10.1: bytes=32 time<1ms TTL=128



Ping statistics for 192.168.10.1:

 	Packets: Sent = 4, Received = 4, Lost = 0 (0% loss),

Approximate round trip times in milli-seconds:

 	Minimum Oms, Maximum = 6ms, Average = 2ms



*Observations (Bus Topology)*



1. *The average latency was even lower than star with only about '2ms'. As hub is a physical-layer device.*
2. *However, during simulation, the hub 'broadcasted' the PDU packet to all connected PCs.*
3. *While it is fast for small no. of devices, this creates high traffic collisons as the network grows.*



=======================================================================================



* **ringCORRECTping (2960 Switch)**



Cisco Packet Tracer PC Command Line 1.0

C:\\>ping -t 192.168.10.4



Pinging 192.168.10.4 with 32 bytes of data:



Reply from 192.168.10.4: bytes=32 time=16ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL-128

Reply from 192.168.10.4: bytes=32 time=8ms TTL-128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128

Reply from 192.168.10.4: bytes=32 time=8ms TTL=128



**Note:** *Once you connect the three switches, one of the copper cross-over links b/w switches remains Orange.
      While the others turn Green, why?, this happens due to STP which 'blocks' one path to prevent data from
      looping endlessly.*



* **ringERRORping (2960 Switch)**



Cisco Packet Tracer PC Command Line 1.0

C:\\>ping -t 192.168.10.6



Pinging 192.168.10.6 with 32 bytes of data:



Reply from 192.168.10.6: bytes=32 time=12ms TTL=128

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Request timed out.

Reply from 192.168.10.6: bytes=32 time=8ms TTL=128



*Observations (Ring-like Topology)*



1. *Latency was the highest aroung '8ms' because the packet has to travel through multiple switches to reach 
   the destination.*
2. *As the ringERRORping shows 9 consecutive timeouts after the link was cut b/w Switch 1 \& Switch 3 before the 
   connection was restored.*
3. *This delay occurs due to Spanning Tree Protocol(STP) has to detect the link failure and transition the 
   'blocked' port to 'forward' state.*
4. *The Ring topology is the only one that survived a hardware failure, proving its **high fault tolerance**.*







