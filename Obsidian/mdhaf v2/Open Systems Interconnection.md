1. Physical
2. Datalink
3. Network
4. Transport
5. Session
6. Presentation
7. Application

Layers 5-7 together forms ==**Protocol Data Unit (PDU)**==. Sockets are then formed at Session layer (5). At Transport (4), a TCP header is formed. The header is added to PDU. The PDU's are broken into segments via sequencing in order to send and receive data. With a TCP header, the PDU becomes a==segment==. At Network (3), IP header is added attaching data (packet) at end of segment. Data portion of PDU is know as ==payload==.