Section 3: The OSI Model

OSI Model is used to explain communication within a network. 

Model Layers: 
                Layer 7: Application            All
                Layer 6: Presentation           People
                Layer 5: Session                Sleeping
                Layer 4: Transport              Through
                Layer 3: Network                Networking
                Layer 2: Datalink               Don't
                Layer 1: Physical               Pass

Layer 7 (Application):

    Provides Network Processes to Applications
        - Provides Access for Users
        
    Applications such as FTP, Telnet, HTDP & HTTP  are used at this layer. This layer manages application protocals like HTTP, not applications like Firefox.

    Day to day applications such as Firefox make use of protocals that are Layer 7 applications to communicate with the lower levels of the OSI Model. 

Layer 6 (Presentation):

    Manages the format that data is presented in.
    Data Representation/Syntax - This layer ensures that data is readable by the receiving system. 

    Data must be changed into 'Machine Independant Format'. 

    - Formats daya to be presented to the Application Layer
    - Structures Data
    - Negotiates Data Transfer syntax for Application Layer - This may include using ASCII Characters to be universally understood etc. 
    - Can provide encryption

Layer 5 (Session): 

    Interhost Communication
        - Establishment, Maintenance and termination of sessions between applications.
        - Allows two application processes on different machines to establish a session between them.
        - This layer can perform functions that allow sessions to communicate with the network, performing actions, providing security, name recognition, logging. Etc. 
    Examples:
        - Remote Procedure Calls (RPCs)
        - Network File System (NFS)
        - Apple Zone Information Protocal (ZIP)
        - NetBIOS (Network Basic Input/Output System)
        - PPTP (Point-To-Point Tunnelling Protocol)

Layer 4 (Transport):

    - Ensures End-To-End Communication, Reliability and Flow Control. 
    - Performs Message Segmentation - Accepts message from higher layers of OSI Model, splits message into smaller units (if required) and then passes the smaller units down to the Network Layer (Layer 3) for sending.
    - The Receiver will reassable the size reduced message, which was reduced by the sender at layer 4, at layer 4 of its own OSI model on its end. (Reduced by sender at Layer 4, Reassembled at Layer 4 at the destination).
    - Handles transport issues between hosts
    - Ensures transport reliability

    Main Examples: 
        - TCP (Transmission Control Protocol)
        - UDP (User Datagram Protocol)

    TCP: 
        - TCP provides reliability - It establishes, maintains and terminates virtual circuits between devices. To End-Systems go through the TCP 3-way handshake in order to establish a connection (SYN, SYN ACK, ACK)
        - Packets are sequenced, and if packets are lost, they are re-transmitted. 
    UDP:
        - Does not provide reliability - If packets are dropped, they are lost. Higher level applications with the OSI Model would need to ensure reliability. 
        - Does not include Flow Control. 
        - Normally used for services like VoIP, which does not require retransmission of packets.
        - More lightweight and has less overhead compared with TCP

    Flow Control (With TCP): 
        - Flow Control will manage data transmission between devices - To ensure the transmitting device does not send more data than the receiver can process. (Imagine a fast server sending lots of data to an iPhone and overwhelming it, the iPhone can send a message to the Transport Layer of the sender to slow down etc)
        - Session Multiplexing - Allows for the Multiplexing of several message streams or sessions into one logical link - This layer will keep track of which message belongs to which layer

    Analogy: 
        TCP: Like a telephone call, if I give you info on the phone, you may repeat that back to me (ACK) to confirm to me that the information I gave you was received correctly. 
        UDP: Like a postal service, I write the info and send it to you, but there is no guarentee that the mail (UDP Packet) will actually reach its destination. 


Layer 3 (Network):

    - Regards Data Delivery - Routers route data packets from one device to another. 
    - May also include Layer 3 Switches, which have routing capabilities, such as routing packets between VLANs in a network for example. 
    - Layer 3 devices choose the best path to deliver data based on information provided by routing protocols such as
        - OSPF (Open Shortest Path First)
        - BGP (Border Gateway Protocol)
        - IS-IS (Intermediate System-to-Intermediate System)
    
    IPv4 Example: 
        - Addresses such as 192.168.1.1 with a Network Mask of 255.255.255.0
        - Network Mask informs devices that, in the example above, the first 3 octets are network and these are what routing decisions are made on.

    - Layer 3 devices will determine the best path to route traffic based on a set of criteria, such as:
        - Cost
        - Hop Count (RIP Used this to determine best path)
        - Bandwidth (OSPF Used this to determine best path)
        - Longest Match Of Network Address

    - Routing decision are based on the logical addressing format in IPv4 or IPv6.
    - No reliability at the transport layer - IP is not concerned with reliability and relies on higher layer protocals such as TCP for reliability. If UDP is used at Layer 4, The application layer will have to provide reliability if required. 
        - TFTP - Uses IP at Layer 3 (No Reliability) & UDP at Layer 4 (No Reliability) - So the Application provides reliability in this example as none is given at Layers 3 or 4. 


Layer 2 (Data Link):

    - Provides physical addressing and access to media. 
    - It is concerned with how data is formatted for transmission and how access to the network is controlled.

    Example: 
        - Ethernet

            - Uses MAC Addresses (Media Access Control Address) as a Physical Address System
            - MAC Addresses are 48 bits, and made up of 2 parts:
                - Organization Unit Identifier (OUI)
                - Unique Portion 
    
    - This layer also provides error detection - in certain cases can correct errors that happen at the physical layer
        - For example: In Ethernet, data sent will be formatted according to the rules of Ethernet, but if this data traverses a WAN Connection that may use PPP (Point to Point Protocol)
        Layer 2 will ensure that the data from higher layers is formatted correctly for transmission across individual physical links, where the physical link characteristics may vary. 

Layer 1 (Physical):

    - Defines how data is transmitted - i.e what physical state will represent binary 1 or binary 0, media signal and binary transmission are defined at this layer. 
    - Defines the electrical, mechanical, procedural and functional specifications for activating, maintaining and deactivating the physical link. This allows for interoperability. 

    Example:
        - When using an RJ45 Cable, these adhere to a standard so that we know we can plug that ethernet cable into any device that supports RJ45 and it will work as expected.
        - The physical spec, i.e voltage and cable specification of that RJ45 will differ to say a WAN Connector. But again will be standardized. These specifications and standards are set out at Layer 1 of the OSI Model.