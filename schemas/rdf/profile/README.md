# AAS RDF Profile

This is a simplified, RDF-native version for the AAS Metamodel.

## Issues with the current RDF-serialization


| Name                                                                    | Description                                                                                                                                                                           | Example                                                                                                                                                        | Possible Fix                                         |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------|
| Domain and Range                                                        | The current model uses rdfs:domain and rdfs:range which do not implement OWL-semantics                                                                                                | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/rdf-ontology.ttl#L34)                                | a) Replace with OWL restrictions                        |
|                                                                         |                                                                                                                                                                                                |                                 | b) Only use SHACL Shapes                        |
| _Reference_ Object                                                      | The AAS-meta-model uses a _Reference_ element to link to other resources. The RDF-serialization holds the URI as a literal. This is inefficient as it interrupts the graph structure. | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L45)                   | Leverage _Reference_ target identifiers as resources |
| Referencing in general                                                  | The AAS-meta-model uses Reference->Key->Value paths to describe a (in 80% global) reference, while RDF nativly supports global references (through URIs). There shall be a shortcut to simplify references to one triple. | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L51)                   | Introduce Linked Data references |
| [URI structure](https://github.com/admin-shell-io/aas-specs/issues/166) | Semantically equivalent properties have different URIs as they are tied to their respective Meta-Model-Element.                                                                       | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L105) vs. [Example2](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/examples/Complete_Example.ttl#L155) | Harmonize URIs                                       |
| Semantic Versioning                                                     | The current RDF files (spec & examples) work toward V3RC02 of the meta-model and should represent this in their namespace.                                                            | [Example](https://github.com/sebbader/aas-specs/blob/3411649e1aef3b0db6aefa9e67e2058eb802f6a0/schemas/rdf/profile/rdf-profile-shapes.ttl#L1)                                | Update To RC02                                       |
| Paths to Referables                                                     | Non-identifiables are referenced using concatenated paths from their Identifiable. Let's make all Referables to Identifiables by using a URI construction rule.                                                             | Reference to Property: (Submodel)http://example.org/aas/submodel1 (SubmodelElementCollection)idShortOfSmc (Property)idShortOfProperty -->  http://example.org/aas/submodel1/idShortOfSmc/idShortOfProperty rdf:type aas:Property                      | Making everything identifiable through URI concatenation                                     |



## Contributors

| Github | Name | Affiliation |
|--|--|--|
| [alw-iwu](https://github.com/alw-iwu) | Arno Weiß | Fraunhofer IWU |
| [changqin26](https://github.com/changqin26) | Chang Qin | Fraunhofer IAIS |
| [kenwenzel](https://github.com/kenwenzel) | Ken Wenzel | Fraunhofer IWU |
| [sebbader](https://github.com/sebbader) | Sebastian Bader | SAP SE |
