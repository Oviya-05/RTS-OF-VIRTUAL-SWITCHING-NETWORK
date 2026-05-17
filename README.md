# RTS OF VIRTUAL SWITCHING NETWORK

---

## 1. Introduction

In modern communication systems, millions of devices exchange data continuously through networks. To ensure efficient and reliable communication, different switching techniques are used. Switching is the process of transferring data from a source device to a destination device through intermediate network devices. Among the various switching techniques, the **Virtual Switching Network (VSN)** plays an important role in providing fast, reliable, and organized communication.

A Virtual Switching Network creates a temporary logical connection, called a **virtual circuit**, between the sender and receiver before data transmission begins. Unlike circuit switching, where a dedicated physical path is reserved, virtual switching creates a logical path that efficiently uses network resources. This technique is widely used in modern communication systems such as MPLS networks, ATM networks, mobile communication systems, and video conferencing applications.

---

## 2. Switching in Communication Networks

Switching is a method used to forward data from one device to another through a communication network. Since direct communication between every pair of devices is impractical, switching helps in sharing network resources efficiently.

### 2.1 Need for Switching

- Efficient utilization of communication channels
- Reduction of transmission cost
- Reliable data delivery
- Better bandwidth management
- Support for multiple users simultaneously

---

## 3. Types of Switching Techniques

- **Circuit Switching –** Establishes a dedicated physical communication path between sender and receiver before communication starts.
- **Message Switching –** Transfers the complete message from one node to another using the store-and-forward method.
- **Packet Switching –** Divides data into smaller packets and transmits them independently through the network.
- **Virtual Circuit Switching –** Combines the advantages of circuit switching and packet switching. A logical path is established before transmission, but resources are shared dynamically.

---

## 4. Virtual Switching Network (VSN)

### 4.1 Definition

A Virtual Switching Network is a communication system that establishes a temporary logical connection between source and destination devices for data transmission.

> The logical path created is called a **virtual circuit**.

---

## 5. Architecture of Virtual Switching Network

The architecture of a Virtual Switching Network consists of multiple interconnected components that work together to establish and manage virtual communication paths.

```
Source Node → Switching Nodes → Destination Node
```

### 5.1 Source Node

- The source node is the device that initiates communication.
- **Functions –** Sends RTS request, Generates data packets, Starts virtual circuit establishment
- **Example –** A computer initiating a video call.

### 5.2 Switching Nodes

- Switching nodes are intermediate devices that forward packets through the network.
- **Functions –** Check resource availability, Maintain routing tables, Forward packets to the next node, Manage congestion
- **Example –** Routers and switches in a network.

### 5.3 Routing Tables

- Routing tables store path information required for packet forwarding.
- **Functions –** Store virtual circuit identifiers, Determine next-hop destination, Maintain path information
- **Importance –** They ensure packets follow the correct virtual path.

### 5.4 Virtual Circuit Identifier (VCI)

- VCI is a unique number assigned to each virtual connection.
- **Functions –** Identifies virtual circuits, Helps switches forward packets correctly, Maintains communication sessions

### 5.5 Destination Node

- The destination node receives transmitted data packets.
- **Functions –** Receives RTS request, Sends CTS responses, Reassembles received packets
- **Example –** A mobile device receiving a video call.

---

## 6. Working of Virtual Switching Network

The operation of a Virtual Switching Network occurs in three stages.

- **Connection Establishment Stage –** Before transmitting data, the source establishes a virtual connection with the destination.

```
Source → RTS → Network → CTS → Source
```

- **Data Transfer Stage –** After connection establishment, data packets are transmitted through the established virtual circuit.

- **Connection Termination Stage –** After communication is completed, the virtual circuit is released.

```
Data Transfer Complete → Connection Release
```

---

## 7. RTS and CTS Mechanism

### RTS (Request To Send/Switch)

- RTS is a control packet sent by the source to request communication setup.
- **Functions –** Initiates virtual path setup, Requests bandwidth allocation, Prevents congestion

