# Video-Conferencing-Platform
WebRTC, Google Meet, Microsoft Teams, Dyte.io, Cisco Webx

RTMP /RTSP/ HLS/ MPEG - DASH/ SRT/ Websockets/ IRC/ XMPP/ MQTT/ AMQP/ RCS/ STOMP

# Difference Between Signaling Protocols and Transport Protocols?
**Signaling Protocols**-
A Signaling Protocol is used to identify the state of connection between telephones or VOIP terminals. Signaling protocols include: ALOHA, EDSS1, Dual-tone multi-frequency signaling, H.248, H.323, H.225.0, Jingle, Media Gateway Control Protocol, Megaco, R1, NBAP (Node B Application Part), R2 signalling, **Session Initiation Protocol (SIP)**, Signaling System No.5, Signaling System No.6, Signaling System No.7 (SS7), SCCP (Skinny Call Control Protocol), Q.931 and QSIG.

**Transport Protocols**
TCP/ UDP

**Network Protocols**
HTML / Websockets
XHR , SSE, Ajax Long Pooling, Comet

# Client Server Architecture (vs) Peer2Peer Architecture
Though we have n-number of architectural patterns where an application can be built, i would like to throw some light on the two most common patterns which are common the world of internet.
1. Client Server Architecture
2. Peer 2 Peer

In the **Client Server architecture**, there is request response cycle between Client and the server.There is request which goes from client to the server and theres is response which is being generated from the server which is sent to the client, all these things are done through the HTTP Requests.It is like one way traffic between the client and the server.In order to mitigate this XHR and SSE came into picture so that there is a two way communication between Client and server, but it was more like a hack and latency which was produced. Then Came into the Picture the Websockets, where it provide a Bidirectional terminal between the Client and the Server. The Messages can flow from both the ways(From client to server and vice versa).

In **Peer to Peer Architecture**, things are little bit different here.There is no involvement if server here, the data is transfered between the Browsers only, which inturn decreases the Latency. In Terms of the Video Conferencing Platform, WebRTC is the Newest implementation where the browser deals with the server in order to establish connection only, later the data(VIdeo, audio, Etc) is between the Browsers itself.

# Websockets
Websockets are the implementation of client server architecture, where there is request is been sent from client to the server.
Generally in this architecture there is a request from client to the server and server responds, there is no two way communication so the client needs to constantly ping the server for any update which increases the latency.So websockets open bidirectional tunnel between client and the server so even the server can respond whenever there is a change in the system.In the Context of video conferencing this method also has some latency because the client is not directly in contact with the client.His data is routed through the server.In order to mitigate this WebRTC came into picture.

# WebRTC
Inorder to know about WbeRTC, we need to have an idea about Websockets.
Though Info is transfered between browsers, inorder to intiate connection the browser should approach Server.
In WebRTC the architecture used is Peer 2 Peer where the clients only reach out to server for signaling purpose(To intiate the request between the browsers) , later the client interacts directly with the client so there is no server involvement which inturn decreases the latency.
1. https://webrtc-security.github.io/

In Order to understand the WebRTC, there are few set of Topics which needs to be read upon
1. NAT - It is Technology where the Private or Local Ip Addresses of the Internal hosts is swapped with the public IP of the Router.It Improves the Security because internal Hosts IP Address are hidden.
  a. One to One NAT
  b. Address Restricted NAT
  c. Port Restricted NAT
  d. Symmetric NAT
2. Session Traversal Utilities for NAT (STUN) - The Functionality of the STUN server is to tell the Public IP Address/ Port Through NAT.Works for Full Cone, Port restricted NAT, Address Restricted NAT.Doesnt work for Symmentric NAT. Stun Server Port 3478, 5349 for TLS. Cheap to Maintain.
3. Traversal using relays around NAT (TURN) - In case of Symmentric NAT we use TURN. It's just a server that relays packets. Turn default server Port 3478, 5349 for TLS. Expensive to maintain and run.
3. Interactive Connectivity Establishment(ICE) -ICE collects all available candidates(Local IP Address, refelexive Addresses - STUN Ones and relayed Addresses - TURN Addresses). These all address are calles ICE Candidates. All these collected addresses are then sent to the remote peer via SDP. 
4. SDP
5. Signaling the SDP via Websockets

# NAT SlipStreaming
1. https://medium.com/dsc-sastra-deemed-to-be-university/nat-slipstreaming-1a94351dd518

# mDNS
WebRTC currently lets web applications discover private IP addresses to enable direct connectivity between hosts on a local network. While private IP addresses do not uniquely identify browser users, they may still be used for tracking purposes. To prevent this misuse, private IP addresses returned by RTCPeerConnection will now be masked with mDNS hostnames in certain situations. While this change should be transparent to most WebRTC applications, some developers may need to update their client and backend services. 
1. https://datatracker.ietf.org/doc/html/draft-ietf-rtcweb-mdns-ice-candidates-03
2. https://groups.google.com/g/discuss-webrtc/c/6stQXi72BEU
3. https://getstream.io/blog/webrtc-ip-leaks/
4. https://webrtchacks.com/dear-ny-times/

# SFU / MCU / Peer2Peer
 Selective Forwarding Unit - A Selective Forwarding Unit (SFU) is a media server that receives media from each party in a conference call, decides which streams should be forwarded to other parties, and then forwards them.
Multipoint Control Unit - A WebRTC MCU is a communication server that helps enable real-time communication (RTC) between devices and applications. It stands for “multipoint control unit” and allows for multi-party communication by integrating various audio and video signals into a single stream.
Peer2Peer - P2P networks are different from traditional client-server networks, in which each client is connected to a central server. In a P2P network, there is no central server; instead, each peer is equal and can connect to any other peer on the network.

1. https://getstream.io/blog/what-is-a-selective-forwarding-unit-in-webrtc/
