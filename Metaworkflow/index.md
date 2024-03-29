# Utilisation du workflow 

Le *Metaworkflow* utilise un classeur Excel nommé *Sequencing\_summary.xslx* situé sur la baie de stockage Panoramix.

# Le classeur Excel *Sequencing_Summary*

Le *Sequencing\_Summary*, est un classeur Excel contenant l'ensemble des metadonnées des runs de la plateforme. Il permet de réaliser différentes analyses en fonction des metadonnées entrées. 

**Lors du remplissage du classeur, NE PAS METTRE d'espaces.**

## Onglet Samples 

Les metadonnées sont entrées dans cet onglet du classeur. La section suivante va présenter l'ensemble des colonnes de cet onglet et expliquer comment les compléter. 

Pour savoir quelles colonnes remplir pour les différentes analyses réalisables, se référer à l'onglet "Examples" du *Sequencing_Summary*.

Voici une liste des colonnes et des valeurs qu'elles contiennent. Dans certains cas (précisé ci-dessous), il faut utiliser un menu déroulant pour compléter les cellules.

* **T** : Index de la ligne pour pouvoir ordonner lies lignes
* **sample\_name** : Concatenation (automatique) du Sample\_ID et du Sample\_Name
* **Sample\_Name** : Nom de l'échantillon 
* **Sample\_ID** : ID TGML de l'échantillon
* **Process** *(menu déroulant)* : Indique si l'échantillon doit être traité
    * *no* : Ne pas traiter l'échantillon
    * *yes* : Traiter l'échantillon
    * *done* : L'échantillon a déjà été traité
* **Type** *(menu déroulant)* : Type de librairies
    * *RNA-seq*
    * *ChIP-seq*
    * *scRNA-seq*
    * ...
* **Analysis\_type** *(menu déroulant)* : Type d'analyse à réaliser
    * *Concatenation\_QC* : Utilise les fichiers FASTQ produits par le séquenceur, les concatène et produit un rapport MultiQC
    * *Demultiplexage\_Concatenation\_QC* : Utilise les fichiers BCL produites par le séquenceur, produit des fichiers FASTQ, les concatène et produit un rapport MultiQC
    * *Concatenation\_Quantification\_QC* : Utilise les fichiers FASTQ produits par le séquenceur, les concatènes, produit une table de comptage des reads alignés sur un génome et un rapport MultiQC
    * *Demultiplexage\_Concatenation\_Quantification\_QC* : Utilise les fichiers BCL produites par le séquenceur, produit des fichiers FASTQ, les concatènes, produit une table de comptage des reads alignés sur un génome et un rapport MultiQC
* **Specie** *(menu déroulant)* : Nom complet de l'organisme
    * *Homo\_sapiens*
    * *Mus\_musculus*
    * ...
* **Se\_or\_Pe** *(menu déroulant)* : Spécifie si les reads sont paired-end (pe) ou single-end (se)
* **Origin** *(menu déroulant)* : Spécifie le type de fichiers d'entrée.
    * Organiser par ordre d'utilisation
    * *bcl* : Part de fichier BCL. Demultipelxage avec bcl2fastq
    * *bcl\_no\_mismatch* : Part de fichier BCL, avec un demultiplexage sans autoriser d'erreur dans les séquences d'indexes. Demultipelxage avec bcl2fastq
    * *bcl\_NS2000\_p1p2* : Part des fichier BCL provenant du NextSeq 2000 avec une *Flowcell* P1 ou P2 (1 lane). Demultipelxage avec bcl-convert
    * *bcl\_NS2000\_p3* : Part des fichier BCL provenant du NextSeq 2000 avec une *Flowcell* P3 (2 lanes). Demultipelxage avec bcl-convert
    * *NS500\_W10* : Part de fichiers FASTQ générés par le NextSeq500
    * *NextSeq500* : Part de fichiers FASTQ générés par le NextSeq500 avant la mise à jour de Septembre 2021
    * *NextSeq2000* : Part de fichiers FASTQ générés par le NextSeq2000
    * *sra* : Part d'un numéro d'archive SRA (Ne peux réaliser que la récupération des fichiers FASTQ)
