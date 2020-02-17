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

Both datasets use the same parameters but the only difference between them is the type of simulation network. In this case, the dataset 1 uses our company WLAN and the simulation in the dataset 2 uses a UMTS network.

An overview of the recorded datasets describing the number of clients, used network, the payload, and the resulting data rates:
![Screenshot](https://cloud.githubusercontent.com/assets/26060264/25328159/2011537e-28d7-11e7-9005-45d988ac143d.png)

Client ID | Dataset Client ID | Device Type | OS | Version | Architecture | Cores |
--- | --- | --- | --- | --- | --- | --- |
1 |	dev\_1 |	Huawei MediaPad 7 Zoll |	Android |	4.0.3 SDK:15 |	armv7l |	2 |
2 |	dev\_2 |	Nexus S |	Android |	4.1.2 SDK:16 |	armv7l |	1 |
3 |	dev\_3 |	PC Client |	Windows |	7 |	amd64 |	4 |
4 |	dev\_4 |	PC Client |	Windows |	7 |	x86 |	2 |
5 |	dev\_5 |	Motorola |	Android |	4.1.2 SDK:16 |	i686 |	2 |
6 |	dev\_6 |	Nexus 7 Tablet |	Android |	4.4.4 SDK:19 |	armv7l |	4 |
7 |	dev\_7 |	Galaxy Nexus |	Android |	4.3 SDK:18 |	armv7l |	2 |
8 |	dev\_8 |	Moto X |	Android |	4.4.2 SDK:19 |	armv7l |	2 |
9 |	dev\_9 |	Samsung Galaxy Tab 2 |	Android |	4.2.2 SDK:17 |	armv7l |	2 |
10 |	dev\_10 |	Samsung Galaxy Tab |	Android |	4.0.4 SDK:15 |	armv7l |	2 |
11 |	dev\_11 |	Galaxy Nexus |	Android |	4.4.4 SDK:19 |	armv7l |	2 |
12 |	dev\_12 |	LG-D802 |	Android |	4.4.2 SDK:19 |	armv7l |	4 |
13 |	dev\_13 |	Nexus 5 |	Android |	4.4.4 SDK:19 |	armv7l |	4 |
14 |	dev\_14 |	Samsung, GT-I9300 |	Android |	4.3 SDK:18 |	armv7l |	4 |
15 |	dev\_15 |	Galaxy Nexus |	Android |	4.4.4 SDK:19 |	armv7l |	2 |
16 |	dev\_16 |	Samsung, GT-I8190 |	Android |	4.1.2 SDK:16 |	armv7l |	2 |
17 |	dev\_17 |	PC Client |	Windows |	7 |	amd64 |	8 |


The analysis of the recorded datasets describing the number of out-of-order events and a summary of the processing times:
![Screenshot](https://cloud.githubusercontent.com/assets/26060264/25328163/24303e48-28d7-11e7-8232-b278b348d6d9.png)

Further details of the dataset can be found in:

*Wolfgang Weiss, Víctor Juan Expósito Jiménez and Herwig Zeiner. A Dataset and a Comparison of Out-of-Order Event Compensation Algorithms. In Proceedings of the 2nd International Conference on Internet of Things, Big Data and Security (IoTBDS 2017), pages 36-46, 2017, ISBN: 978-989-758-245-5*

To get a better understanding of the paper, some dataset labels were changed. In this table, the equivalence of those labels to the datasets are given:

- S-Message-ID --> Sequence ID (sid)
- S-Client-Detection-Time --> Detection Time (dt)
- C-Send-Time --> Client send time (cst)
- C-Server-Message-received-Time --> Client receive time (crt)
- S-Message-received-time-ms --> Server received time (srect)
- C-Server-Message-Processed-Time --> Server response time (srest)
- C-Server-Message-Processed-Time --> Server processing time
- S-Session-Name --> Session Name
- S-Client-Network-Type --> Network type
- S-Last-Clock-Synch-Time --> Time of the last time synchronization
- C-NTP-offset --> Synchronization time offset (ms)


Example how to read the data files with R:
```
sampleData <- read.csv2(file="sample.csv", header=TRUE, sep=";", dec=".")
rowClasses <- sapply(sampleData, class)
data <- read.csv2(file="dataset-d/d-1.csv", header=TRUE, sep=";", dec=".", colClasses=rowClasses)
```

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)](http://creativecommons.org/licenses/by-sa/4.0/).

![Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)](https://i.creativecommons.org/l/by-sa/4.0/88x31.png "Creative Commons Attribution-ShareAlike 4.0 International License (CC-BY-SA)")
