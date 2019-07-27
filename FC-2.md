Manages data flow and creates frames of data. A single frame payload is a max of 2112 bytes.


Classes of Service:

1 - Dedicated connection, allowcates full bandwidth between ports with Acknowledgements.

2 - Connectionless, switch-to-switch communication between ports, transfers frames with Acknowledgements. (BB & EE Credits)

3 - Predominate Connectionless, switch-to-switch communication between ports, transfers frames with No Acknowledgements. (BB Credits)

4 - Dedication connection, allocates requested amount of bandwidth between ports, uses virtual circuits with Acknowledgements.

6 - Dedicated connection for multicase service with Acknowledgements.

F - Switch to switch communication with Acknowledgements.

Class 2, 3, and F is supported by Brocade.



Flow Control:

Class 2, ACK - Acknowledgement

Class 3, R_RDY - Receiver_Ready (used 99% of the time)

Class F, VC_RDY - Virtual Circuit Ready


Glossary:

BB - Buffer-to-Buffer Flow Control

EE - End-to-End Flow Control
