# How the Internet Works

## Blurb

The Internet runs the world; it connects our devices, powers our businesses, and
even talks to our thermostats. But how does it all happen? We will follow an
adventurous young web browser from the moment a hapless user presses "enter" and
witness the trials and tribulations of many packets. Ride alongside the most
fearsome syscalls as we learn how the Internet works!

## Description



## Script Sketch

Type in google.com

DNS request

outbound UDP to [DNS server IP]

Show UDP message

local routing table

default gateway

ARP probe for gateway IP (or cached)

Send based on ARP'd MAC

Show IP frame

Explain Ethernet and 802.11*

Local router (static again)

Packet gets to ISP

Intro to BGP

Packet gets to [DNS server IP]

Mention recursive resolution, ask root server, repeat.

DNS server sends UDP response back.

Receive DNS reply, match ID

Cool, got the IP of google.com

Browser creates HTTP request.

TLS init

TCP Handshake

TLS handshake (no crypto)

IP and Ethernet redux

Routing redux

Show HTTP/1.1 request

Wrap in TLS

Wrap in TCP frame

More routing.

HTTP request gets to Google.com

Get the requested page (::jazzhands::)

Show HTTP reply

HTTP reply, all the way back

Unwrap body

Render HTML
