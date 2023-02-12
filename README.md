# Video-Conferencing-Platform
WebRTC, Google Meet, Peer - Peer

# Various-Communications

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


# VOIP
VoIP has two Flavors of Protocol
1. Signalling( SCCP, H.323, SIP)
2. Transport (RTP, RTCP)

**VoIP protocols include**:
1. **Session Initiation Protocol(SIP)**- connection management protocol developed by the IETF
2. **H.323**- one of the first VoIP call signaling and control protocols that found widespread implementation.Since the development of newer, less complex protocols such as MGCP and SIP, H.323 deployments are increasingly limited to carrying existing long-haul network traffic.
3. **Media Gateway Control Protocol (MGCP)**- connection management for media gateways
4. **H.248**- control protocol for media gateways across a converged internetwork consisting of the traditional PSTN and modern packet networks
5. **Real-time Transport Protocol (RTP)**- transport protocol for real-time audio and video data
6. **Real-time Transport Control Protocol (RTCP)**- sister protocol for RTP providing stream statistics and status information
7. **Secure Real-time Transport Protocol (SRTP)**- encrypted version of RTP
8. **Session Description Protocol (SDP)**- a syntax for session initiation and announcement for multi-media communications and WebSocket transports.
9. **Inter-Asterisk eXchange (IAX)-** protocol used between Asterisk PBX instances
10. **Extensible Messaging and Presence Protocol (XMPP)**- instant messaging, presence information, and contact list maintenance
11. **Jingle**- for peer-to-peer session control in XMPP
12. **Skype protocol**- proprietary Internet telephony protocol suite based on peer-to-peer architecture

**Big Thinks to think About**
1. Registration and populating the phone interface (Number, Assignments, etc)
2. Making Calls(address signalling, directory services, etc)
3. Negotiating the details for the RTP Stream(port, codec, etc)
4. Terminating the Call

VoIP Support: POE, TFTP, DHCP, DNS, NTP

# WebRTC
Inorder to know about WbeRTC, we need to have an idea about Websockets.
Though Info is transfered between browsers, inorder to intiate connection the browser should approach Server.
**Websockets**
Websockets are the implementation of client server architecture, where there is request is been sent from client to the server.
Generally in this architecture there is a request from client to the server and server responds, there is no two way communication so the client needs to constantly ping the server for any update which increases the latency.So websockets open bidirectional tunnel between client and the server so even the server can respond whenever there is a change in the system.In the Context of video conferencing this method also has some latency because the client is not directly in contact with the client.His data is routed through the server.In order to mitigate this WebRTC came into picture.
In WebRTC the architecture used is Peer 2 Peer where the clients only reach out to server for signaling purpose(To intiate the request between the browsers) , later the client interacts directly with the client so there is no server involvement which inturn decreases the latency.

In Order to understand the WebRTC, there are few set of Topics which needs to be read upon
1. NAT
2. STUN, TURN
3. ICE
4. SDP
5. Signaling the SDP via Websockets




