## OpenC2 Namespace Registry

The OpenC2 core language is extended using profiles.
This registry tracks the status of currently defined specifications,
plus functions for which profiles are under consideration.

* Each specification is assigned a unique identifier (Namespace) in the form of an IRI.
* A Namespace can be abbreviated using a Namespace Prefix when referencing types defined within it.
* Properties with namespaced types are identified by a Property ID or Property Name in OpenC2 messages.

| Prop ID  | Property Name | OpenC2 Specification                                                                              | NS Prefix | Namespace                                     |
|----------|---------------|---------------------------------------------------------------------------------------------------|-----------|-----------------------------------------------|
|          |               | [OpenC2 Language Spec v1.0 CS01](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://oasis-open.org/openc2/lang/v1.0        |
|          |               | [OpenC2 Language Spec v1.0 CS02](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://oasis-open.org/openc2/lang/v1.0.1      |
|          |               | [OpenC2 Language Spec v1.1](https://github.com/oasis-tcs/openc2-oc2ls)                            |           | http://oasis-open.org/openc2/lang/v1.1        |
|          |               | [OpenC2 Language Spec v1.1 Common Types](https://github.com/oasis-tcs/openc2-oc2ls)               | ls:       | http://oasis-open.org/openc2/types/v1.1       |
|          |               | [OpenC2 JSON Abstract Data Notation v1.0](https://github.com/oasis-tcs/openc2-jadn)               |           | http://oasis-open.org/openc2/jadn/v1.0        |
|          |               | <center>**Standard Actuator Profile**</center>                                                    |           |                                               |
| 1024     | slpf          | [Stateless Packet Filtering AP](https://github.com/oasis-tcs/openc2-apsc-stateless-packet-filter) | slpf:     | http://oasis-open.org/openc2/ap-slpf/v1.0     |
| 1025     | sfpf          | [Stateful Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-sfpf)                       | sfpf:     | http://oasis-open.org/openc2/ap-sfpf/v1.0     |
| 1026     | sbom          | [Software Bill of Materials AP](https://github.com/oasis-tcs/openc2-ap-sbom)                      | sbom:     | http://oasis-open.org/openc2/ap-sbom/v1.0     |
| 1027     | edr           | [Endpoint Detection and Response AP](https://github.com/oasis-tcs/openc2-ap-edr)                  | edr:      | http://oasis-open.org/openc2/ap-edr/v1.0      |
| 1030     | ids           | [Intrusion Detection AP](https://github.com/oasis-tcs/openc2-ap-ids)                              | ids:      | http://oasis-open.org/openc2/ap-ids/v1.0      |
| 1034     | pf            | [Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-pf)                                  | pf:       | http://oasis-open.org/openc2/ap-pf/v1.0       |
|          | hop           | [Honeypot Control AP](https://github.com/oasis-tcs/openc2-ap-honeypots)                           | hop:      | http://oasis-open.org/openc2/ap-honeypot/v1.0 |
|          | av            | [Anti-virus AP](https://github.com/oasis-tcs/openc2-ap-av)                                        | av:       | http://oasis-open.org/openc2/ap-av/v1.0       |
|          | log           | [Logging Control AP](https://github.com/oasis-tcs/openc2-ap-lc)                                   | log:      | http://oasis-open.org/openc2/ap-log/v1.0      |
|          |               | <center>**Custom Actuator Profile**</center>                                                      |           |                                               |
| 9001     | blinky        | Blinky Lights HTTP API                                                                            | led:      | http://oasis-open.org/openc2/custom/haha/v1.0 |
|          |               | <center>**Proposed Actuator Profile**</center>                                                    |           |                                               |
|          |               | Endpoint Response (split from EDR)                                                                |           |                                               |
|          |               | Threat Analytics (split from EDR)                                                                 |           |                                               |
| ~~1028~~ | ~~sdnc~~      | Software Defined Network Controller                                                               |           |                                               |
| ~~1029~~ | ~~emgw~~      | Email Gateway                                                                                     |           |                                               |
| ~~1031~~ | ~~ips~~       | Intrusion Prevention                                                                              |           |                                               |
| ~~1032~~ | ~~dlp~~       | Data Loss Prevention                                                                              |           |                                               |
| ~~1033~~ | ~~swg~~       | Secure Web Gateway                                                                                |           |                                               |
|          |               | Security Posture Attribute Collection                                                             |           |                                               |
|          |               | Security Posture Evaluation                                                                       |           |                                               |
|          |               | Cloud Identity and Access Management                                                              |           |                                               |
