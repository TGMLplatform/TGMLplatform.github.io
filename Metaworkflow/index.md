# Documentation du *Metaworkflow*

## Utilisation du workflow 

Le *Metaworkflow* utilise un classeur Excel nommé *Sequencing\_summary.xslx* situé sur la baie de stockage Panoramix.

## Le classeur Excel *Sequencing_Summary*

Le *Sequencing\_Summary*, est un classeur Excel contenant l'ensemble des metadonnées des runs de la plateforme. Il permet de réaliser différentes analyses en fonction des metadonnées entrées. 

**Lors du remplissage du classeur, évitez d'incorporer des espaces.**

### Remplissage du classeur

Les metadonnées sont entrée dans l'onglet *samples* du classeur. La section suivante va présenter l'ensemble des colonnes de cet onglet et expliquer comment les compléter.

* T : Index de la ligne pour pouvoir ordonner lies lignes
* sample_name : Concatenation du Sample_ID et du Sample_Name.
* Sample_Name : Nom de l'échantillon 
* Sample_ID : ID TGML de l'échantillon
* Process : Indique si il faut traiter l'échantillon ou pas
* Type : Type de librairies
* Analysis_type : Type d'analyse à réaliser
    * Concatenation_QC
    * Concatenation_Quantification_QC
    * Demultiplexage_Concatenation_QC
    * Demultiplexage_Concatenation_Quantification_QC
