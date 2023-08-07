# DNS_StateMachines

## Table of Finite State Machines

| Name               | Description                                                 | Inputs                  | Outputs                 |
|--------------------|-------------------------------------------------------------|-------------------------|-------------------------|
| SEND_DNS_REQUEST   | Sends a DNS request packet to the server, triggering        | Control channel         | Control channel         |
|                    |a SUCCESS event                                              | Event                   | Event                   |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| DNS_PACKET_LISTEN  | Listens for packets on a set filter, triggering             | Control channel         | Control channel         |
|                    |  a SUCCESS event                                            | Event                   | Event                   |
|                    |                                                             | Packet Queue            | Packet Queue            |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| DNS_MK_REPLY       | Extracts received packet info, makes reply packet, triggers | Control channel         | Control channel         |
|                    |  a SUCCESS event                                            | Received packet         | Event                   |
|                    |                                                             | Event                   |                         |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| SEND_PKT           | Sends a packet, triggering SUCCESS event                    | Control channel         | Control channel         |
|                    |                                                             | Packet                  | Event                   |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| ADD_GLUE_RECORDS   | Adds glue records to reply packet                           | Control channel         | Control channel         |
|                    |                                                             | Packet                  | Event                   |
|                    |                                                             | Modified Packet         |                         |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| SEND_SYNC          | Sends a packet through control channel                      | Control channel         | Control channel         |
|                    |                                                             | Packet                  | Event                   |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| WAIT_SYNC          | Waits for sync signal, receives packet through control      | Control channel         | Control channel         |
|                    | channel                                                     |                         | Event                   |
|                    |                                                             |                         | Synced Message          |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| COMPARE_REPLIES0x20| Compares domain name casings of received and synced replies | Control channel         | Control channel         |
|                    |                                                             | Received reply(data link)| Event                  |
|                    |                                                             | Synced reply (data channel)|                      |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| GET_DNS_SPORT      |                                                             |                         |                         |
|------------------- |-------------------------------------------------------------|-------------------------|-------------------------|
| GET_DNS_REOLVER_IP |                                                             |                         |                         |