* **Accession** : Chemin vers les fichiers d'entrée
* **Run** : Numéro du run
* **Customer** *(menu déroulant)* : Nom du collaborateur/trice
* **Run\_Name** : Nom du run 
* **Kit\_index** *(menu déroulant)* : Kit d'index utilisé pour préparer la librarie
* **I7\_Index\_ID** : Nom de l'index I7
* **Index** : Séquence de l'index I7
* **Length\_1** : Longueur de la séquence de l'index I7 (calculé automatiquement)
* **I5\_Index\_ID** : Nom de l'index I5
* **Index2** : Séquence de l'index I5
* **Length\_2** : Longeur de l'index I5 (calculé automatiquement)
* **Description** : Type de librairie (reprend automatiquement le contenu de la case *Type*)
* **Date\_run** : Date du run
* **Reads** : Taille des lectures ("taille\_read1"x"taille\_read2").
* **Cellplex\_feature\_type** *(menu déroulant)* : Type de librairie pour le Cellplex
    * *gene\_Expression* : Librairie de Gene Expression (ARN messager)
    * *Multiplexing\_Capture* : Librairie de CMO
* **CMO\_information** : Liste les CMO utilisés avec leur nom (Sample1,CMO1;Sample2,CMO2;etc,...). **Séparer le nom de l'échantillon et le CMO correspondant par une virgule. Entre deux échantillons différents, mettre un point-virgule**
* **Expected\_cell\_number** : Nombre de cellules attendues pour le Cellplex
* **Index\_10X** : Indiquer *"yes"* si les indexes 10X ont été utilisé, sinon, remplir les séquences d'indexes dans les colonnes *Index* et *Index2*

**Ne pas remplir. Utilisé par d'ancienne version, mais conservé**
* Quantile\_normalization
* Commentaire
* Merged\_or\_unmerged
* Exp
* Project
* Cell\_type
* Chip\_target
* Sample\_Plate
* Sample\_Well 
* ADT\_information
* HTO\_information
* Kit\_HTO

## Onglet data\_validation\_lists

L'onglet data\_validation\_lists contient l'ensemble des valeurs utilisées pour les menus déroulants.

### Ajouter une valeur dans les menus déroulants

Pour ajouter une valeur dans un menu déroulant

* Dans l'onglet *data_validation_lists*, ajouter la valeur dans la colonne d'intêret
* Dans l'onglet *samples*, sélectionner la colonne d'intêret sauf le nom de la colonne. Pour cela :
    * Sélectionner le nom de la colonne
    * Avec le clavier : 
        * Appuyer sur la flèche "bas"
        * Enfoncer ctrl + shift
        * Appuyer sur la flèche "bas" jusqu'à atteindre la fin du document
        * Une fois fait, l'ensemble de la colonne sera selectionnée
* Dans l'onglet supérieur d'Excel, aller dans *Données* -> Validation des données -> Si une fenêtre demande si vous voulez modifier les données sélectionner "Oui" -> Autoriser = Liste -> Source = Sélectionner les valeurs dans l'onglet *data_validation_lists*.

## Onglet examples

L'onglet *examples* propose des exemples des remplissages de l'onglet *samples*

* Demultiplexage 
* Demultiplexage avec analyse de données
* Analyses de données à partir des FASTQ générés par le séquenceur
* Analyses de données de single-cell RNA-seq
* Analyses de données de single-cell RNA-seq multiplexé

## Onglet genome\_version

L'onglet *genome_version* contient la correspondance entre le nom d'organisme et la version du génome utilisé pour l'analyse. **Modifier les valeurs ne changera pas les version de génome utilisée!!!**
