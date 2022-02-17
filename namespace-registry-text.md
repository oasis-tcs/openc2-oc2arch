# OpenC2 Namespace Registry

*Text to be re-written and included in the OpenC2 Architecture*

## Namespace Concepts
A [namespace](https://en.wikipedia.org/wiki/Namespace) is a set of names used to identify objects.
A namespace ensures that all of a given set of objects can be easily identified and unambiguously referenced.

All OpenC2 type definitions are contained in a specification, and each specification is assigned a
globally-unique namespace in the form of a URI.  Types in one specification can reference types
defined in another specification using a namespaced name:

    name = <namespace identifier> separator <local name>

XML includes namespaces but JSON does not. Because OpenC2 consists of multiple specifications,
it requires a namespacing mechanism usable with JSON data.
OpenC2 has therefore created a naming approach similar to XML's that can be applied to non-namespaced
data formats such as JSON.  For brevity it assigns a short Namespace Identifier (NSID) to each referenced
namespace using an **import** statement, then uses the NSID as a prefix to each referenced type:

**schema**:
```
    import: {"ex": "http://www.example.com/datatypes/v1.2"}

    Person = Record
        1 name   String
        2 id     Integer
        3 email  ex:Email-Address       // type definition imported/resolved from another specification
```
**JSON data**:
```
    {"name": "John", "id": 12345, "email": "john@acme.com"}
```
Namespacing thus involves four different values:
* **Namespace**: The unique identifier of a referenced specification: "http://www.example.com/datatypes/v1.2"
* **Type Name**: the name of a type defined in a referenced specification: "Email-Address"
* **NSID**: a short abbreviation for a Namespace used as a prefix in an imported type: "ex"
* **Field Name**: may be serialized as a JSON object property whose value is an imported type: "email"

NSID and Field Name are both defined by the importing specification; neither are registered here.
Type Names (including NSID prefixes) never appear in JSON data, so Namespaces and NSIDs are never
needed or used in JSON data except within a schema document.

This approach uses a resolver to look up all namespaced type definitions from their defining specifications
and incorporate them into a single schema. Authors can manually copy and paste definitions
into a monolithic specification, but namespace resolution automates that process, eliminating redundancy
and the potential for inconsistency.

A namespace URI is only an identifier. For syntactic reasons it must have a scheme (http) but it
is not a network-accessible resource. 
Referenced specifications do not need to be available online and implementations are not required to do
namespace resolution at runtime, although dynamic namespace resolution may be appropriate for some use cases.
URLs for online schemas should be derived from the namespace using scheme "https", filename "schema", and
the applicable file extension: ".jadn" for the abstract schema, and ".json", ".xsd", ".cddl", ".proto", etc.
for corresponding concrete schemas.

## Registration Process
OpenC2 TC Documentation Norms suggests
[naming conventions](https://github.com/oasis-tcs/openc2-tc-ops/blob/master/Documentation-Norms.md#42-assign-work-product-name)
for TC work products.  Namespace URIs should be based on this convention, omitting the filename and the "docs" domain component,
and using "http" as the scheme component.

* **Actuator Profile Name**: ap-\<function-shorthand\>
* **Example Profile URL**: https://docs.oasis-open.org/openc2/ap-av/v1.0/ap-av-v1.0.html
* **Example Namespace**: http://oasis-open.org/openc2/ap-av/v1.0
* **Example Schema URL**: https://oasis-open.org/openc2/ap-av/v1.0/schema.jadn

Custom actuator profile namespaces are chosen by the profile author and MUST NOT conflict with namespace URIs registered here.
Custom profile authors MAY register Namespaces under http://oasis-open.org/openc2/custom but are not required to do so.
