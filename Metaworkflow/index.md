# Documentation du *Metaworkflow*

## Utilisation du workflow 

Le *Metaworkflow* utilise un classeur Excel nommé *Sequencing\_summary.xslx* situé sur la baie de stockage Panoramix.

## Le classeur Excel *Sequencing_Summary*

Le *Sequencing\_Summary*, est un classeur Excel contenant l'ensemble des metadonnées des runs de la plateforme. Il permet de réaliser différentes analyses en fonction des metadonnées entrées. 

**Lors du remplissage du classeur, évitez d'incorporer des espaces.**

### Remplissage du classeur

Les metadonnées sont entrées dans l'onglet *samples* du classeur. La section suivante va présenter l'ensemble des colonnes de cet onglet et expliquer comment les compléter. 

Voici une liste des colonnes et des valeurs qu'elles contiennent. Dans certains cas (précisé ci-dessous), il faut utiliser un menu déroulant pour compléter les cellules. Pour certaines colonnes, les choix possibles du menu seront expliqués.

1. A remplir pour tous les runs
* T : Index de la ligne pour pouvoir ordonner lies lignes
* sample\_name : Concatenation du Sample\_ID et du Sample\_Name.
* Sample\_Name : Nom de l'échantillon 
* Sample\_ID : ID TGML de l'échantillon
* Process **(menu déroulant)** : Indique si il faut traiter l'échantillon ou pas
    * *no* : Ne pas traiter l'échantillon
    * *yes* : Traifer l'échantillon
    * *done* : L'échantillon a déjà été traité
* Type **(menu déroulant)** : Type de librairies
    * RNA-seq
    * ChIP-seq
    * scRNA-seq
    * etc, ...
* Analysis\_type **(menu déroulant)** : Type d'analyse à réaliser
    * *Concatenation_QC* : Utilise les fichiers FASTQ produits par le séquenceur et produit un rapport MultiQC
    * *Concatenation_Quantification_QC* : Utilise les fichiers FASTQ produits par le séquenceur, produit une table de comptage des reads alignés sur un génome et un rapport MultiQC
    * *Demultiplexage_Concatenation_QC* : Utilise les images BCL produites par le séquenceur, produit des fichiers FASTQ et un rapport MultiQC
    * *Demultiplexage_Concatenation_Quantification_QC* : Utilise les images BCL produites par le séquenceur, produit des fichiers FASTQ une table de comptage des reads alignés sur un génome et un rapport MultiQC
* Specie **(menu déroulant)** : Nom complet de l'organisme
    * Homo\_sapiens
    * Mus\_musculus
    * etc, ...
* Se\_or\_Pe **(menu déroulant)** : Spécifie si les reads sont paired-end (pe) ou single-end (se)
* Origin **(menu déroulant)** : Spécifie le type de fichiers données en entrée au workflow. Les choix utilisés le plus souvent sont listés ci-dessous. 
    * bcl : Part de fichier BCL
    * bcl\_no\_mismatch : Part de fichier BCL, avec un demultiplexage sans autorisqer d'erreur dans les séquences d'indexes
    * NS500\_W10 : Part de fichiers FASTQ générés par le séquenceur
* Accession : Chemin vers les fichiers d'entrées (BCL ou FASTQ)
* Run : Numéro du run
* Customer **(menu déroulant)** : Nom du collaborateur/trice
* Sample\_Project : Nom du run 
* Kit\_index **(menu déroulant)** : Kit d'index utilisé pour préparer la librarie
* I7\_Index\_ID : Nom de l'index I7
* Index : Séquence de l'index I7
* Length\_1 : Longueur de la séquence de l'index I7 (calculé automatiquement)
* I5\_Index\_ID Nom de l'index I5
* Index2 : Séquence de l'index I5
* Length\_2 : Longeur de l'index I5 (calculé automatiquement)
* Description : Type de librairie (reprend le contenu de la case *Type* automatiquement)
* Date\_run : Date du run
* Reads : Taille des lectures (taille\_read1xtaille\_read2).
2. A remplir pour les expériences de CITE-seq de Cellplex ou de SingleCell RNA-seq
* Cellplex\_feature\_type
* CMO\_information
* Expected\_cell\_number
* ADT\_information
* HTO\_information
* Kit\_HTO
* Index\_10X
3. Ne pas remplir. Utilisé par d'ancienne version, mais conservé
* Quantile\_normalization
* Commentaire
* Merged\_or\_unmerged
* Exp
* Project
* Cell\_type
* Chip\_target
* Sample\_Plate : Position de la FlowCell
* Sample\_Well : Numéro de puit de l'échantillon
