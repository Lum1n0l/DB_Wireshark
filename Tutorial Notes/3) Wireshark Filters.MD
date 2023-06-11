Filters

When viewing traffic, I noticed that the MAC Address of the destination device was different to the source address of the same traffic on the opposite end of the wire (Where you would think they would be the same but reversed)

This is because in David's example, the two PC's being captured are in different subnets. Therefore they send there traffic to the router to do the routing. Therefore the destination MAC address is that of the routers not the PC Destination. 

The router rewrites/recreates the frame and request with the destination PC MAC Address when routed onto a different interface. 

I can refer to the Wireshark documentation for details on how to filter traffic in Wireshark.

        Link: https://www.wireshark.org/docs/wsug_html_chunked/index.html

I can either apply a capture filter, to only capture the desired traffic. Or I can apply a display filter to a complete capture of all traffic to only view what I'm looking for within a pcap. 