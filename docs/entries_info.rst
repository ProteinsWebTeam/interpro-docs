########################################
InterPro Entries : essential information
########################################

.. :ref:memberdb_page browse.html#memberdb-page
.. :ref:entry_page browse.html#entry-page
.. :ref:protein_page browse.html#protein-page
.. :ref:structure_page browse.html#structure-page
.. :ref:taxonomy_page browse.html#taxonomy-page
.. :ref:set_page browse.html#set-page
.. :ref:proteome_page browse.html#proteome-page

An InterPro entry is created for each protein family, domain or important site signature that is integrated into 
InterPro from one or more of it's :doc:`13 member databases </databases>`. Where signatures from two or more member databases describe 
the same family, domain or site, the member database signatures are brought together under one InterPro entry.

An InterPro entry provides a written description of the family, domain or site and lists the contributing member 
database signatures. Each entry has a name, a unique InterPro identifier and an :ref:`entry type <entry_types>`. `Go terms <http://geneontology.org/>`_ associated 
with the entry are also displayed. For each InterPro entry further information is provided showing, for example, 
the proteins, structures and pathways matching this entry along with taxonomic distribution. This information can 
be easily viewed by :doc:`/browse`. 

.. _entry_types:

********************
InterPro entry types 
********************

InterPro entries are created for protein families, domains, sites, repeats and homologous superfamilies, defined as follows:

|F| **Family** - a group of proteins that share a common evolutionary origin reflected by their related functions, sequence homology or 
similarities in their structure.

|D| **Domain** - a distinct functional, structural or sequence unit often found associated with other types of domains.

|S| **Site** - a short sequence containing one or more conserved residues, including: active sites, binding sites, 
conserved sites and sites of post-translational modification. 

|R| **Repeat** - A short sequence (usually <50 amino acids) typically repeated many times within a protein.

|H| **Homologous Superfamily** - a group of proteins that share a common evolutionary origin, reflected by similarity in 
their structure, even if sequence similarity is low. This entry type contains signatures from the CATH-Gene3D and 
SUPERFAMILY member databases exclusively.

|U| **Unintegrated** - member database signatures that might not yet be curated in InterPro, or might not reach InterPro's 
criteria for integration, but may still provide useful information.

**************************
Other entry and page types
**************************
In addition to the main :ref:`InterPro Entries <entry_page>`, which bring together protein signatures from the member databases consortium, 
InterPro also provides entry pages for the individual :ref:`member database signatures <memberdb_page>` and for :ref:`proteins <protein_page>`, 
:ref:`structures <structure_page>`, :ref:`taxons <taxonomy_page>`, :ref:`proteomes <proteome_page>` and :ref:`sets/clans <set_page>` integrated or used by 
InterPro. These entry pages also have further information available that can be viewed by :doc:`/browse`. More information is available 
in the corresponding `train online section <https://www.ebi.ac.uk/training/online/course/interpro-functional-and-structural-analysis-protei/what-interpro-entry>`_.

.. _relationship:

*******************
Entry relationships
*******************
InterPro entries that represent a subset of proteins from another InterPro entry are identified as "children" of the 
"parent" entry. InterPro displays these connections between entries in the "Family Relationships" or "Domain Relationships" 
sections. Entries at the top of these hierarchies describe broad families or domains that share higher level structure and/or 
function, while those entries at the bottom describe more specific functional subfamilies or structural/functional subclasses 
of domains. More information is available in the corresponding `train online section <https://www.ebi.ac.uk/training/online/course/interpro-functional-and-structural-analysis-protei/relationships-between-interpro-entries/>`_.

.. _overlapping:

*******************
Overlapping entries
*******************
Relationships between homologous superfamilies and either family or domain entries are generated automatically using the 
Jaccard and containment indexes. These relationships are shown in the Overlapping homologous superfamilies/Overlapping 
entries section on the InterPro entry pages. More information is available in the corresponding `train online section <https://www.ebi.ac.uk/training/online/course/genome3d-annotations-interpro/homologous-superfamily-entry-type-in-interpro/what-are-overlapping-entries/>`_.

**********
Ontologies
**********

InterPro uses several standards and ontologies:

- the `NCBI Taxonomy <//www.ncbi.nlm.nih.gov/taxonomy>`_  for taxa: the NCBI assigns unique taxonomic identifiers for all organisms (taxa) that are represented in UniProtKB. As these taxonomic identifiers are stable, InterPro uses them to let users search the resource by organism;
- the `Gene Ontology (GO) <//www.geneontology.org>`_ for functions, processes, cellular components: InterPro2Go (https://doi.org/10.1093/database/bar068) is a manually created mapping between InterPro entries and GO terms. Where an InterPro entry hits a set of functionally similar proteins, GO terms describing the conserved function or location are associated with the InterPro entry.
- the Nomenclature Committee of the `International Union of Biochemistry and Molecular Biology <//www.iubmb.org/>`_ (NC-IUBMB) via `IntEnz <https://www.ebi.ac.uk/intenz/>`_: Enzyme Commission (EC) numbers describe enzyme-catalyzed reactions and are available in UniProtKB, e.g. `P17050 <https://www.uniprot.org/uniprotkb/P17050/entry>`_. Where an InterPro entry hits reviewed/Swiss-Prot proteins annotated with EC numbers, the EC numbers are associated to the InterPro entry.
- `Reactome <//reactome.org>`_ and `MetaCyc <//metacyc.org/>`_ for pathways. Where an InterPro entry hits a reviewed/Swiss-Prot protein involved in a pathway described by Reactome, the pathway is associated to the InterPro entry. As reactions in MetaCyc include EC numbers, InterPro uses EC numbers assigned to an entry (as described above) and to a metabolic pathway to link InterPro entries and MetaCyc pathways.


.. |F| image:: images/entry_types/family.png
  :alt: Family entry type icon
  :width: 15pt

.. |D| image:: images/entry_types/domain.png
  :alt: Domain entry type icon
  :width: 15pt

.. |H| image:: images/entry_types/homologous.png
  :alt: Homologous Superfamily entry type icon
  :width: 15pt

.. |R| image:: images/entry_types/repeat.png
  :alt: Repeat entry type icon
  :width: 15pt

.. |S| image:: images/entry_types/site.png
  :alt: Site type icon
  :width: 15pt

.. |U| image:: images/entry_types/unintegrated.png
  :alt: Unintegrated entry type icon
  :width: 15pt