### CTS (Clear To Send)

- CTS is sent by the destination after successful path establishment.
- **Functions –** Confirms resource availability, Allows data transmission, Completes connection setup

---

## 8. Types of Virtual Circuits

- **Permanent Virtual Circuit (PVC) –** A permanent logical connection established manually.
- **Switched Virtual Circuit (SVC) –** A temporary virtual connection created when needed.

---

## 9. Routing in Virtual Switching Networks

Routing determines the best path for data transmission.

### 9.1 Functions of Routing

- Path selection
- Congestion handling
- Traffic management
- Error handling

### 9.2 Routing Table Components

- Virtual circuit number
- Destination address
- Output port number

---

## 10. Real-Time Scenarios of Virtual Switching Network

- **Video Conferencing –** Applications such as Zoom, Google Meet, WhatsApp use virtual paths for smooth communication.
- **ATM Banking Networks –** Banks use virtual switching for secure transaction processing between ATMs and servers.
- **MPLS Networks –** Multiprotocol Label Switching uses virtual circuits for fast packet forwarding.
- **Mobile Communication –** 4G and 5G communication systems use virtual switching for voice and internet services.
- **Cloud Computing –** Cloud servers use virtual networks for communication between virtual machines and applications.

---

## 11. Cisco Packet Tracer Simulation

The ATM Banking Network using Virtual Switching Network was implemented using **Cisco Packet Tracer** in Simulation Mode to analyze logical communication path establishment and packet transmission between ATM machines and the central bank server.

The simulation demonstrated how virtual switching enables reliable and organized communication in banking networks.

### 11.1 Objectives of the Simulation

- To simulate an ATM banking communication network
- To establish virtual communication paths between ATM machines and the bank server
- To analyze packet transmission using Virtual Switching Network principles
- To observe packet flow using Simulation Mode in Cisco Packet Tracer
- To study reliable communication between multiple devices

### 11.2 Network Design Structure

**Topology Used:** Star Topology

**Components Used:**

| Component | Quantity |
|-----------|----------|
| 2960 Switch | 1 |
| Server | 1 |
| PCs (ATM Machines) | 3 |
| Copper Straight-Through Cable | 4 |

### 11.3 Communication Structure

```
ATM0 (PC0) ─┐
ATM1 (PC1) ─┼─── 2960 Switch ─── Bank Server
ATM2 (PC2) ─┘
```

### 11.4 IP Address Configuration

| Device | IP Address | Subnet Mask |
|--------|------------|-------------|
| **ATM0 (PC0)** | 192.168.1.1 | 255.255.255.0 |
| **ATM1 (PC1)** | 192.168.1.2 | 255.255.255.0 |
| **ATM2 (PC2)** | 192.168.1.3 | 255.255.255.0 |
| **Bank Server** | 192.168.1.100 | 255.255.255.0 |
| **Switch** | 192.168.1.254 | 255.255.255.0 |

### 11.5 Switch Configuration

The switch VLAN interface was configured using CLI commands.

**CLI Commands Used:**

```bash
enable
configure terminal
interface vlan 1
ip address 192.168.1.254 255.255.255.0
no shutdown
exit
```

The VLAN interface was enabled successfully for network communication management.

### 11.6 Simulation Procedure

**STEP 1:** Open the Cisco Packet Tracer software.

**STEP 2:** Drag one switch, one server, and three PC terminals from the toolbar and place them in the workspace area.

**STEP 3:** Rename the PCs as ATM0, ATM1, and ATM2 to represent ATM machines.

**STEP 4:** Select Copper Straight-Through cable from the toolbar and connect all ATM machines and the bank server to the switch using different Fast Ethernet ports.

**STEP 5:** Click on each device, select `Desktop → IP Configuration`, and assign static IP addresses and subnet masks.

**STEP 6:** Repeat STEP 5 for all ATM machines and the bank server.

