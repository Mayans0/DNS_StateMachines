## Table of Finite State Machines

| Name               | Description                                                 | Inputs                  | Outputs                 |
|--------------------|-------------------------------------------------------------|-------------------------|-------------------------|
| SEND_DNS_REQUEST   | Sends a DNS request packet to the server, triggering the event SUCCESS  | Control channel, Event | Control channel, Event |
| DNS_PACKET_LISTEN  | Listens for packets on a set filter, triggering the event SUCCESS  | Control channel, Event, Packet Queue | Control channel, Event |
| DNS_MK_REPLY       | Extracts received packet info, makes reply packet, triggers the event SUCCESS  | Control channel, Received packet, Event | Control channel, Event |
| SEND_PKT           | Sends a packet, triggering the event SUCCESS                    | Control channel, Packet | Control channel, Event |
| ADD_GLUE_RECORDS   | Adds glue records to reply packet                           | Control channel, Packet, Modified Packet | Control channel, Event |
| SEND_SYNC          | Sends a packet through control channel                     | Control channel, Packet | Control channel, Event |
| WAIT_SYNC          | Waits for sync signal, receives packet through control channel | Control channel, Event, Synced Message | Control channel, Event |
| COMPARE_REPLIES0x20| Compares domain name casings of received and synced replies  | Control channel, Received reply (data link), Synced reply (data channel) | Control channel, Event |
| GET_DNS_SPORT      |                                                             |                         |                         |
| GET_DNS_REOLVER_IP |                                                             |                         |                         |
