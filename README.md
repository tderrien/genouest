# genouest
Data organization on genouest bioifinormatic pltaform and (hopefully) useful tools

Our private storage is located here `/grous/dog/`.

Then useful resources could be accessed here :

```
Dog genome sequence :          /groups/dog/data/canFam3/sequence/softmasked/Canis_familiaris.CanFam3.1.72.dna_sm.toplevel.fa
Dog genome annotations :
	- version Ensembl (v94) :     /groups/dog/data/canFam3/annotation/Ensembl94/Canis_familiaris.CanFam3.1.94.gtf
	- version 3.2 (Wucher, 2017): /groups/dog/data/canFam3/annotation/canfam3.2/canfam3.2.gtf
- Polymorphisms:
	- SNPs  DBVDC (Tosso/Vidhya):	/groups/dog/data/canFam3/variation/dogs.648.vars.flt.ann.vcf.gz
	- SNPs de DB_SNPs (v151, 5M):	/groups/dog/data/canFam3/variation/Ensembl/canis_familiaris_v94.vcf.gz
	- SVs de DGVa (252k):					/groups/dog/data/canFam3/variation/Ensembl/canis_familiaris_structural_variations.vcf_v94.gz
- Transposable Elemts, rep:     /groups/dog/data/canFam3/repeats/RM01032017.gtf
- Sequence Gaps 						   /groups/dog/data/canFam3/gap/gap_26Feb2013.canfam3.wochr.bed
- ...
```

Then data related to (dog) NGS project are in `/groups/dog/data/canFam3/NGS/` and the structure is as followed:    

```
=> PROJECT_NAME						: e.g. Melanoma ou Epilepsy
	=> DNA | RNA						: biological material 
		 => Sequencing_type 		: *new* : could be WGS (Whole Genome Sequencing); EXOME ; Targeted_Sequencing; ou ./ (si q’un seul type de séquençage)
			=> BAM					: BAM Files
			=> FASTQ				: FASTQ Files
			=> RESULTS				: Results linked to analysis on the project
				=> version d’annotation	: répertoire qui liste la version d’annotation utilisée pour l’analyse e.g:  on_canfam3 (Ensembl) ou on_canfam3.2
```

For instance, the data structure is as followed (July 2020):
```
$ tree -L 3 -d ./
|-- dog10k
|   `-- DNA
|       |-- BAM
|       |-- FASTQ
|       |-- RESULTS
|       `-- scripts
|-- Dog_Reannotation
|   |-- DNA
|   `-- RNA
|       |-- BAM
|       |-- FASTQ
|       `-- RESULTS
```