**STEP 7:** Click on the ATM machine, open `Desktop → Command Prompt`, and verify communication using the Ping command.

**STEP 8:** During communication, the ATM machine sends RTS (Request To Send), the switch verifies the communication path, and the bank server responds with CTS (Clear To Send) to establish a temporary logical communication path.

**STEP 9:** Enter Ping commands to test packet transmission between ATM machines and the bank server.

```
ping 192.168.1.100
```

**STEP 10:** Select "Add Simple PDU" from the toolbar and place it on the source ATM machine and destination bank server to verify connectivity.

**STEP 11:** Switch to **Simulation Mode** to observe packet flow and successful communication through the Virtual Switching Network.

### 11.7 Simulation Mode Observation

The simulation was analyzed using Simulation Mode in Cisco Packet Tracer.

**Simulation Steps:**

- Realtime mode switched to Simulation mode
- ICMP packets generated
- Auto Capture/Play executed
- Packet movement observed

### 11.8 Working Principle of the Simulation

1. ATM machine initiates transaction request.
2. RTS packet is transmitted to establish communication.
3. The switch checks communication path availability.
4. Bank server responds with CTS packet.
5. A virtual communication path is created.
6. Transaction packets travel through the established logical path.
7. After transaction completion, the communication path is released.

### 11.9 Example Banking Transactions Simulated

- ATM0 performed balance enquiry
- ATM1 simulated cash withdrawal
- ATM2 performed money transfer request

> All communication was completed successfully through virtual switching.

### 11.10 Simulation Output

*(Refer to screenshots captured from Cisco Packet Tracer Simulation Mode)*

### 11.11 Result

The ATM Banking Network was successfully simulated using Cisco Packet Tracer. The Virtual Switching Network established temporary logical communication paths between ATM machines and the bank server before packet transmission.

The simulation demonstrated **reliable and efficient communication** suitable for real-world banking systems.

---

## 12. Advantages of Virtual Switching Networks

- **Efficient Bandwidth Utilization –** Resources are shared dynamically.
- **Reliable Communication –** Packets follow the same virtual path.
- **Reduced Congestion –** Resources are reserved before transmission.
- **Ordered Packet Delivery –** Packets arrive in sequence.
- **Better Multimedia Support –** Suitable for video and voice communication.

---

## 13. Disadvantages of Virtual Switching Networks

- **Setup Delay –** Time is required to establish virtual circuits.
- **Complex Management –** Routing and resource allocation are complicated.
- **Path Dependency –** Path failures interrupt communication.
- **Additional Overhead –** Control packets increase network load.

---

## 14. Technologies Based on Virtual Switching

- **ATM (Asynchronous Transfer Mode) –** Uses fixed-size cells for high-speed communication.
- **Frame Relay –** Efficient WAN packet-switching technology.
- **MPLS –** Uses labels for fast routing.
- **VLAN –** Creates logical networks inside physical networks.
- **SDN (Software Defined Networking) –** Separates network control and forwarding functions.

---

## 15. Challenges in Virtual Switching Networks

- **Security Issues –** Unauthorized access may affect virtual circuits.
- **Scalability Problems –** Managing large networks becomes difficult.
- **Congestion –** Heavy traffic affects performance.
- **Fault Tolerance –** Path failures interrupt communication.

---

## 16. Future Scope of Virtual Switching Networks

Future communication systems increasingly depend on virtual networking technologies.

- 5G communication
- Cloud networking
- IoT systems
- AI-based routing
- Smart city infrastructure
- Edge computing

---

## 17. Conclusion

Virtual Switching Networks provide efficient and reliable communication by establishing logical paths between devices. They combine the advantages of circuit switching and packet switching, making them suitable for modern applications such as video conferencing, cloud computing, banking systems, and mobile communication.

The RTS and CTS mechanisms ensure proper resource allocation and congestion control. Although virtual switching networks have limitations such as setup delay and management complexity, their advantages in bandwidth utilization, reliability, and scalability make them highly important in modern communication systems.

