## Description of the content in vampire-moth-globi

[![Build Status](https://travis-ci.org/ParasiteTracker/vampire-moth-dwca.svg)](https://travis-ci.org/ParasiteTracker/vampire-moth-dwca) [![GloBI](http://api.globalbioticinteractions.org/interaction.svg?accordingTo=globi:ParasiteTracker/vampire-moth-dwca)](http://globalbioticinteractions.org/?accordingTo=globi:ParasiteTracker/vampire-moth-dwca) 

[```Citation```](#Citation) / [```Interaction Types```](#interaction-types) / [```Data Definitions```](#data-definitions) / [```Included Resources```](#included-resources) /  [```Data Issues```](#data-issues) / [```Summary```](#summary)


### Description

vampire-moth-dwca is a repository for specimen occurrence data about vampire moths and their fruit-piercing relatives (Lepidoptera: Erebidae: *Calyptra* spp.). The feeding observations are from the specimens.

This GitHub repository was created from the contents of a Symbiota Darwin Core Archive file. Presently, only the occurrences.csv and eml.xml is indexed by GloBI.

***Workflow***

All of the fields in the occurrences.csv dataset were produced by entering data in presently available fields in Symbiota (September 28, 2018). A Darwin Core Archive was created using the Symbiota Darwin Core Archive publishing tool and the files from that publication are directly uploaded to the GitHub repository. 



![image of vampire-moth-dwca-symbiota](https://raw.githubusercontent.com/ParasiteTracker/vampire-moth-dwca/master/biotic-interaction-lifecycle.png)

Edit on Symbiota -> create Darwin Core Archive -> push to your GitHub repository for this dataset



***Entering Data in Symbiota***

Biotic interaction data can be entered through the ```DWC:dynamicProperties``` and ```DWC:associatedTaxa``` fields. 

[```DWC:associatedTaxa```](http://rs.tdwg.org/dwc/terms/associatedTaxa) is "A list (concatenated and separated) of identifiers or names of taxa and their associations with the Occurrence." The TDWG recommended best practice is to "separate the values with a vertical bar (' | '), and to separate the relationship from the taxon with a colon (':'). Examples: "host: Quercus alba", "parasitoid of:Cyclocephala signaticollis | predator of Apis mellifera".

The interactions are not explicitly defined, meaning that the word "host" or "eats" could have different meanings in different datasets because a definition of the word is not included. This is where the ```DWC:dynamicProperties``` becomes useful.

[```DWC:dynamicProperties```](http://rs.tdwg.org/dwc/terms/dynamicProperties) is a "list of additional measurements, facts, characteristics, or assertions about the record. Meant to provide a mechanism for structured content", and that structured content for biotic interactions could include the explict identifiers for the details of the interaction.

![image of vampire-moth-dwca-symbiota](https://raw.githubusercontent.com/ParasiteTracker/vampire-moth-dwca/master/Symbiota-screen.png)

Key:value formatted data entered into ```DWC:dynamicProperties``` in the above examples are: 

	targetTaxonName: Homo sapiens; 
	targetTaxonId: https://www.gbif.org/species/2436436; 
	interactionTypeName: eats; 
	interactionTypeId: http://purl.obolibrary.org/obo/RO_0002470; 
	targetBodyPartName: blood; 
	targetBodyPartId: http://purl.obolibrary.org/obo/NCIT_C12434



Key:value formatted data entered into ```DWC:associatedTaxa``` in the above examples are: 

	eats: Homo sapiens


### Citation

Jennifer Zaspel. 2018. Biotic species interactions manually extracted from occurrence records.


### Interaction Types

The kinds of biotic species interactions in this dataset are mapped to terms in the Relations Ontology (RO). Classes to describe interactions in the RO (and other ontologies) can be searched through the [Ontobee](http://www.ontobee.org/ontology/RO?iri=http://purl.obolibrary.org/obo/RO_0002437).

interactionTypeName | interactionTypeId
--- | --- |
eats | http://purl.obolibrary.org/obo/RO_0002470
 
### Data Definitions

The definitions of the ***keys*** from the key:value pairs that are used in ```DWC:dynamicProperties``` field in the occurrences.csv dataset are described in this document. This is not an exaustive list of classes to describe the interactions, only the ones that were used in this dataset.

  * A **sourceTaxonId** [DWC:scientificNameID](http://rs.tdwg.org/dwc/terms/scientificNameID) : An identifier for the nomenclatural (not taxonomic) details of a scientific name.
  * A **sourceTaxonName** [DWC:scientificName](http://rs.tdwg.org/dwc/terms/scientificName) : The lowest level taxonomic rank that can be determined.
  * A **interactionTypeId** : Identifier for the interaction type.
  * A **interactionTypeName** : A interaction type (ex. eats, piercing). The name of the interaction type should be the name as it is listed in the original text, which is not always the name of the term it is mapped to. As long as the definition to the mapping is compatible with the ```interactionTypeName```, it is usable as a ```interactionTypeId```.
  * A **targetBodyPartName**  : The specific name of the target body part. The name of the body part should be the name as it is listed in the original text, which is not always the name of the term it is mapped to. As long as the definition to the mapping is compatible with the ```targetBodyPartName```, it is usable as a ```targetBodyPartId```.
  * A **targetBodyPartId**  : Identifer for the body part name.
  * A **targetTaxonId** [DWC:scientificNameID](http://rs.tdwg.org/dwc/terms/scientificNameID) : An identifier for the nomenclatural (not taxonomic) details of a scientific name.
  * A **targetTaxonName** [DWC:scientificName](http://rs.tdwg.org/dwc/terms/scientificName) : The lowest level taxonomic rank that can be determined.
  
### Included Resources
Darwin Core Archive created by the [UC Santa Barbara Symbiota Portal](http://symbiota.ccber.ucsb.edu/) 

### Data Issues

Several issues and decisions arose while translating the observations from the literature into a series of single observations. These issues are detailed in the [GitHub issues](https://github.com/ParasiteTracker/vampire-moth-dwca/issues) for this project and also described here.

1. Invalid date strings according to TDWG and GloBI. The date strings like ```2008-00-20``` are entered in DWC:eventDate. TDWG suggests that dates without months or days are entered without the zeros (ex. 1906-06). In this specific case, where the month is not known, the [DWC:eventDate](http://rs.tdwg.org/dwc/terms/eventDate) could include only the year (ex. 2008) and [DWC:startDayOFYear](http://rs.tdwg.org/dwc/terms/startDayOfYear) be entered for the day of year.
1. Dynamic properties not in JSON format. It is recommended best practice for [DWC:dynamicProperties](http://rs.tdwg.org/dwc/terms/dynamicProperties) to be in [JSON format](https://www.w3schools.com/Js/js_json_syntax.asp). The decision was made to include as key:value pairs only because the information was entered by a human into the field, rather than coming from an application. This creates a strong likelihood that errors in the JSON formatting are introduced. Validation checks in Symbiota could help with formatting this field.
1. Only records with ```DWC:associatedTaxa``` or ```DWC:dynamicProperties``` are indexed by GloBI. GloBI does not store all of the records in occurrence dataset.
1. GloBI is using the EML to obtain attribution information. It is important to have this information filled out, so that attribuiton can be correctly linked to the data records when they are indexed in GloBI, and it will act as the reference for the interactions. Ideally, individual occurrence records would have a resolving link back to the reference, which would also serve as a way of linking the interactions on GloBI with the rest of the information about the occurrence.
1. Interaction data coming from multiple record providers could create duplicate interaction records in GloBI with different citations.
1. There is no validation of the information entered in these fields, which increases the change of human error. Improved validation around data format, controlled vocabularies and taxon name verification would improve the data quality.

### Summary
This dataset can serve as a example of how data can be formatted directly in a Symbiota portal and share those interactions through GloBI. Only the presently available fields and resources are used in this example and it is the first example of a Darwin Core Archive formatted dataset from a natural history collections to serve on GloBI. It is not the only way to format data, but if this format is reused, GloBI can understand the structure of the shared data. These were entered by hand into a Symbiota portal that has both ```DWC:associatedTaxa``` and ```DWC:dynamicProperties``` available to use. 

This example is valuable because it demonstrates that biotic interaction data contained within Darwin Core Archives can be presently shared and integrated into other interaction data through GloBI as long as some effort is put into formatting those data. The data can be entered according to TDWG standards in the ```DWC:associatedTaxa``` field, and as key:value pairs in ```DWC:dynamicProperties``` by anyone transcribing data into a Symbitota portal and it does not require additional special services or modifications to the software to perform this task successfully.


