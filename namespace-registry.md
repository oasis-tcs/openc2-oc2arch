## OpenC2 Namespace Registry

**Last Update:** xx December 2023

The OpenC2 core language is extended using actuator profiles (APs).
This registry tracks the status of currently defined AP specifications,
plus functions for profiles under consideration.

* Each AP is [assigned a **short name**](https://github.com/oasis-tcs/openc2-tc-ops/blob/main/Documentation-Norms.md#42-assign-work-product-name) when it is identified as a work product; the TC's practice is to use these short names in namespaces and as namespace identifiers (NSIDs)
* Each specification is assigned a unique identifier (Namespace) in the form of an IRI.
* A Namespace can be abbreviated using a Namespace Prefix when referencing types defined within it.
* Namespaced property sets (e.g., Targets, Args, Results) are identified by ID or Name, depending on serialization, in OpenC2 messages.
* The Property ID/Name (NSID) used in type references and the Namespace Prefix defined in a package's "namespaces" info
  are distinct and can have different values, but they are normally the same.

A more detailed explanation of OpenC2's use of namespaces can be found in [Appendix F](https://docs.oasis-open.org/openc2/oc2arch/v1.0/cs01/oc2arch-v1.0-cs01.html#appendix-f-openc2-namespace-registry) of the OpenC2 Architecture Specification.

Namespaces are assigned according to [OASIS Naming Directives for XML namespaces](http://docs.oasis-open.org/specGuidelines/ndr/namingDirectives.html#xml-namespaces):

| Prop ID | Property Name | OpenC2 Specification                                                                              | NS Prefix | Namespace                                              | Status                                    |
|---------|---------------|---------------------------------------------------------------------------------------------------|-----------|--------------------------------------------------------|-------------------------------------------|
|         |               | [OpenC2 Language Spec v1.0 CS01](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://docs.oasis-open.org/openc2/ns/lang/v1.0         | CS01 2019/07/11                           |
|         |               | [OpenC2 Language Spec v1.0 CS02](https://github.com/oasis-tcs/openc2-oc2ls)                       |           | http://docs.oasis-open.org/openc2/ns/lang/v1.0.1       | CS02 2019/11/04                           |
|         |               | [OpenC2 Language Spec v2.0](https://github.com/oasis-tcs/openc2-oc2ls)                            |           | http://docs.oasis-open.org/openc2/ns/lang/v2.0         | CSD01 2021/08/18                          |
|         |               | [OpenC2 Language Spec v2.0 Common Types](https://github.com/oasis-tcs/openc2-oc2ls)               | ls:       | http://docs.oasis-open.org/openc2/ns/types/v2.0        | Types section of LS                       |
|         |               | [OpenC2 JSON Abstract Data Notation v1.0](https://github.com/oasis-tcs/openc2-jadn)               |           | http://docs.oasis-open.org/openc2/ns/jadn/v1.0         | CS01 2021/08/17                           |
|         |               | <div style="text-align: center">**Standard Actuator Profile**</div>                               |           |                                                        |                                           |
| 1024    | slpf          | [Stateless Packet Filtering AP](https://github.com/oasis-tcs/openc2-apsc-stateless-packet-filter) | slpf:     | http://docs.oasis-open.org/openc2/ns/ap/slpf/v1.0      | CSPRD01 2019/05/31 superseded by PF       |
| 1025    | sfpf          | [Stateful Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-sfpf)                       | sfpf:     | http://docs.oasis-open.org/openc2/ns/ap/sfpf/v1.0      | GH WD01, no CSD, superseded by PF         |
| 1026    | sbom          | [Software Bill of Materials AP](https://github.com/oasis-tcs/openc2-ap-sbom)                      | sbom:     | http://docs.oasis-open.org/openc2/ns/ap/sbom/v2.0      | GH WD01 2021/11/17                        |
| 1027    | er            | [Endpoint Response AP](https://github.com/oasis-tcs/openc2-ap-er)                                 | er:       | http://docs.oasis-open.org/openc2/ns/ap/er/v2.0        | GH 2021/06/02, rename from EDR            |
| 1028    | hop           | [Honeypot Control AP](https://github.com/oasis-tcs/openc2-ap-honeypots)                           | hop:      | http://docs.oasis-open.org/openc2/ns/ap/hop/v1.0       | GH 2021/10/13, use cases                  |
| 1029    | av            | [Anti-virus AP](https://github.com/oasis-tcs/openc2-ap-av)                                        | av:       | http://docs.oasis-open.org/openc2/ns/ap/av/v1.0        | Repo created                              |
| 1030    | ids           | [Intrusion Detection AP](https://github.com/oasis-tcs/openc2-ap-ids)                              | ids:      | http://docs.oasis-open.org/openc2/ns/ap/ids/v1.0       | Repo created, no template                 |
| 1031    | log           | [Logging Control AP](https://github.com/oasis-tcs/openc2-ap-lc)                                   | log:      | http://docs.oasis-open.org/openc2/ns/ap/log/v1.0       | Repo created, no template                 |
| 1032    | swup          | [Software Update AP](https://github.com/oasis-tcs/openc2-ap-sup)                                  | sup:      | http://docs.oasis-open.org/openc2/ns/ap/swup/v1.0      | Repo requested                            |
| 1034    | pf            | [Packet Filtering AP](https://github.com/oasis-tcs/openc2-ap-pf)                                  | pf:       | http://docs.oasis-open.org/openc2/ns/ap/pf/v2.0        | CSD01 2021/07/21 supersedes SLPF and SFPF |
| 1035    | pac           | [Security Posture Attribute Collection AP](https://github.com/oasis-tcs/openc2-ap-pf)             | pac:      | http://docs.oasis-open.org/openc2/ns/ap/pac/v2.0       | Repo created                              |
| 1036    | hunt            | [Threat Hunting AP](https://github.com/oasis-tcs/openc2-ap-hunt)                                  | hunt:   | http://docs.oasis-open.org/openc2/ns/ap/hunt/v2.0        | Repo created                              |
|         |               | <div style="text-align: center">**Extension Actuator Profile**</div>                              |           |                                                        |                                           |
| 9001    | blinky        | Blinky Lights with HTTP and MQTT API                                                              | led:      | http://docs.oasis-open.org/openc2/ns/ext/ap-led/v2.0   | No repo, documented in plugfest use cases |
|         |               | <div style="text-align: center">**Proposed Actuator Profile**</div>                               |           |                                                        |                                           |
|         |               | Endpoint Response (previously EDR, listed above)                                                  |           |                                                        |                                           |
|         |               | Threat Analytics (split from EDR)                                                                 |           |                                                        |                                           |
|         |               | Software Defined Network Controller                                                               |           |                                                        |                                           |
|         |               | Email Gateway                                                                                     |           |                                                        |                                           |
|         |               | Intrusion Prevention                                                                              |           |                                                        |                                           |
|         |               | Data Loss Prevention                                                                              |           |                                                        |                                           |
|         |               | Secure Web Gateway                                                                                |           |                                                        |                                           |
|         |               | Security Posture Evaluation                                                                       |           |                                                        |                                           |