With the rapid growth of 5G, IoT, and cloud computing technologies, Virtual Switching Networks will continue to play a major role in future networking infrastructures.

---

## Question Bank

### PART A – Fill in the Blanks

1. RTS stands for ____________________________________.
2. Virtual Switching Network establishes a __________________ communication path before data transfer.
3. The software used for simulation was __________________ Packet Tracer.
4. The ATM machines were represented using __________________ devices.
5. The central banking system was represented using a __________________.
6. Before transmission, the sender sends an __________________ request.
7. The receiver responds with __________________ before communication begins.
8. ICMP packets were generated using the __________________ command.
9. Copper Straight-Through cables were used to connect devices to the __________________.
10. Simulation Mode is used to observe __________________ transmission.

---

### PART B – Match the Following

| Column A | Column B |
|----------|----------|
| 1. RTS | a. Central Banking Device |
| 2. CTS | b. Request To Send |
| 3. Server | c. Packet Observation |
| 4. Simulation Mode | d. Clear To Send |
| 5. ICMP | e. Connectivity Testing |

---

### PART C – True or False

1. RTS is used before data transmission in Virtual Switching Networks. **(True)**
2. ATM machines were connected wirelessly in the simulation. **(False)**
3. The server acts as the central banking server. **(True)**
4. CTS is sent before RTS. **(False)**
5. Cisco Packet Tracer was used for the simulation. **(True)**
6. Ping command was used to test communication between devices. **(True)**
7. Copper Straight-Through cables were used for device connections. **(True)**
8. Simulation Mode helps observe packet movement in the network. **(True)**

---

### PART D – Multiple Choice Questions (MCQs)

**1. What does RTS stand for?**
- a. Request To Send ✅
- b. Ready To Switch
- c. Routing Transmission Signal
- d. Real Transfer Service

**2. Which device acted as the central communication device?**
- a. Hub
- b. Switch ✅
- c. Bridge
- d. Repeater

**3. Which protocol was used to test connectivity?**
- a. FTP
- b. HTTP
- c. ICMP ✅
- d. SMTP

**4. What happens before packet transmission in Virtual Switching Network?**
- a. Path establishment ✅
- b. Router shutdown
- c. Cable removal
- d. Packet deletion

**5. Which software was used for simulation?**
- a. MATLAB
- b. Cisco Packet Tracer ✅
- c. Python
- d. Wireshark

**6. Which mode was used to observe packet movement?**
- a. Config Mode
- b. Realtime Mode
- c. Simulation Mode ✅
- d. Physical Mode

**7. Which device represented the ATM machines?**
- a. Router
- b. PC ✅
- c. Hub
- d. Printer

**8. What is the purpose of CTS?**
- a. To disconnect devices
- b. To confirm communication readiness ✅
- c. To delete packets
- d. To assign IP addresses

---

### PART E – Short Answer Questions

1. Define RTS in Virtual Switching Network.
2. What is the purpose of using RTS and CTS?
3. Name the components used in the simulation.
4. Why is Simulation Mode used in Cisco Packet Tracer?
5. Explain the working principle of Virtual Switching Network.
6. What is the role of the switch in the network?
7. Why were ICMP ping packets used in the experiment?
8. Explain the real-time ATM banking scenario used in the experiment.
9. What is the function of CTS in communication?
10. What are the advantages of Virtual Switching Network?

---

### PART F – Long Answer Questions

1. Explain the working of RTS and CTS in Virtual Switching Network with a neat diagram.
2. Describe the real-time ATM banking scenario implemented in Cisco Packet Tracer.
3. Explain the step-by-step simulation procedure of Virtual Switching Network.
4. Discuss the advantages and disadvantages of Virtual Switching Network.
5. Explain how logical communication paths are established before data transmission.
6. Describe the packet transmission process observed in Simulation Mode.
