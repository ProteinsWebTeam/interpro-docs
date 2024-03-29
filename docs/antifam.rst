#############
About AntiFam
#############

AntiFam is a resource of profile-HMMs designed to identify spurious
protein predictions. AntiFam profile-HMMs come from two sources:

1. A number of spurious Pfam families have been built in the past. These were based on erronous gene predictions. These protein families have been deleted from Pfam, but new proteins may be predicted. More recently proteins identified as Shadow ORFs and their homologues have been used to create new AntiFam families.

2. Profile-HMMs have been created from translations of commonly occuring non-coding RNAs such as tRNAs. 

This collection of profile-HMM models is designed to be used as a
quality control step for the UniProt sequence database as well as
metagenomic projects.

Note that AntiFam models may hit proteins which are extended at the
N-terminus due to the wrong initiator methionine being selected. Proteins
which have known Pfam domains are unlikely to be spurious proteins.

+----------+-----------+
| Release  | # Entries |
+==========+===========+
|1.0       | 8         |
+----------+-----------+
|1.1       | 23        |
+----------+-----------+
|2.0       | 49        |
+----------+-----------+
|3.0       | 54        |
+----------+-----------+
|4.0       | 67        |
+----------+-----------+
|5.0       | 72        |
+----------+-----------+
|6.0       | 250       |
+----------+-----------+
|7.0       | 263       |
+----------+-----------+

AntiFam is freely available under the Creative commons Zero (CC0) licence.
http://creativecommons.org/publicdomain/zero/1.0/


How to use AntiFam
==================

AntiFam is composed of a collection of alignments found in the file AntiFam.seed.
Using the HMMER3 software a library of profile-HMMs was built. This library is
found in the file AntiFam.hmm.

To use the hmm library you must first make index files with the following command

  ``hmmpress AntiFam.hmm``

To search AntiFam against a set of sequences you run the following command

  ``hmmsearch --cut_ga AntiFam.hmm yourseq.fasta``

Any reported matches are very likely to be spurious gene predictions.


Superkingdom-specific sets
==========================

AntiFam includes superkindom-specific sets of HMMs:

- AntiFam_Eukaryota.hmm
- AntiFam_Bacteria.hmm
- AntiFam_Archaea.hmm
- AntiFam_Virus.hmm

These contain HMMs that we have found to identify spurious proteins in each of
the superkingdoms, unidentified includes unclassified organisms. One HMM may
identify spurious proteins from multiple superkingdoms, and therefore may be 
present in more than one of these superkingdom-specific sets.


Acknowledgements
================

We would like to thank Wolfram Hoeps who made AntiFam release 5.0 and Syed
Muktadir Al Sium who generated the large number of new families added to release 
6.0.


How to cite AntiFam
===================

If you use AntiFam in your work please cite the following paper:

Ruth Y Eberhardt, Dan Haft, Marco Punta, Maria Martin, Claire O'Donovan, 
Alex Bateman. (2012) AntiFam: A tool to help identify spurious ORFs in protein
annotation. Database:bas003. PMID:`22434837 <https://europepmc.org/article/MED/22434837>`_.