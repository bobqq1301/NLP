# Ontology Learning

**Ontology learning** is the automatic or semi-automatic creation of ontology, including extracting the corresponding domain's terms and the relationships between the concepts that these terms represent from a corpus of natural language text, and encoding them with an ontology language for easy retrieval.

## Procedure

The process is usually split into the following **eight** tasks, which are not all necessarily applied in every ontology learning system.

### Domain terminology extraction

During this step, **domain-specific terms** are extracted, which are used in the following step to derive concepts. Relevant terms can be determined by calculation of the *TF/IDF* values or by application of the *C-value / NC-value* method.

### Concept discovery

In this step, terms are grouped to meaning bearing units, which correspond to an abstraction of the words and therefore to concepts. The grouped terms are there domain-specific terms and their synonyms.

### Concept hierarchy derivation

In this step, the OL system tries to arrange the extracted concepts in a **taxonomic structure**, mostly achieved by unsupervised *hierarchical clustering* methods.

### Learning of non-taxonomic relations

In this step, relationships are extracted, which do not express any sub- or supersumption. There are two common approaches to solve this subtask:

* based upon the extraction of anonymous associations;
* extracts verbs, which indicate a relationship between the entities, represented by the surrounding words.

But the result of both approaches has to be evaluated by an ontologist.

### Rule discovery

In this step, **axioms** are generated for the extracted concepts. This can be achieved by analyzing the syntactic structure of a natural language definition and the application of transformation rules on the resulting dependency tree. The result is a list of axioms, which is afterwards comprehended to a concept description, has to be evaluated by an ontologist.

### Ontology population

In this step, the ontology is augmented with instances of concepts and properties. For the augmentation with instances of concepts, methods based on the matching of lexico-syntactic patterns are used. Instances of properties are added by application of bootstrapping methods, which collect relation tuples.

### Concept hierarchy extension

In this step, the OL system tries to extend the taxonomic structure of an existing ontology with further concepts. This can be realized supervised by a trained classifier or unsupervised by the application of similarity measures.

### Frame and Event detection

In this step, the OL system tries to extract complex relationships from text. Approaches range from applying SVM with kernel methods to semantic role labeling to deep semantic parsing techniques.

# References

## C-value / NC-value method

[C-value / NC-value](./[210325]C-value_NC-value.md)

## Hierarchical clustering

## Sub- or supersumption relationships