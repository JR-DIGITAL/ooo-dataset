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

ID | Clients | Network | Interval (ms)	| Net Payload (Bytes) | Gross Payload (Bytes) | Events | Server KiB/sec | Clients KiB/sec |
--- | --- | --- | --- | --- | --- | --- | --- | --- |
D-1 | 8 | 	UMTS | 500 | 	0 | 		265 | 	9600 | 	4.14 | 	0.52 |
D-2 | 9 | UMTS | 500	 | 512 | 1409 | 10800 | 24.77 | 2.75 |
D-3 | 8 | UMTS | 500 | 1024 | 1365 | 9600 | 21.33 | 2.67 |
D-4 | 7 | UMTS | 500 | 2048 | 2426 | 8400 | 33.17 | 4.74 |
D-5 | 7 | UMTS | 500 | 10240 | 10929 | 8400 | 149.42 | 21.35 |
S-7 | 10 | WLAN | 200 | 512 | 1409 | 30000 | 68.80 | 6.88 |
S-8 | 10 | WLAN | 200 | 1024 | 1365 | 30000 | 66.65 | 6.67 |
S-9 | 10 | WLAN | 200 | 2048 | 2426 | 29915 | 118.13 | 11.85 |
S-10 | 10 | WLAN | 200 | 10240 | 10929 | 29999 | 533.64 | 53.36 |
G-1 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-2 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-3 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-4 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-5 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-6 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-7 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-8 | 10 | Simulated | 200 | 0 | 265 | 30000 | 12.94 | 1.29 |
G-9 | 10 | Simulated | 10000 - 100 | 0 | 	265 | 	30057 | 	0.26 - 25.88 | 	0.026 - 2.59 |
G-10 | 10 | Simulated | 10000 - 100 | 0 | 	265 | 	30058 | 	0.26 - 25.88 | 	0.026 - 2.59 |
G-11 | 10 | Simulated | 100 - 10000 | 0 | 	265 | 	29502 | 	25.88 - 0.26 | 	2.59 - 0.026 |
G-12 | 10 | Simulated | 100 - 10000 | 0 | 	265 | 	29503 | 	25.88 - 0.26 | 	2.59 - 0.026 |



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
ID | Clients | Network | ooo Events | ooo Percentage | fpt Min | fpt Q1 | fpt Median | fpt Mean | fpt Q3 | fpt Max | fpt Std Dev |
D-1 | 	8 | 	UMTS | 	1544 | 16.08\% | 59 | 	139 | 	162 | 	181.1 | 190 | 4738 | 103.9  |
D-2 | 9 | UMTS | 3666 | 33.94\% | 81 | 	137 | 167 | 185.8 | 205 | 3680 | 115.6  |
D-3 | 8 | UMTS | 3277 | 34.14\% | 74 | 	132 | 157 | 182.7 | 187 | 5616 | 183.8  |
D-4 | 7 | UMTS | 2302 | 27.40\% | 77 | 	145 | 165 | 193.4 | 203 | 3300 | 116.5  |
D-5 | 7 | UMTS | 1584 | 18.86\% | 154 | 250 | 271 | 288.9 | 304 | 1911 | 83.7  |
S-7 | 10 | WLAN | 7535 | 25.12\% | 11 | 	24 | 	32 | 	46.5 | 50 | 	1522 | 49.9  |
S-8 | 10 | WLAN | 5908 | 19.69\% | 15 | 	27 | 	37 | 	48.4 | 50 | 	872 | 47.1  |
S-9 | 10 | WLAN | 7880 | 26.34\% | 15 | 	29 | 	39 | 	52.6 | 54 | 	3385 | 94.1  |
S-10 | 10 | WLAN | 8495 | 28.32\% | 46 | 	75 | 	92 | 	103.7 | 114 | 1379 | 51.3  |
G-1 | 10 | Simulated | 23968 | 79.89\% | 101 | 302 | 503 |  500.9  | 699 | 901 |  229.7 |
G-2 | 10 | Simulated | 5449 | 18.16\% | 476 | 488 | 500 |  500.5  | 513 | 527 |  14.4 |
G-3 | 10 | Simulated | 6328 | 21.09\% | 29 | 300 | 526 |  525.7  | 751 | 1018 |  260.4 |
G-4 | 10 | Simulated | 9034 | 30.11\% | 24 | 301 | 526 |  525.4  | 750 | 999 |  260.2 |
G-5 | 10 | Simulated | 20305 | 67.68\% | 22 | 128 | 243 |  300.6  | 427 | 995 |  208.5 |
G-6 | 10 | Simulated | 21099 | 70.33\% | 22 | 129 | 244 |  300.8  | 429 | 991 |  209.0 |
G-7 | 10 | Simulated | 8498 | 28.33\% | 251 | 275 | 691 |  500.6  | 726 | 752 |  225.6 |
G-8 | 10 | Simulated | 6652 | 22.17\% | 251 | 342 | 500 |  500.6  | 659 | 750 |  159.8 |
G-9 | 10 | Simulated | 24347 | 81.00\% | 101 | 302 | 500 | 500.9 | 701 | 902 | 230.9 |
G-10 | 10 | Simulated | 8096 | 26.93\% | 448 | 488 | 501 | 500.7 | 513 | 554 | 14.4 |
G-11 | 10 | Simulated | 23764 | 80.55\% | 81 | 301 | 501 | 501.1 | 702 | 901 | 230.7 |
G-12 | 10 | Simulated | 10406 | 35.27\% | 447 | 488 | 501 | 500.6 | 513 | 554 | 14.5 |




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
