# netflow_alliance
Comparison of RFC3954 adherence of leading vendors' NetFlow implementations

# Introduction

In the intricate web of modern digital communication, network administrators face the challenge of managing and optimizing their network infrastructures effectively. To achieve this, they rely on a plethora of tools and technologies, one of which is NetFlow. NetFlow is a powerful network protocol that provides granular insights into network traffic, aiding in the monitoring, analysis, and security of networks. This article delves into what NetFlow is, its significance in network traffic analysis, and why adherence to standards such as RFC 3954 is crucial for a harmonious network ecosystem. 

## Understanding NetFlow
NetFlow is a network protocol developed by Cisco that facilitates the collection and analysis of network traffic data. This protocol enables network devices, such as routers and switches, to gather information about IP traffic as it flows through the network. This information includes details about the source and destination of the traffic, the volume of data transferred, the time of transmission, and the type of services or applications being used.

## Importance in Network Traffic Analysis

NetFlow plays a pivotal role in enhancing network traffic analysis for various reasons:

Traffic Monitoring: NetFlow data provides a real-time snapshot of network activities. Network administrators can identify which devices are generating the most traffic, what applications are being used, and whether any anomalies are present.

Bandwidth Optimization: By understanding which applications and users consume the most bandwidth, administrators can optimize network resources, ensuring that critical services receive the required bandwidth without degradation.

Security Insights: NetFlow assists in the identification of potentially malicious activities. By analyzing traffic patterns, administrators can detect unusual behavior, such as excessive data transfers or communication with known malicious domains.

Troubleshooting: When network issues arise, NetFlow data helps pinpoint the root causes. It aids in diagnosing problems by revealing which devices are involved and which paths the data takes through the network.

## RFC 3954: A Standard for NetFlow Management

The Request for Comments (RFC) 3954 outlines the standardization of NetFlow export format for IP Flow Information Export (IPFIX). This standardization ensures interoperability among various vendors' network devices and facilitates a consistent and unified approach to NetFlow data collection.

Vendor Compliance and Interoperability

The adherence to RFC 3954 by different vendors is crucial for several reasons:

- Data Consistency: A uniform NetFlow export format ensures that data collected from different vendor devices can be easily combined and analyzed, leading to accurate and comprehensive insights.

- Integration: Organizations often use a mix of network devices from various vendors. When all devices export NetFlow data in compliance with the same standard, integrating and managing the data becomes seamless.

- Efficient Analysis: Non-compliance could result in fragmented and incompatible data formats, making analysis more complex and time-consuming. Compliance fosters a more efficient analysis process.

- Future-Proofing: As networks evolve, new technologies and devices emerge. Adhering to standardized protocols ensures that NetFlow remains relevant and effective in the face of technological advancements.

NetFlow stands as a pillar of network traffic analysis, providing valuable insights that empower network administrators to optimize their networks for performance and security. The importance of adhering to standards like RFC 3954 cannot be understated; it ensures a harmonious network environment, where data from diverse sources can be seamlessly integrated and analyzed. As technology continues to evolve, the role of NetFlow and its standardized implementations will remain pivotal in the ever-changing landscape of network management and security.

