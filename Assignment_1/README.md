**Assignment 1: Basic Network Topologies**



Course: ENCS304 Computer Networks 




Objective: Evaluation of Star, Bus, and Ring topologies for connectivity and fault tolerance.



* **Project Structure**



exp1\_topologies.pkt: The main Cisco Packet Tracer file containing all three network designs.





output\_exp1.txt: Documented ICMP ping results and behavioral observations.





report\_exp1.pdf: Final lab report including objectives, screenshots, and conclusions.



* **Requirements**



Software: Cisco Packet Tracer (v8.0 or higher recommended).



Operating System: Windows, macOS, or Linux.



* **How to Open and Verify the Lab**



1\. Opening the Network Designs

  Launch Cisco Packet Tracer.



2\. Go to File > Open and select exp1\_topologies.pkt.



3\. You will see three distinct areas:



  Task 1 (Star): Central 2960 Switch connected to 4 PCs.



  Task 2 (Bus): Central PT-Hub connected to 4 PCs.



  Task 3 (Ring): Three 2960 Switches connected in a loop.



2\. Verifying Connectivity (Realtime Mode)



  Click on any PC in the workspace.



  Navigate to the Desktop tab and open the Command Prompt.



  Type ping 192.168.10.x (replace x with the destination PCs IP).



  A successful reply indicates correct IP configuration and connectivity.



3\. Observing Packet Flow (Simulation Mode)



  Switch to Simulation Mode.
  
  
  
  Click Edit Filters and ensure only ICMP is selected.
  
  
  
  Use the Add Simple PDU to send a message between two devices.
  
  
  
  Press Play/Forward to observe how the Switch (Star) filters traffic while the Hub (Bus) broadcasts it.



4\. Testing Fault Tolerance (Failure Test)



  In the Ring-like Topology, use the Delete Tool to remove one cable between two switches.
  
  
  
  Perform a ping between PCs on different switches.
  
  
  
  Observe how the network reconverges and restores communication through the redundant path.





