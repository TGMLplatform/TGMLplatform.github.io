# Documentation du *Metaworkflow*

## Utilisation du workflow 

Le *Metaworkflow* utilise un classeur Excel nommé *Sequencing\_summary.xslx* situé sur la baie de stockage Panoramix.

## Le classeur Excel *Sequencing_Summary*

Le *Sequencing\_Summary*, est un classeur Excel contenant l'ensemble des metadonnées des runs de la plateforme. Il permet de réaliser différentes analyses en fonction des metadonnées entrées. 

**Lors du remplissage du classeur, évitez d'incorporer des espaces.**

### Remplissage du classeur

Les metadonnées sont entrées dans l'onglet *samples* du classeur. La section suivante va présenter l'ensemble des colonnes de cet onglet et expliquer comment les compléter. 

Voici une liste des colonnes et des valeurs qu'elles contiennent. Dans certains cas (précisé ci-dessous), il faut utiliser un menu déroulant pour compléter les cellules. Pour certaines colonnes, les choix possibles du menu seront expliqués.

* T : Index de la ligne pour pouvoir ordonner lies lignes
* sample_name : Concatenation du Sample_ID et du Sample_Name.
* Sample_Name : Nom de l'échantillon 
* Sample_ID : ID TGML de l'échantillon
* Process i**(menu déroulant)** : Indique si il faut traiter l'échantillon ou pas
    * *no* : Ne pas traiter l'échantillon
    * *yes* : Traifer l'échantillon
    * *done* : L'échantillon a déjà été traité
* Type **(menu déroulant)** : Type de librairies
    * RNA-seq
    * ChIP-seq
    * scRNA-seq
    * etc, ...
* Analysis_type (menu déroulant) : Type d'analyse à réaliser
    * *Concatenation_QC* : Utilise les fichiers FASTQ produits par le séquenceur et produit un rapport MultiQC
    * *Concatenation_Quantification_QC* : Utilise les fichiers FASTQ produits par le séquenceur, produit une table de comptage des reads alignés sur un génome et un rapport MultiQC
    * *Demultiplexage_Concatenation_QC* : Utilise les images BCL produites par le séquenceur, produit des fichiers FASTQ et un rapport MultiQC
    * *Demultiplexage_Concatenation_Quantification_QC* : Utilise les images BCL produites par le séquenceur, produit des fichiers FASTQ une table de comptage des reads alignés sur un génome et un rapport MultiQC

