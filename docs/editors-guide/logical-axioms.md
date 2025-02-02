# Logical Axioms

**Always have the reasoner on in Protege!!! Use the inferred view!**

Use Elk, we generally stay within the EL++ subset. Sometimes UnionOf is used but this is not relied upon in inference.

Note if you don’t stay in the inferred view you will see a lot of redundant subclass assertions.

## SubClassOf axioms

For normal ontology development we would avoid asserting axioms that can be inferred. Here we violate this dictum and assert a subClassOf axiom if it is true and it is asserted elsewhere (we annotate axiom with the source ID). 

If we want to remove a subClassOf axiom that has external evidence, we turn it into a excluded_subClassOf annotation (non-logical) axiom.

## Definitional Equivalence Axioms

In addition to SubClassOf axioms, we have EquivalenceAxioms conforming to design patterns. See the patterns folder for details.

[https://github.com/monarch-initiative/mondo/tree/master/src/patterns](https://github.com/monarch-initiative/mondo/tree/master/src/patterns)

Currently equivalence axioms live in the main ontology file (but are exported to csvs in the patterns folder using dosdp-tools).

DPs are roughly:

* Based on location or affected structure (Uberon/CL/GO-CC)
* For infectious diseases, NCBITaxon for causal agent
* GO
* Rare X

See further on this doc under Design Patterns for more info.

Currently we punt somewhat on semantics. We use ‘disease_has_location’ which has deferred some semantics, essentially to mean “should be classified under X disease”. We will have more discussion on this. We never over-describe with this relation, it is intended for primary location.

