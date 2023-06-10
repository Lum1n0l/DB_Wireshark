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

    Flow Control: 
        - Flow Control will manage data transmission between devices. 
