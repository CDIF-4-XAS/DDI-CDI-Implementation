### Ontology origin  
This is a merged ontology from:
https://github.com/ddi-cdi/ddi-cdi/tree/main/build/encoding/ontology

Used files:
Conceptual.onto.ttl
DataDescription.onto.ttl
KeyValue.onto.ttl
FormatDescription.onto.ttl

Additionally the NamedIndividuals have been removed.


robot merge \
-i  ddi-cdi-source/DataDescription.onto.ttl \
-i  ddi-cdi-source/Conceptual.onto.ttl \
-i  ddi-cdi-source/KeyValue.onto.ttl \
-i  ddi-cdi-source/FormatDescription.onto.ttl  \
-i  ddi-cdi-source/StructuredDataTypes.onto.ttl  \
-o ddi-cdi-source/cdi-ddi.owl


robot remove \
--input ddi-cdi-source/cdi-ddi.owl \
--select individuals \
--output ddi-cdi-source/cdi-ddi_ohne.owl


robot extract --method STAR \
-i  ddi-cdi-source/cdi-ddi_ohne.owl \
--term-file cdi_terms.txt \
--output cdi_import.owl
