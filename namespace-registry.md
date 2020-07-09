# OpenC2 Namespace Registry
A [namespace](https://en.wikipedia.org/wiki/Namespace) is a set of names used to identify objects.
A namespace ensures that all of a given set of objects can be easily identified and unambiguously referenced.

All OpenC2 type definitions are contained in a specification, and each specification is assigned a globally-unique
namespace in the form of a URI.  Types in one specification can reference types defined in another
specification using a namespaced name:

    name = <namespace identifier> separator <local name>

XML includes namespaces, but JSON does not.  Because OpenC2 consists of multiple specifications,
it requires a namespacing mechanism even when using JSON data format.
OpenC2 has therefore created a naming approach similar to XML's that can be applied to non-namespaced
data formats such as JSON. This approach uses a *resolver* to look up all namespaced type definitions
from their defining specifications and include them in a single collection of local definitions.
Because the resolver converts all namespaced names to local names, namespace identifiers never appear
in OpenC2 JSON data.
