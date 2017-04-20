# OoO-Dataset
*A dataset for evaluating out-of-order event compensation algorithms.*

These are synthetically generated datasets using standard commercial devices, networks, and protocols commonly used in Internet of Things applications aiming to resemble real world use cases. Several sessions were carried out to cover the influence of different parameters of payload and network types.

The datasets were designed to resemble the behavior and architecture of an Internet of Things use case, where many nodes are connected over a network. Each node continuously sends text-based messages to a common destination in a predefined interval over HTTP. The event producers are various kinds of Android smartphones, running a customized application which is optimized for efficient event generation. Two Windows PCs were also used as event producers for the WLAN datasets running the same code base. The sessions were recorded using either the internal wireless network after the IEEE 802.11 standard (WLAN), or the public cell phone network (UMTS) of different providers.

**Dataset Columns**

- S-Message-received-time (original receive timestamp in human readable format)
- S-Message-received-time-ms (original receive timestamp)
- S-Http-Content-Length (content length of the HTTP message)
- S-Devide-ID (device identifier, stored in the server log)
- S-Message-ID (a sequence ID, unique for each device)
- S-Session-Name (name of the current session, defined by the client)
- S-Client-Detection-Time (time when the event was detected in the client)
- S-Network-Type (selected network by the client, e.g. wifi, umts)
- S-Client-IP (cient's OP address)
- S-Last-Clock-Synch-Time (time when the client was synchronized the last time)
- C-Device-ID (device identifier, stored in the client log)
- C-Message-ID (a sequence ID, unique for each device)
- C-Send-Time (time when the event was sent to the server)
- C-Arrival-Time (time when the answer from the server was received by the client)
- C-NTP-offset (time synchronisation offset between server's time and client's time)
- C-Server-Message-received-Time (server response: time when the event was received in the server)
- C-Server-Message-Processed-Time (server response: time when the event left the server)
- C-Server-Pocessing-duration-ns (server response: elapsed time for processing this event in ns)
- A-Duration-send (duration for sending this event = C-Server-Message-received-Time - C-Send-Time)
- A-Duration-receive (duration for receiving the answer from the server = C-Arrival-Time - C-Server-Message-Processed-Time)
- A-Duration-round-trip (round trip duration = C-Arrival-Time  - C-Send-Time)
- A-ooo-Event-Client-Sequence (if this is an out of order event based on the sequence ID for this device)
- A-ooo-Event-Sent-Time (if this is an out of order event based on the receive time)
- A-Time-to-previous-Client-sequence-detection-time (detection time difference to the previous event based on the sequence ID of this client)
- A-Time-to-previous-Client-sequence-send-time (send time difference to the previous event based on the sequence ID of this client)
- A-Time-to-previous-Client-sequence-receive-time (receive time difference to the previous event based on the sequence ID of this client)
- A-Time-to-previous-Server-Client-sequence-receive-time (server-receive time difference to the previous event based on the sequence ID of this client)


This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)](http://creativecommons.org/licenses/by-sa/4.0/).

![Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)](https://i.creativecommons.org/l/by-sa/4.0/88x31.png "Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)")
