## Description of the content in vampire-moth-globi

[![Build Status](https://travis-ci.org/ParasiteTracker/vampire-moth-dwca.svg)](https://travis-ci.org/ParasiteTracker/vampire-moth-dwca) [![GloBI](http://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:ParasiteTracker/vampire-moth-dwca)](http://globalbioticinteractions.org/?accordingTo=globi:ParasiteTracker/vampire-moth-dwca) 

[```Citation```](#Citation) / [```Interaction Types```](#interaction-types) / [```Data Definitions```](#data-definitions) / [```Included Resources```](#included-resources) /  [```Data Issues```](#data-issues) / [```Summary```](#summary)


### Description

vampire-moth-dwca is a repository for specimen occurrence data about vampire moths and their fruit-piercing relatives (Lepidoptera: Erebidae: *Calyptra* spp.). The feeding observations are from the specimens.

This GitHub repository was created by importing the contents of a Symbiota Darwin Core Archive file. All of the fields in the dataset were produced by entering data in presently available fields in Symbiota (September 28, 2018).

### Citation

Jennifer Zaspel. 2018. Biotic species interactions manually extracted from occurrence records.


### Interaction Types

The interactions in this dataset were mapped to terms in the Relations Ontology (RO). Piercing was not available in RO, so ```biotically interacts with``` was used as a replacement.

interactionTypeName | interactionTypeId
--- | --- |
eats | http://purl.obolibrary.org/obo/RO_0002470
piercing | http://purl.obolibrary.org/obo/RO_0002437
enclosed conditions | http://purl.obolibrary.org/obo/ENVO_01001405
in nature | http://purl.obolibrary.org/obo/ENVO_01001226
under experimental conditions | http://purl.obolibrary.org/obo/ENVO_01001405
 
### Data Definitions

The definitions of the key:value pairs that are used in DWC:dynamicProperties field in the occurrences.tsv dataset are described here. This is not an exaustive list of classes to describe the interactions, only the ones that were used in this dataset.

  * A **sourceTaxonId** [DWC:scientificNameID](http://rs.tdwg.org/dwc/terms/scientificNameID) : An identifier for the nomenclatural (not taxonomic) details of a scientific name.
  * A **sourceTaxonName** [DWC:scientificName](http://rs.tdwg.org/dwc/terms/scientificName) : The lowest level taxonomic rank that can be determined.
  * A **interactionTypeId** : Identifier for the interaction type.
  * A **interactionTypeName** : A interaction type (ex. eats, piercing). The name of the interaction type should be the name as it is listed in the original text, which is not always the name of the term it is mapped to. As long as the definition to the mapping is compatible with the ```interactionTypeName```, it is usable as a ```interactionTypeId```.
  * A **targetBodyPartName**  : The specific name of the target body part. The name of the body part should be the name as it is listed in the original text, which is not always the name of the term it is mapped to. As long as the definition to the mapping is compatible with the ```targetBodyPartName```, it is usable as a ```targetBodyPartId```.
  * A **targetBodyPartId**  : Identifer for the body part name.
  * A **targetTaxonId** [DWC:scientificNameID](http://rs.tdwg.org/dwc/terms/scientificNameID) : An identifier for the nomenclatural (not taxonomic) details of a scientific name.
  * A **targetTaxonName** [DWC:scientificName](http://rs.tdwg.org/dwc/terms/scientificName) : The lowest level taxonomic rank that can be determined.
  
### Included Resources


### Data Issues

Several issues and decisions arose while translating the observations from the literature into a series of single observations. Those are described here.

1. Invalid date strings according to TDWG and GloBI
1. Dynamic properties not in json format
1. Only records with ```DWC:associatedTaxa``` or ```DWC:dynamicProperties``` are indexed by GloBI
1. GloBI is using the EML to obtain attribution information. It is important to have this information filled out

### Summary
This dataset can serve as a example of how a person can format data for serving occurrence records using Darwin Core Archives from natural history collections to GloBI. It is not the only way to format data, but if this format is reused, GloBI can understand the structure of the shared data. These were entered by hand into a Symbiota portal that has both DWC:associatedTaxa and DWC:dynamicProperties available to use. 

![image of vampire-moth-globi](https://raw.githubusercontent.com/seltmann/vampire-moth-globi/master/network-bloodfeeding.png)

