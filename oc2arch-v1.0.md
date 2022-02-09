
![OASIS Logo](http://docs.oasis-open.org/templates/OASISLogo-v3.0.png)

-------

# Open Command and Control (OpenC2) Architecture Specification Version 1.0

## Working Draft 03

## 19 January 2022

&nbsp;

<!-- URI list start (commented out except during publication by OASIS TC Admin)

#### This stage:
https://docs.oasis-open.org/openc2/oc2arch/v1.0/csd01/oc2arch-v1.0-csd01.md (Authoritative) \
https://docs.oasis-open.org/openc2/oc2arch/v1.0/csd01/oc2arch-v1.0-csd01.html \
https://docs.oasis-open.org/openc2/oc2arch/v1.0/csd01/oc2arch-v1.0-csd01.pdf

#### Previous stage:
N/A

#### Latest stage:
https://docs.oasis-open.org/openc2/oc2arch/v1.0/oc2arch-v1.0.md (Authoritative) \
https://docs.oasis-open.org/openc2/oc2arch/v1.0/oc2arch-v1.0.html \
https://docs.oasis-open.org/openc2/oc2arch/v1.0/oc2arch-v1.0.pdf

URI list end (commented out except during publication by OASIS TC Admin) -->

#### Technical Committee:
[OASIS Open Command and Control (OpenC2) TC](https://www.oasis-open.org/committees/openc2/)

#### Chair:
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](https://www.sfractal.com/) \
Michael Rosa (mjrosa@cyber.nsa.gov), [National Security Agency](https://www.nsa.gov/)

#### Editors:
Dan Johnson (dj@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/) \
Duncan Sparrell (duncan@sfractal.com), [sFractal Consulting LLC](http://www.sfractal.com/)

#### Additional artifacts:
This prose specification is one component of a Work Product that also includes:
* XML schemas: (list file names or directory name)
* Other parts (list titles and/or file names)
* `(Note: Any normative computer language definitions that are part of the Work Product, such as XML instances, schemas and Java(TM) code, including fragments of such, must be (a) well formed and valid, (b) provided in separate plain text files, (c) referenced from the Work Product; and (d) where any definition in these separate files disagrees with the definition found in the specification, the definition in the separate file prevails. Remove this note before submitting for publication.)`

#### Related work:
This specification is related to:
* _Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html.

#### Abstract:
Cyberattacks are increasingly sophisticated, less expensive to execute, dynamic and automated. The provision of cyber defense via statically configured products operating in isolation is untenable. Standardized interfaces, protocols and data models will facilitate the integration of the functional blocks within a system and between systems. Open Command and Control (OpenC2) is a concise and extensible language to enable machine-to-machine communications for purposes of command and control of cyber defense components, subsystems and/or systems in a manner that is agnostic of the underlying products, technologies, transport mechanisms or other aspects of the implementation.

This document describes the Abstract Architecture of OpenC2, to define a common understanding of the messages and interactions for all bindings and serializations.

#### Status:
This document was last revised or approved by the OASIS Open Command and Control (OpenC2) TC on the above date. The level of approval is also listed above. Check the "Latest stage" location noted above for possible later revisions of this document. Any other numbered Versions and other technical work produced by the Technical Committee (TC) are listed at https://www.oasis-open.org/committees/tc_home.php?wg_abbrev=openc2#technical.

TC members should send comments on this specification to the TC's email list. Others should send comments to the TC's public comment list, after subscribing to it by following the instructions at the "[Send A Comment](https://www.oasis-open.org/committees/comments/index.php?wg_abbrev=)" button on the TC's web page at https://www.oasis-open.org/committees/openc2/.

This specification is provided under the [Non-Assertion](https://www.oasis-open.org/policies-guidelines/ipr#Non-Assertion-Mode) Mode of the OASIS IPR Policy, the mode chosen when the Technical Committee was established. For information on whether any patents have been disclosed that may be essential to implementing this specification, and any offers of patent licensing terms, please refer to the Intellectual Property Rights section of the TC's web page (https://www.oasis-open.org/committees/openc2/ipr.php).

Note that any machine-readable content ([Computer Language Definitions](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsCompLang)) declared Normative for this Work Product is provided in separate plain text files. In the event of a discrepancy between any such plain text file and display content in the Work Product's prose narrative document(s), the content in the separate plain text file prevails.

#### Key words:
The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "NOT RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in BCP 14 [[RFC2119](#rfc2119)] and [[RFC8174](#rfc8174)] when, and only when, they appear in all capitals, as shown here.

#### Citation format:
When referencing this specification the following citation format should be used:

**[OpenC2-Arch-v1.0]**

_Open Command and Control (OpenC2) Architecture Specification Version 1.0_. Edited by Dan Johnson and Duncan Sparrell. 19 August 2021. OASIS Committee Specification Draft 01. https://docs.oasis-open.org/openc2/oc2arch/v1.0/csd01/oc2arch-v1.0-csd01.html. Latest stage: https://docs.oasis-open.org/openc2/oc2arch/v1.0/oc2arch-v1.0.html.

#### Notices
Copyright © OASIS Open 2021. All Rights Reserved.

Distributed under the terms of the OASIS [IPR Policy](https://www.oasis-open.org/policies-guidelines/ipr).

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs.

For complete copyright information please see the full Notices section in an Appendix below.

-------

# Table of Contents
[[TOC will be inserted here]]

-------

# 1 Introduction

_The content in this section is non-normative, except where it is
marked normative._

OpenC2 is a suite of specifications that enables command and
control of cyber defense systems and components. OpenC2 typically
uses a request-response paradigm where a _Command_ is encoded by
a _Producer_ (managing application) and transferred to a
_Consumer_ (managed device or virtualized function) using a
secure transfer protocol, and the Consumer can respond with
status and any requested information.

OpenC2 allows the application producing the commands to discover
the set of capabilities supported by the managed devices. These
capabilities permit the managing application to adjust its
behavior to take advantage of the features exposed by the managed
device. The capability definitions can be easily extended in a
noncentralized manner, allowing standard and non-standard
capabilities to be defined with semantic and syntactic rigor.

OpenC2 is defined across a family of specifications of several types:

* The **OpenC2 Architecture Specification** (this document)
  describes the fundamental structures of OpenC2 and provides a
  blueprint for developing Actuator Profiles and Transfer
  Specifications.

* The **OpenC2 Language Specification** provides the semantics
 for the essential elements of the language, the structure for
  Commands and Responses, and the schema that defines the proper
  syntax for the language elements that represents the Command or
  Response. The Language Specification also defines the
  mechanisms for extending the OpenC2 language.
  [[OpenC2-Lang-v1.0]](#openc2-lang-v10)

* **OpenC2 Actuator Profiles** specify the subset of the OpenC2
  language relevant in the context of specific Actuator
  functions. Cyber defense components, devices, systems and/or
  instances may (in fact are likely to) implement multiple
  Actuator profiles. Actuator profiles extend the language by
  defining Specifiers that identify the Actuator to the required
  level of precision. Actuator Profiles may also define Command
  Arguments and Targets that are relevant and/or unique to those
  Actuator functions.

* **OpenC2 Transfer Specifications** utilize existing protocols
  and standards to implement OpenC2 message transfer in specific
  environments. These standards are used for communications and
  security functions beyond the scope of the language, such as
  message transfer encoding, authentication, and end-to-end
  transport of OpenC2 Messages.

The most common encoding of OpenC2 is in JSON and the most common
binding is to HTTP; this document assumes this encoding and
binding for all examples. Other encodings and bindings are
permitted and are defined in their respective documents.

## 1.1 Changes from earlier versions

* Reformatted to December 2020 OASIS work product template

## 1.2 Glossary

<!-- Optional section with suggested subsections -->

### 1.2.1 Definitions of terms

*This section is normative.*

-   **Action**: The task or activity to be performed (e.g., 'deny').

-   **Actuator**: The function performed by the Consumer that executes the
    Command (e.g., 'Stateless Packet Filtering').

-   **Argument**: A property of a Command that provides additional information
    on how to perform the Command, such as date/time, periodicity, duration,
    etc.

-   **Command**: A Message defined by an Action-Target pair that is sent from a
    Producer and received by a Consumer.

-   **Consumer**: A managed device / application that receives Commands. Note
    that a single device / application can have both Consumer and Producer
    capabilities.

-   **Message**: A content- and transport-independent set of elements conveyed
    between Consumers and Producers.

-   **Producer**: A manager application that sends Commands.

-   **Request**: A Message from a Producet to a Consumer used to convey a
    Command.
    
-   **Response**: A Message from a Consumer to a Producer acknowledging a
    Command or returning the requested resources or status to a previously
    received Command.

-   **Specifier**: A property or field that identifies a Target or Actuator to
    some level of precision.

-   **Target**: The object of the Action, i.e., the Action is performed on the
    Target (e.g., IP Address).

### 1.2.2 Acronyms and abbreviations

| Acronym | Description |
|---------|----------------------------------------------------------------------|
| API     | Application Programming Interface |
| ASCII   | American Standard Code for Information Interchange |
| BCP     | Best Current Practice |
| CBOR    | Concise Binary Object Representation |
| CIDR    | Classless Inter-Domain Routing |
| CoAP    | Constrained Application Protocol |
| DOI     | Digital Object Identifier |
| EUI     | Extended Unique Identifier |
| HTTP    | Hyper Text Transfer Protocol |
| HTTPS   | Hyper Text Transfer Protocol Secure |
| IACD    | Integrated Adaptive Cyber Defense |
| IANA    | Internet Assigned Numbers Authority |
| ICMP    | Internet Control Message Protocol |
| ID      | Identifier |
| IP      | Internet Protocol |
| IPR     | Intellectual Property Rights |
| JSON    | JavaScript Object Notation |
| MAC     | Media Access Control |
| MQTT    | Message Queuing Telemetry Transfer |
| OASIS   | Organization for the Advancement of Structured Information Standards |
| OODA    | Observe-Orient-Decide-Act |
| OpenC2  | Open Command and Control |
| OpenDXL | Open Data eXchange Layer |
| PDF     | Portable Document Format |
| RFC     | Request for Comment |
| SCTP    | Stream Control Transmission Protocol |
| SHA     | Security Hash Algorithm |
| SLPF    | StateLess Packet Filtering |
| STD     | Standard |
| TC      | Technical Committee |
| TCP     | Transmission Control Protocol |
| UDP     | User Datagram Control Protocol |
| UML     | Unified Modeling Language |
| URI     | Uniform Resource Identifier |
| UTC     | Coordinated Universal Time |
| UUID    | Universally Unique IDentifier |
| XML     | eXtensible Markup Language |


### 1.2.3 Document conventions

- Naming conventions
- Font colors and styles
- Typographic conventions

## 1.3 Some markdown usage examples

**Text.**

Note that text paragraphs in markdown should be separated by a blank line between them -

Otherwise the separate paragraphs will be joined together when the HTML is generated.
Even if the text appears to be separate lines in the markdown source.

To avoid having the usual vertical space between paragraphs,  
append two or more space characters (or space-backslash) to the end of the lines  
which will generate an HTML break tag instead of a new paragraph tag \
(as demonstrated here).

### 1.3.1 Figures and Captions

FIGURE EXAMPLE:
<note caption is best placed ABOVE figure, so a hyperlink to it will actually display the figure, instead of rendering the figure off the screen above the caption. The same placement should be used for table captions>

###### Figure 1 -- Title of Figure
![image-label should be meaningful](images/image_0.png) (this image is intentionally missing)

###### Figure 2 -- OpenC2 Message Exchange
![message exchange](images/image_1.png)


### 1.3.2 Tables

#### 1.3.2.1 Basic Table
**Table 1-1. Table Label**

| Item | Description |
| :--- | :--- |
| Item 1 | Something<br>(second line) |
| Item 2 | Something |
| Item 3 | Something<br>(second line) |
| Item 4 | text |

#### 1.3.2.2 Table with Three Columns and Some Bold Text
text.

| Title 1 | Title 2 | title 3 |
| :--- | :--- | :--- |
| something | something | something else that is a long string of text that **might** need to wrap around inside the table box and will just continue until the column divider is reached |
| something | something | something |

#### 1.3.2.3 Table with a caption which can be referenced

###### Table 1-5. See reference label construction

| Name | Description |
| :--- | :--- |
| **content** | Message body as specified by content_type and msg_type. |

Here is a reference to the table caption:
Please see [Table 1-5 or other meaningful label](#table-1-5-see-reference-label-construction) 


### 1.3.3 Lists

Bulleted list:
* bullet item 1.
* **Bold** bullet item 2.
* bullet item 3.
* bullet item 4.

Indented or multi-level bullet list - add two spaces per level before bullet character (* or -):
* main bullet type
  * Example second bullet
    * See third level
      * fourth level

Numbered list:
1. item 1
2. item 2
3. item 3

Left-justified list without bullets or numbers:
To list multiple items without full paragraph breaks between items, add space-backslash after each item except the last.

### 1.3.4 Reference Label Construction

REFERENCES and ANCHORS
- in markdown source, format the Reference tags as level 6 headings like: `###### [RFC2119]`
###### [RFC2119]
Bradner, S., "Key words ..."

- reference text has to be on a separate line below the tag

- format cross-references (citations of the references) like: `see [[RFC2119](#rfc2119)]`  
"see [[RFC2119](#rfc2119)]"  
(note the outer square brackets in markdown will appear in the visible HTML text)

- The text in the Reference tag (following ###### ) will become an HTML anchor using the following conversion rules:  
  - punctuation marks will be dropped (including "[" )  
  - leading white spaces will be dropped  
  - upper case will be converted to lower  
  - spaces between letters will be converted to a single hyphen

- The same HTML anchor construction rules apply to cross-references and to section headings.  
  - Thus, a section heading like "## 1.2 Glossary"  
  - becomes an anchor in HTML like `<a href="#12-glossary">`  
  - referenced in the markdown like: see [Section 1.2](#12-glossary)  
  - in markdown: `"see [Section 1.2](#12-glossary)"`  
  - similar HTML anchors are also used in constructing the TOC

### 1.3.5 Code Blocks

Text to appear as an indented code block with grey background and monospace font - use three back-ticks before and after the code block.

Note the actual backticks will not appear in the HTML format. If it's necessary to display visible backticks, place a back-slash before them like: \``` .

```
{   
    "target": {
        "x_kmip_2.0": {
            {"kmip_type": "json"},
            {"operation": "RekeyKeyPair"},
            {"name": "publicWebKey11DEC2017"}
        }
    }
}
```

Text to be highlighted as code can also be surrounded by a single "backtick" character: 
`code text`

## 1.4 Page Breaks
Add horizontal rule lines where page breaks are desired in the PDF - before each major section
- insert the line rules in markdown by inserting 3 or more hyphens on a line by themselves:  ---
- place these before each main section in markdown (usually "#" - which generates the HTML `<h1>` tag)

-------

# 2 Overview of OpenC2 Architecture

OpenC2 is a suite of specifications for Producers and Consumers
to command and execute cyber defense functions. These
specifications include the OpenC2 Language Specification,
Actuator Profiles, and Transfer Specifications. The OpenC2
[Language Specification](#openc2-lang-v10) and Actuator Profile
specifications focus on the language content and meaning at the
Producer and Consumer level of Command and Response while the
transfer specifications focus on the protocols for their
exchange.

In general, there are two types of participants involved in the
exchange of OpenC2 Messages, as depicted in Figure 2-1:

1. **Producers**: A Producer is an entity that creates Commands
   to provide instruction to one or more systems to act in
   accordance with the content of the Command. A Producer may
   receive and process Responses in conjunction with a Command.
2. **Consumers**: A Consumer is an entity that receives and may
   act upon a Command. A Consumer may create Responses that
   provide any information captured or necessary to send back to
   the Producer.

**Figure 2-1. OpenC2 Message Exchange**

![OpenC2 Message Exchange](images/MessageFlow.png)


The language defines two payload structures:

1. **Command**: An instruction from one system known as the
   Producer, to one or more systems, the Consumer(s), to act on
   the content of the Command.
2. **Response**: Any information sent back to the Producer as a
   result of the Command.

## 2.1 Commands and Responses

The OpenC2 language has two distinct content types: Command and
Response. The Command is sent from a Producer to a Consumer and
describes an Action to be performed by an Actuator on a Target.
The Response is sent from a Consumer, usually back to the
Producer, and is a means to provide information (such as
acknowledgment, status, etc.) as a result of a Command.

### 2.1.1 OpenC2 Command
The Command describes an Action to be performed on a Target and
may include information identifying the Actuator or Actuators
that are to execute the Command. A Command can also contain an
optional Command identifier, if necessary. The following list
summarizes the main four components of a
Command.

* **Action** (required): The task or activity to be performed.
* **Target** (required): The object of the action. The Action is
  performed on the Target. Properties of the Target, called
  Target Specifiers, further identify the Target to some level of
  precision, such as a specific Target, a list of Targets, or a
  class of Targets.
* **Arguments** (optional): Provide additional information on how
  the command is to be performed, such as date/time, periodicity,
  duration, etc.
* **Actuator** (optional): The Actuator executes the Command. The
  Actuator will be defined within the context of an Actuator
  Profile. Properties of the Actuator, called Actuator
  Specifiers, further identify the Actuator to some level of
  precision, such as a specific Actuator, a list of Actuators, or
  a group of Actuators.

The Action and Target components are required. A particular
Target may be further refined by the Target type. The [Language
Specification](#openc2-lang-v10) defines procedures to extend the
set of OpenC2 Targets.

Command Arguments, if present, influence the Command by providing
information such as timing, periodicity, duration, or other
details on what is to be executed. They can also be used to
convey the need for acknowledgment or additional status
information about the execution of a Command.

An Actuator is an implementation of a cyber defense function that
executes the Command. An Actuator Profile is a specification that
identifies the subset of Actions, Targets and other aspects of
the OpenC2 language that are required or optional in the
context of a particular Actuator. An Actuator Profile may extend
the language by defining additional Targets, Arguments, and
Actuator Specifiers that are meaningful and possibly unique to
the Actuator.

The Actuator may be omitted from a Command and typically will not
be included in implementations where the identities of the
endpoints are unambiguous or when a high-level effects-based
Command is desired and the tactical decisions on how the effect
is achieved is left to the recipient.


### 2.1.2 OpenC2 Response
The Response is a Message sent from the recipient of a Command.
Response messages provide acknowledgment, status, results from a
query, or other information. At a minimum, a Response will
contain a status code to indicate the result of performing the
Command. Additional status text and response fields optionally
provide more detailed information that is specific to or
requested by the Command.


## 2.2 Producers, Consumers, and Devices

Figure 2-X illustrates three representative
configurations for an OpenC2 Consumer device:

1. The Consumer implements a single Actuator Profile (AP).
1. The Consumer implements multiple APs, which may be all
   different, all the same, or a mixture.
1. The Consumer is a manager for a collection of devices,
   providing an indirect means for the Producer to use
   OpenC2 Commands to influence the operations of those
   devices. The managed devices in the collection may or may
   not be identical.

In configurations 1 and 2, the Producer has direct, explicit
knowledge of the APs implemented by the Consumer.  OpenC2
Commands issued by the Producer directly affect the
operation of the Consumer device.  An example of multiple
instances of the same AP in configuration 2 would be packet
filtering functions on multiple, distinct network
interfaces.

In configuration 3, the Producer has knowledge of the
capabilities supported by the Consumer manager, but only
indirect affect the operation of the managed devices. In
configuration 3 there is no assumption that the interface
between the Consumer manager and the managed devices uses
OpenC2 Commands and Responses.

**Figure 2-2. Producer / Consumer / Device Configurations**

![Producer-Consumer-Device Configurations](images/PCD-Configurations.png)


## 2.3 Implementations

OpenC2 implementations integrate the OpenC2 specifications
described above with related industry specifications, protocols,
and standards. Figure 2-3 depicts the relationships among the
family of OpenC2 specifications, and their relationships to other
industry standards and environment-specific implementations of
OpenC2. Note that the layering of implementation aspects in the
diagram is notional, and not intended to preclude any particular
approach to implementing the needed functionality (for example,
the use of an application-layer message signature function to
provide message source authentication and integrity).


**Figure 2-3. OpenC2 Documentation and Layering Model**
![OpenC2 Documentation and Layering Model](images/OC2LayeringModel.png)

OpenC2 is conceptually partitioned into four layers as shown in
Table 2-1.

**Table 2-1. OpenC2 Protocol Layers**

| Layer | Examples |
| :--- | :--- |
| Function-Specific Content | Actuator Profiles<br>([OpenC2-SLPF-v1.0](#openc2-slpf-v10), ...) |
| Common Content | Language Specification |
| Message | Transfer Specifications<br>([OpenC2-HTTPS-v1.0](#openc2-https-v10), [OpenC2-MQTT-v1.0](#openc2-mqtt-v10), ...) |
| Secure Transport | HTTPS, CoAP, MQTT, OpenDXL, ... |

* The **Secure Transport** layer provides a communication path
  between the Producer and the Consumer. OpenC2 can be layered
  over any standard transport protocol.
* The **Message** layer provides a transfer- and
  content-independent mechanism for conveying Messages. A
  transfer specification maps transfer-specific protocol elements
  to a transfer-independent set of message elements consisting of
  content and associated metadata.
* The **Common Content** layer defines the structure of Commands
  and Responses and a set of common language elements used to
  construct them.
* The **Function-specific Content** layer defines the language
  elements used to support a particular cyber defense function.
  An Actuator profile defines the implementation conformance
  requirements for that function. Producers and Consumers will
  support one or more profiles.

The components of a Command are an Action (what is to be done), a
Target (what is being acted upon), an optional Actuator (what is
performing the command), and Command Arguments, which influence
how the Command is to be performed. An Action coupled with a
Target is sufficient to describe a complete Command. Though
optional, the inclusion of an Actuator and/or Command Arguments
provides additional precision to a Command.

The components of a Response are a numerical status code, an
optional status text string, and optional results. The format of
the results, if included, depend on the type of Response being
transferred.



-------

# 3 Conformance
<!-- Required section -->

(Note: The [OASIS TC Process](https://www.oasis-open.org/policies-guidelines/tc-process#wpComponentsConfClause) requires that a specification approved by the TC at the Committee Specification Public Review Draft, Committee Specification or OASIS Standard level must include a separate section, listing a set of numbered conformance clauses, to which any implementation of the specification must adhere in order to claim conformance to the specification (or any optional portion thereof). This is done by listing the conformance clauses here.
For the definition of "conformance clause," see [OASIS Defined Terms](https://www.oasis-open.org/policies-guidelines/oasis-defined-terms-2017-05-26#dConformanceClause).

See "Guidelines to Writing Conformance Clauses":  
http://docs.oasis-open.org/templates/TCHandbook/ConformanceGuidelines.html.

Remove this note before submitting for publication.)


-------

# Appendix A. References

<!-- Required section -->

This appendix contains the normative and informative references that are used in this document.

While any hyperlinks included in this appendix were valid at the time of publication, OASIS cannot guarantee their long-term validity.

## A.1 Normative References

The following documents are referenced in such a way that some or all of their content constitutes requirements of this document.

(Reference sources:
For references to IETF RFCs, use the approved citation formats at:  
http://docs.oasis-open.org/templates/ietf-rfc-list/ietf-rfc-list.html.  
For references to W3C Recommendations, use the approved citation formats at:  
http://docs.oasis-open.org/templates/w3c-recommendations-list/w3c-recommendations-list.html.  
Remove this note before submitting for publication.)

###### [OpenC2-Lang-v1.0]
_Open Command and Control (OpenC2) Language Specification Version 1.0_. Edited by Jason Romano and Duncan Sparrell. Latest stage: https://docs.oasis-open.org/openc2/oc2ls/v1.0/oc2ls-v1.0.html

###### [OpenC2-HTTPS-v1.1]
_Specification for Transfer of OpenC2 Messages via HTTPS Version 1.1_. Edited by David Lemire. Latest stage: https://docs.oasis-open.org/openc2/open-impl-https/v1.1/open-impl-https-v1.1.html

###### [OpenC2-MQTT-v1.0]
_Specification for Transfer of OpenC2 Messages via MQTT Version 1.0_. Edited by David Lemire. Latest stage: https://docs.oasis-open.org/openc2/transf-mqtt/v1.0/transf-mqtt-v1.0.html

###### [OpenC2-SLPF-v1.0]
_Open Command and Control (OpenC2) Profile for Stateless Packet Filtering Version 1.0_. Edited by Joe Brule, Duncan Sparrell, and Alex Everett. Latest stage: https://docs.oasis-open.org/openc2/oc2slpf/v1.0/oc2slpf-v1.0.html

###### [RFC2119]
Bradner, S., "Key words for use in RFCs to Indicate Requirement Levels", BCP 14, RFC 2119, DOI 10.17487/RFC2119, March 1997, http://www.rfc-editor.org/info/rfc2119.

###### [RFC8174]
Leiba, B., "Ambiguity of Uppercase vs Lowercase in RFC 2119 Key Words", BCP 14, RFC 8174, DOI 10.17487/RFC8174, May 2017, http://www.rfc-editor.org/info/rfc8174.

## A.2 Informative References

###### [RFC3552]
Rescorla, E. and B. Korver, "Guidelines for Writing RFC Text on Security Considerations", BCP 72, RFC 3552, DOI 10.17487/RFC3552, July 2003, https://www.rfc-editor.org/info/rfc3552.

-------

# Appendix B. Safety, Security and Privacy Considerations

<!-- Optional section -->

(Note: OASIS strongly recommends that Technical Committees consider issues that might affect safety, security, privacy, and/or data protection in implementations of their specification and document them for implementers and adopters. For some purposes, you may find it required, e.g. if you apply for IANA registration.

While it may not be immediately obvious how your specification might make systems vulnerable to attack, most specifications, because they involve communications between systems, message formats, or system settings, open potential channels for exploit. For example, IETF [[RFC3552](#rfc3552)] lists “eavesdropping, replay, message insertion, deletion, modification, and man-in-the-middle” as well as potential denial of service attacks as threats that must be considered and, if appropriate, addressed in IETF RFCs.

In addition to considering and describing foreseeable risks, this section should include guidance on how implementers and adopters can protect against these risks.

We encourage editors and TC members concerned with this subject to read _Guidelines for Writing RFC Text on Security Considerations_, IETF [[RFC3552](#rfc3552)], for more information.

Remove this note before submitting for publication.)

-------

# Appendix C. Acknowledgments

<!-- Required section -->

Note: A Work Product approved by the TC must include a list of people who participated in the development of the Work Product. This is generally done by collecting the list of names in this appendix. This list shall be initially compiled by the Chair, and any Member of the TC may add or remove their names from the list by request. Remove this note before submitting for publication.

## C.1 Special Thanks

<!-- This is an optional subsection to call out contributions from TC members. If a TC wants to thank non-TC members then they should avoid using the term "contribution" and instead thank them for their "expertise" or "assistance". -->

Substantial contributions to this document from the following individuals are gratefully acknowledged:

Participant Name, Affiliation or "Individual Member"

## C.2 Participants

<!-- A TC can determine who they list here, however, TC Observers must not be listed. It is common practice for TCs to list everyone that was part of the TC during the creation of the document, but this is ultimately a TC decision on who they want to list and not list. -->

The following individuals have participated in the creation of this specification and are gratefully acknowledged:

**OpenC2 TC Members:**

| First Name | Last Name | Company |
| :--- | :--- | :--- |
Philippe | Alman | Something Networks
Alex | Amirnovman | Company B
Kris | Anderman | Mini Micro
Darren | Anstman | Big Networks

-------

# Appendix D. Revision History

<!-- Optional section -->

| Revision | Date | Editor | Changes Made |
| :--- | :--- | :--- | :--- |
| specname-v1.0-wd01 | yyyy-mm-dd | Editor Name | Initial working draft |

-------

# Appendix E. Example Appendix with subsections

## E.1 Subsection title

### E.1.1 Sub-subsection

-------

# Appendix F. Notices

<!-- Required section. Do not modify. -->

Copyright © OASIS Open 2021. All Rights Reserved.

All capitalized terms in the following text have the meanings assigned to them in the OASIS Intellectual Property Rights Policy (the "OASIS IPR Policy"). The full [Policy](https://www.oasis-open.org/policies-guidelines/ipr) may be found at the OASIS website.

This document and translations of it may be copied and furnished to others, and derivative works that comment on or otherwise explain it or assist in its implementation may be prepared, copied, published, and distributed, in whole or in part, without restriction of any kind, provided that the above copyright notice and this section are included on all such copies and derivative works. However, this document itself may not be modified in any way, including by removing the copyright notice or references to OASIS, except as needed for the purpose of developing any document or deliverable produced by an OASIS Technical Committee (in which case the rules applicable to copyrights, as set forth in the OASIS IPR Policy, must be followed) or as required to translate it into languages other than English.

The limited permissions granted above are perpetual and will not be revoked by OASIS or its successors or assigns.

This document and the information contained herein is provided on an "AS IS" basis and OASIS DISCLAIMS ALL WARRANTIES, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO ANY WARRANTY THAT THE USE OF THE INFORMATION HEREIN WILL NOT INFRINGE ANY OWNERSHIP RIGHTS OR ANY IMPLIED WARRANTIES OF MERCHANTABILITY OR FITNESS FOR A PARTICULAR PURPOSE.

As stated in the OASIS IPR Policy, the following three paragraphs in brackets apply to OASIS Standards Final Deliverable documents (Committee Specification, Candidate OASIS Standard, OASIS Standard, or Approved Errata).

\[OASIS requests that any OASIS Party or any other party that believes it has patent claims that would necessarily be infringed by implementations of this OASIS Standards Final Deliverable, to notify OASIS TC Administrator and provide an indication of its willingness to grant patent licenses to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this deliverable.\]

\[OASIS invites any party to contact the OASIS TC Administrator if it is aware of a claim of ownership of any patent claims that would necessarily be infringed by implementations of this OASIS Standards Final Deliverable by a patent holder that is not willing to provide a license to such patent claims in a manner consistent with the IPR Mode of the OASIS Technical Committee that produced this OASIS Standards Final Deliverable. OASIS may include such claims on its website, but disclaims any obligation to do so.\]

\[OASIS takes no position regarding the validity or scope of any intellectual property or other rights that might be claimed to pertain to the implementation or use of the technology described in this OASIS Standards Final Deliverable or the extent to which any license under such rights might or might not be available; neither does it represent that it has made any effort to identify any such rights. Information on OASIS' procedures with respect to rights in any document or deliverable produced by an OASIS Technical Committee can be found on the OASIS website. Copies of claims of rights made available for publication and any assurances of licenses to be made available, or the result of an attempt made to obtain a general license or permission for the use of such proprietary rights by implementers or users of this OASIS Standards Final Deliverable, can be obtained from the OASIS TC Administrator. OASIS makes no representation that any information or list of intellectual property rights will at any time be complete, or that any claims in such list are, in fact, Essential Claims.\]

The name "OASIS" is a trademark of [OASIS](https://www.oasis-open.org/), the owner and developer of this specification, and should be used only to refer to the organization and its official outputs. OASIS welcomes reference to, and implementation and use of, specifications, while reserving the right to enforce its marks against misleading uses. Please see https://www.oasis-open.org/policies-guidelines/trademark for above guidance.
