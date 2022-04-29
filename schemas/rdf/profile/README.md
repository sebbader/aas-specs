# AAS RDF Profile

This is a simplified, RDF-native version for the AAS Metamodel.

## Issues with the current RDF-serialization


| Name                                                                    | Description                                                                                                                                                                           | Example                                                                                                                                                        | Possible Fix                                         |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Domain and Range                                                        | The current model uses rdfs:domain and rdfs:range which do not implement OWL-semantics                                                                                                | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/rdf-ontology.ttl#L34)                                | Replace with OWL restrictions                        |
| _Reference_ Object                                                      | The AAS-meta-model uses a _Reference_ element to link to other resources. The RDF-serialization holds the URI as a literal. This is inefficient as it interrupts the graph structure. | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L45)                   | Leverage _Reference_ target identifiers as resources |
| [URI structure](https://github.com/admin-shell-io/aas-specs/issues/166) | Semantically equivalent properties have different URIs as they are tied to their respective Meta-Model-Element.                                                                       | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L105) vs. [Example2](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L155) | Harmonize URIs                                       |
| Semantic Versioning                                                     | The current RDF files (spec & examples) work toward V3RC02 of the meta-model and should represent this in their namespace.                                                            | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/profile/rdf-profile-shapes.ttl#L1)                                | Update To RC02                                       |



## Contributors

| Github | Name | Affiliation |
|--|--|--|
| [alw-iwu](https://github.com/alw-iwu) | Arno Weiß | Fraunhofer IWU |
| [changqin26](https://github.com/changqin26) | Chang Qin | Fraunhofer IAIS |
| [kenwenzel](https://github.com/kenwenzel) | Ken Wenzel | Fraunhofer IWU |
| [sebbader](https://github.com/sebbader) | Sebastian Bader | SAP SE |