## How to contribute?
Contributing to the project is very easy!
- Enable NetFlows on your device by setting a recipient ($recipient_ip and $recipient_port) to which the flows will be sent.
- On the recipient catch NetFlow traffic using tcpdump (tcpdump -i $interface host $recipient_ip and $recipient_port -w netflow.pcap).
- Use Wireshark to check which fields are present in the streams (in Wireshark, from the "Analyze" menu select "Decode As...", add a field and as "Current" choose "CFLOW".
- Make a pull request on the project indicating, for your device vendor, which fields you have detected (🟩 - Implemented) and which you have not detected (🟥 - Non Implemented).


RFC 3954 Compliance Comparison Table
-----------------------------------

>**Disclaimer**\
This table shows the compliance of major vendors' NetFlow implementations with what is defined in RFC 3954 (https://datatracker.ietf.org/doc/html/rfc3954), especially what is indicated in chapter 8 "Field Type Definitions".

<br>

| CSV Values 	| JSON Values               	| Description
|-------	|-----------------------	|-----------------------
| 🟩     	| Yes           	        | Implemented
| 🟥     	| No       	                | Not Implemented
| 🟧     	| Partially	                | Partially Implemented
| ❓     	| Pending                	| Pending Response
<br>

**Last Updated:** Fri August 17 2023
| **Filed Type** | **Description**            | **Cisco (ASA)** | **Fortigate** | **pfSense** | **Radware (Alteon)** | **Palo Alto** | **Check Point** | **Watchguard** | **Juniper** | **SonicWall** | **Sophos** | **Barracuda** | **Force Point** |
|:------------------------------:|:---------------------------:|:----------------:|:---------------:|:--------------:|:----------------:|:-----------:|:---------------:|:-------:|:----------------:|:----------:|:-----------:|:---------------:|:--------------:|
| **IN_BYTES**           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IN_PKTS**                           | Description         | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **FLOWS**                           | Description              | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **PROTOCOL**                           | Description        | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **TOS**                           | Description      | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **TCP_FLAGS**                           | Description  | ❓               | ❓              | ❓              | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **L4_SRC_PORT**          | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV4_SRC_ADDR**                           | Description                 | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **SRC_MASK**                           | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **INPUT_SNMP**                           | Description           | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **L4_DST_PORT**                           | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV4_DST_ADDR**      | Description      | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **DST_MASK**                           | Description  | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **OUTPUT_SNMP**                           | Description      | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV4_NEXT_HOP**                           | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **SRC_AS**                           | Description              | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **DST_AS**           | Description              | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **BGP_IPV4_NEXT_HOP**                           | Description              | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MUL_DST_PKTS**                           | Description                         | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓              | ❓         | ❓          | ❓              | ❓             |
| **MUL_DST_BYTES**                           | Description                   | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **LAST_SWITCHED**                           | Description             | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **FIRST_SWITCHED**            | Description                         | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **OUT_BYTES**                           | Description                         | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **OUT_PKTS**                           | Description                     | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_SRC_ADDR**          | Description          | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_DST_ADDR**                           | Description      | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_SRC_MASK**                           | Description          | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_DST_MASK**     | Description     | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_FLOW_LABEL**                           | Description | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **ICMP_TYPE**                           | Description     | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MUL_IGMP_TYPE**           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **SAMPLING_INTERVAL**                           | Description        | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **SAMPLING_ALGORITHM**                           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓               | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **FLOW_ACTIVE_TIMEOUT**     | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **FLOW_INACTIVE_TIMEOUT**                           | Description         | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **ENGINE_TYPE**                           | Description             | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **ENGINE_ID**          | Description          | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **TOTAL_BYTES_EXP**                           | Description          | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **TOTAL_PKTS_EXP**                           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓              | ❓         | ❓          | ❓              | ❓             |
| **TOTAL_FLOWS_EXP**      | Description   | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_TOP_LABEL_TYPE**        | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓              | ❓         | ❓          | ❓              | ❓             |
| **MPLS_TOP_LABEL_IP_ADDR**                           | Description             | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓              | ❓         | ❓          | ❓              | ❓             |
| **FLOW_SAMPLER_ID**                 | Description                 | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓           | ❓              | ❓             |
| **FLOW_SAMPLER_MODE**                           | Description                  | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓           | ❓              | ❓             |
| **FLOW_SAMPLER_RANDOM_INTERVAL**                           | Description               | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **DST_TOS**                           | Description             | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **SRC_MAC**                           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓           | ❓              | ❓             |
| **DST_MAC**                           | Description                | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓           | ❓              | ❓             |
| **SRC_VLAN**               | Description    | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **DST_VLAN**                           | Description            | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IP_PROTOCOL_VERSION**                           | Description              | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **DIRECTION**          | Description           | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_NEXT_HOP**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **BGP_IPV6_NEXT_HOP**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **IPV6_OPTION_HEADERS**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_1**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_2**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_3**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_4**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_5**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_6**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_7**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_8**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_9**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
| **MPLS_LABEL_10**        | Description       | ❓               | ❓              | ❓             | ❓               | ❓          | ❓              | ❓      | ❓               | ❓         | ❓          | ❓              | ❓             |
