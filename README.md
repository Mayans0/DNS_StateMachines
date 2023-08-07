## Table of Finite State Machines

| Name               | Description                                                 | Inputs                  | Outputs                 |
|--------------------|-------------------------------------------------------------|-------------------------|-------------------------|
| SEND_DNS_REQUEST   | Sends a DNS request packet to the server, triggering the event SUCCESS  | Control channel, Event | Control channel, Event |
| DNS_PACKET_LISTEN  | Listens for packets on a set filter, triggering the event SUCCESS  | Control channel, Event, Packet Queue | Control channel, Event |
| DNS_MK_REPLY       | Extracts information from a packet and crafts a reply packet, triggers the event SUCCESS  | Control channel, Received packet, Event | Control channel, Event |
| SEND_PKT           | Sends a packet, triggering the event SUCCESS                    | Control channel, Packet | Control channel, Event |
| ADD_GLUE_RECORDS   | Adds glue records to a packet                           | Control channel, Packet, Modified Packet | Control channel, Event |
| SEND_SYNC          | Sends a packet through a control channel                     | Control channel, Packet | Control channel, Event |
| WAIT_SYNC          | Waits for a sync signal and receives a packet through the control channel | Control channel, Event, Synced Message | Control channel, Event |
| COMPARE_REPLIES0x20| Compares domain name casings of two replies recieved from the data link and control channel | Control channel, Received reply (data link), Synced reply (data channel) | Control channel, Event |
| GET_DNS_SPORT      |                                                             |                         |                         |
| GET_DNS_REOLVER_IP |                                                             |                         |                         |
