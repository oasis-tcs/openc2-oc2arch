## OpenC2 Namespace Registry

**Last Update:** 26 January 2022

The OpenC2 core language is extended using profiles.
This registry tracks the status of currently defined specifications,
plus functions for profiles under consideration.

* Each specification is assigned a unique identifier (Namespace) in the form of an IRI.
* A Namespace can be abbreviated using a Namespace Prefix when referencing types defined within it.
* Property sets with namespaced types are identified by ID or Name (depending on serialization) in OpenC2 messages.

| Prop ID | Property Name | OpenC2 Specification                                                                              | NS Prefix | Namespace                                      | Status                                           |
|---------|---------------|---------------------------------------------------------------------------------------------------|-----------|------------------------------------------------|--------------------------------------------------|
|         |               | [OpenC2 Language Spec v1.0 CS01](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://oasis-open.org/openc2/lang/v1.0         | CS01 2019/07/11                                  |
|         |               | [OpenC2 Language Spec v1.0 CS02](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://oasis-open.org/openc2/lang/v1.0.1       | CS02 2019/11/04                                  |
|         |               | [OpenC2 Language Spec v1.1](https://github.com/oasis-tcs/openc2-oc2ls)                            |           | http://oasis-open.org/openc2/lang/v1.1         | CSD01 2021/08/18                                 |
|         |               | [OpenC2 Language Spec v1.1 Common Types](https://github.com/oasis-tcs/openc2-oc2ls)               | ls:       | http://oasis-open.org/openc2/types/v1.1        | Types section of LS                              |
|         |               | [OpenC2 JSON Abstract Data Notation v1.0](https://github.com/oasis-tcs/openc2-jadn)               |           | http://oasis-open.org/openc2/jadn/v1.0         | CS01 2021/08/17                                  |
|         |               | <div style="text-align: center">**Standard Actuator Profile**</div>                               |           |                                                |                                                  |
| 1024    | slpf          | [Stateless Packet Filtering AP](https://github.com/oasis-tcs/openc2-apsc-stateless-packet-filter) | slpf:     | http://oasis-open.org/openc2/ap-slpf/v1.0      | CSPRD01 2019/05/31 superseded by PF              |
| 1025    | sfpf          | [Stateful Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-sfpf)                       | sfpf:     | http://oasis-open.org/openc2/ap-sfpf/v1.0      | GH WD01, no CSD, superseded by PF                |
| 1026    | sbom          | [Software Bill of Materials AP](https://github.com/oasis-tcs/openc2-ap-sbom)                      | sbom:     | http://oasis-open.org/openc2/ap-sbom/v1.0      | GH WD01 2021/11/17                               |
| 1027    | er            | [Endpoint Response AP](https://github.com/oasis-tcs/openc2-ap-er)                                 | er:       | http://oasis-open.org/openc2/ap-er/v1.0        | GH 2021/06/02, rename from EDR                   |
| 1028    | hop           | [Honeypot Control AP](https://github.com/oasis-tcs/openc2-ap-honeypots)                           | hop:      | http://oasis-open.org/openc2/ap-hop/v1.0       | GH 2021/10/13, use cases                         |
| 1029    | av            | [Anti-virus AP](https://github.com/oasis-tcs/openc2-ap-av)                                        | av:       | http://oasis-open.org/openc2/ap-av/v1.0        | Repo created                                     |
| 1030    | ids           | [Intrusion Detection AP](https://github.com/oasis-tcs/openc2-ap-ids)                              | ids:      | http://oasis-open.org/openc2/ap-ids/v1.0       | Repo created, no template                        |
| 1031    | log           | [Logging Control AP](https://github.com/oasis-tcs/openc2-ap-lc)                                   | log:      | http://oasis-open.org/openc2/ap-log/v1.0       | Repo created, no template                        |
| 1032    | sup           | [Software Update AP](https://github.com/oasis-tcs/openc2-ap-sup)                                  | sup:      | http://oasis-open.org/openc2/ap-sup/v1.0       | Repo requested                                   |
| 1034    | pf            | [Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-pf)                                  | pf:       | http://oasis-open.org/openc2/ap-pf/v1.0        | CSD01 2021/07/21 supersedes SLPF and SFPF        |
|         |               | <div style="text-align: center">**Extension Actuator Profile**</div>                              |           |                                                |                                                  |
| 9001    | blinky        | Blinky Lights with HTTP and MQTT API                                                              | led:      | http://oasis-open.org/openc2/ext/ap-led/v1.0   | No repo, documented in plugfest use cases        |
| 9101    | cdiam         | Cloud Identity and Access Management                                                              | cdiam:    | http://oasis-open.org/openc2/ext/ap-cdiam/v1.0 | No repo, planned output of Fall 2021 ACES Course |
|         |               | <div style="text-align: center">**Proposed Actuator Profile**</div>                               |           |                                                |                                                  |
|         |               | Endpoint Response (previously EDR, listed above)                                                  |           |                                                |                                                  |
|         |               | Threat Analytics (split from EDR)                                                                 |           |                                                |                                                  |
|         |               | Software Defined Network Controller                                                               |           |                                                |                                                  |
|         |               | Email Gateway                                                                                     |           |                                                |                                                  |
|         |               | Intrusion Prevention                                                                              |           |                                                |                                                  |
|         |               | Data Loss Prevention                                                                              |           |                                                |                                                  |
|         |               | Secure Web Gateway                                                                                |           |                                                |                                                  |
|         |               | Security Posture Attribute Collection                                                             |           |                                                |                                                  |
|         |               | Security Posture Evaluation                                                                       |           |                                                |                                                  |
