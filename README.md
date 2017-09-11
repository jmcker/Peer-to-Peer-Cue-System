# Peer-to-Peer Cue System #

Cue system for simple two-way communication and visual signaling using WebRTC peer-to-peer connection.
v2.0

Demo: [http://jackmckernan.tk/open-development/peer-to-peer-cue-system/](http://jackmckernan.tk/open-development/peer-to-peer-cue-system/)

### Setup ###

1. Open receive.html on the receiving device.
2. Open send.html on the sending device.
3. Both should indicate a successful connection in the *Status* box.
4. If send.html is opened before receive.html, connection will be unsuccessful. 
5. Refresh send.html once receive.html is opened to connect.

### Features ###

The reciever has access to large indicators for standby, go, fade, and stop signals. 

The sender has access to buttons that send the standby, go, fade, and stop signals, triggering the recievers indicators.

Both have access to a two-way messenger for additional communication.

### Current Limitations ###

Because this system was only designed for a single active pair of users, the identifiers used for inital connection and handshake are hand-assigned. For a multi-user system, this would need to be adapted to generate random ids that could be communicated prior to inital connection. This could be achieved through a centralized database (i.e. username linked with a randomly generated key at each login), any pre-existing two-way communication protocol, or simply with local generation and instructions to communicate to the second party. For ideas and implementation, take a look at [this](https://www.html5rocks.com/en/tutorials/webrtc/basics/#toc-signaling).

Should either identifier indicate that it is already in use, nothing can be done until the hold should expires on the server within two days or so. In this projects current state and with only a single active pair of users, the only option to rectify this is to manually change the indentifiers on **both** the sending and recieving page.

This error is especially prevalent when one user momentarily loses network connection. [PeerJS](http://peerjs.com/docs/) (handles indentifier pool and initial handshake before dropping to direct peer-to-peer) has documentation suggesting a method to recover from this. At the time that this project was under active development, however, this method was unsuccessful at restoring connection or removing the "in use" status of the identifier on the PeerJS servers. There were several reports that error was on PeerJS's end of things. The [PeerJS Repository](https://github.com/peers/peerjs) no longer appears to be under active development, so chances are this issue has not been resolved.

I made the decision to build this using WebRTC because it was a pretty new and exciting standard at the time. It worked well, but there are a multitude of improvements that can be made to this little experiment. Best of luck to anyone who stumbles upon this!


### Contact ###
Jack McKernan [jmcker@outlook.com](mailto:jmcker@outlook.com)
