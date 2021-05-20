# Introduction of this folder

The artefacts in this folder represent Asset administration Shell (AAS) of the Platform Industrie 4.0 from AAS metamodel and AAS API aspects in terms of RDF. 

## rdf-ontology.ttl

In rdf-ontology.ttl, the classes and relationships of AAS metamodel are described. The metamodel describes how information about assets and I4.0
Components can be processed ans structured. 

## shacl-schema.ttl

Shacl shapes schema define a set of conditions for AAS metamodel ontology. The RDF graphs based on the AAS metamodel ontology need to be validated against
shacl shapes in shacl-schema.ttl. Only when they satisfy the conditions, these RDF graphs can be accpeted.

## examples

Here stores the examples for AAS metamodel, including how to describe an Asset Administraion Shell, an Asset, a Submodel and etc. These examples are the same with the ones 
in Asset Administration Shell Specification.

## aas-api

In this sub-folder, it contains the Ontology, Shacl Shapes descrbing how information can be exchanged via Application Programming Interfaces. 

