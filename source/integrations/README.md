### Creating an .owl file from .tsv using SSSOM  
sssom convert cdif4xas-mappings.sssom.tsv --output-format owl -o cdif4xas-mappings.sssom.owl

### Merging mappings with ddi-cdi ontology
robot merge --input cdif4xas-mappings.sssom.owl \
	--input ../imports/cdi_import.owl \
	--output ../../cdif4xas.owl
