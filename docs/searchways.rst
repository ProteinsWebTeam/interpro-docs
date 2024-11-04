###################################
How to search the InterPro website?
###################################

.. :ref:Search homepage.html#search
.. :ref:navigation_menu banner.html#navigation-menu
.. :ref:navigation_banner banner.html#navigation-banner
.. :ref:memberdb_page browse.html#memberdb-page
.. :ref:entry_page browse.html#entry-page
.. :ref:protein_page browse.html#protein-page
.. :ref:structure_page browse.html#structure-page
.. :ref:taxonomy_page browse.html#taxonomy-page
.. :ref:entry_types entries_info.html#entry-types

A search can be performed on the :doc:`/homepage` using the :ref:`Search` component, by clicking on the Search tab in the 
:ref:`navigation menu <navigation_menu>`, 
or by clicking on the magnifying glass in the :ref:`navigation banner <navigation_banner>`. 
There are five different types of search available in InterPro:

- :ref:`quick_search`
- :ref:`sequence_search`
- :ref:`text_search`
- :ref:`domain_arch_search`
- :ref:`browse_feature`

.. _quick_search:

************
Quick search
************

.. figure:: images/banner/navigation_search_box.png
  :alt: Quick search component
  :width: 200px
  :align: left

The magnifying glass in the navigation banner allows a quick search for a specified keyword. 
A search can be triggered by entering some text and pressing the enter/return key or clicking 
the magnifying glass. If the keyword is text, the results will be displayed as described in 
the :ref:`text_search`. If the keyword entered is an accession, it automatically redirects to the 
corresponding :doc:`InterPro page </browse>` under the **Browse** tab in the :ref:`navigation menu <navigation_menu>`. 

.. _sequence_search:

***************
Sequence search
***************

A sequence or a batch of sequences of nucleotides or amino acids can be submitted in FASTA format in the 
dedicated text area or by uploading a fasta file. The **Advanced options** allows users to select the 
sequence type (protein -amino acids-, or RNA/DNA -nucleotides-), the InterPro member databases and other 
sequence features of interest 
to search against (by default they are all selected). The sequence search is performed using the 
:doc:`InterProScan software </interproscan>`. While the sequence search is running, the user can continue 
to navigate through the website, other browser tabs or applications and will get a pop-up notification 
when the job has been completed (this requires the browser notifications to be allowed).

.. figure:: images/search/seq.png
  :alt: Sequence search component
  :width: 800px


.. _sequence_search_results:

Sequence search results
=======================
Results of a protein sequence search are available under the **Results** tab in the navigation menu under 
**Your InterProScan Searches** section. This page displays the sequence searches that have been
performed in the last seven days, with the most recent one being displayed at the top. The *Status* 
column gives an indication of whether or not the search has completed (green tick symbol / searching), if the 
search has been saved locally (the results will still be available even after the seven days limit set up on 
InterPro servers), or if the results have been imported (file symbol). Searches can be deleted or saved locally 
by clicking on the bin or file icon in the *Action* column, respectively.

Previously ran searches can be imported either by typing the job ID in the **Import** text box, for searches 
performed in the last seven days on our servers, or by uploading an :doc:`InterProScan </interproscan>` output 
file in JSON format, the job is added to the table. If the second option is chosen and InterProScan was 
run using nucleotide sequences, a job result is created for each Open Reading Frame (ORF) and ORFs from the same 
nucleotide sequence are grouped accordingly.
This import feature can be used by users requiring to have InterProScan graphic output formats for publications 
and other uses.

.. figure:: images/search/interpro_rtd_list_jobs.png
  :alt: Sequence search list
  :width: 800px

  Summary of sequence searches.

Clicking on the job ID or on the text in the *Results* column opens a page summarising the search, including the 
sequence type, number of sequences, status and expiry date (see figure below).
When a search has been run using a previous version of InterProScan, it can be re-run using the latest 
version of the software by clicking on the **Resubmit All** button. If the search has been run in the last seven 
days, the results can be saved in the browser to be able to access them once the seven days limit has been reached 
by clicking on the **Save results in Browser** button.
The results can be downloaded by clicking on the **Download** button. If the search has been run in the last seven days
the results can be downloaded in TSV, JSON, XML and GFF formats, thereafter, if the search has been saved locally, 
the results are only available in JSON format.

.. figure:: images/search/interpro_rtd_seq_list.png
  :alt: InterProScan search results (Sequences) page
  :width: 800px

  InterProScan search results (Sequences) page.

All the submitted sequences are listed in a table. Clicking on the name in the **Sequence** column allows to 
access the results summarised in a protein sequence viewer (see figure below).

.. figure:: images/search/sequence_search_result.png
  :alt: Sequence search viewer
  :width: 800px

  Example of protein sequence viewer as displayed on the InterProScan search results page.

.. Example protein used: P02936

On the results page, some general information about the submitted sequence is provided, 
followed by the predicted InterPro protein family membership when available ([1] in the figure above).

The sequence submitted is shown in its full length at the top of the protein sequence viewer (grey bar) [2]. 
InterPro entries and signatures matches are displayed in categories: Families, Domains, Conserved residues, Unintegrated 
and Other features.
Each coloured bar represents a protein family, a domain or important site that has been 
matched to part or all the length of the submitted protein sequence. 

On the right-hand side of the match, if a signature has been integrated in an InterPro entry, the later is shown [3a, 5a].
Directly below the InterPro entry, the member database signatures that contributed to that InterPro entry are shown [3b, 5b]. 

In the Domains category, representative domains are displayed at the top [4].

In the example above, seven InterPro entries (2 families, 3 domains, 2 homologous superfamilies entries) have been found matching the 
submitted sequence. The first InterPro entry is for a protein family [3a], containing two member database 
signatures, in this case from Prosite (PR01022) and HAMAP (MF_00842)[3b], the other family contains 1 PANTHER signature. 
The following 2 InterPro matches are Homologous superfamilies, containing 1 and two member database signatures, respectively.
The last 3 InterPro matches are domains. The first two InterPro domains contain one member database signature each. 
The last InterPro domain entry [5a] contains signatures from 3 member databases (Pfam, CDD and Prosite) [5b] which all represent the 
same domain. 

Member database signatures not integrated in InterPro entries are displayed under the **Unintegrated** category.

CDD also provides per residue annotations which are displayed in the **Conserved residues** category [6].
Looking at the **Other features** category, we also learn that the protein has a signal peptide at its N-terminal end.


Additionally to the InterPro matches, information about the GO terms associated to the InterPro entries and PANTHER signatures matching the protein 
are displayed below the sequence viewer when available. The GO terms are assigned manually to InterPro entries using on 
the `Gene Ontology <http://geneontology.org/>`_ and reflect the Biological process, Molecular function or Cellular location the protein may have.

.. _text_search:

***********
Text search
***********

The text search is available by selecting the “By Text” section under the **Search** tab in the website menu. 
The text search allows to search the following information in the database:

- Name or keyword (e.g. `Afadin <https://www.ebi.ac.uk/interpro/search/text/Afadin/?page=1#table>`_)
- InterPro accession (e.g. `IPR000562 <https://www.ebi.ac.uk/interpro/search/text/IPR000562/?page=1#table>`_)
- Member database signature accession (e.g. `PF00040 <https://www.ebi.ac.uk/interpro/search/text/PF00040/?page=1#table>`_)
- Protein accession (e.g. `P04937 <https://www.ebi.ac.uk/interpro/search/text/P04937/?page=1#table>`_) or identifier/short name (e.g. `FINC_RAT <https://www.ebi.ac.uk/interpro/search/text/FINC_RAT/?page=1#table>`_)
- PDB structure (e.g. `6AR9 <https://www.ebi.ac.uk/interpro/search/text/6AR9/?page=1#table>`_)
- Gene name (e.g. `BRCA2 <https://www.ebi.ac.uk/interpro/search/text/BRCA2/?page=1#table>`_)
- GO terms (e.g. `GO:0005911 <https://www.ebi.ac.uk/interpro/search/text/GO:0005911/?page=1#table>`_)
- Proteome accession (e.g. `UP000000304 <https://www.ebi.ac.uk/interpro/search/text/UP000000304/?page=1#table>`_)
- Taxonomy accession (e.g. `7240 <https://www.ebi.ac.uk/interpro/search/text/7240/?page=1#table>`_)
- Set/Clan accession (e.g. `CL0451 <https://www.ebi.ac.uk/interpro/search/text/CL0451/?page=1#table>`_)

Entering a **name**, or **keywords**, retrieves a list of all the InterPro entries and InterPro member database 
signatures that contain these searched words in their title or description. By default the term searched is highlighted 
in the results list and the description is shortened, clicking on the |toggle| symbol located on the left hand side of 
the **Export** button removes the highlight and shows the full description text. The setting is saved and also applied 
to other text searches throughout the website.

Entering an **accession number** gives an exact match and a quick 
access to the corresponding InterPro page. It also displays the list of the InterPro entries and any member 
database signatures linked to that accession number/identifier.

Selecting the accession number or name of any entry in the list of entries opens the corresponding InterPro page 
(e.g. :ref:`member database signature <memberdb_page>`, :ref:`InterPro entry <entry_page>`). An overview of the entry 
is provided and tabs on the left hand-side menu allow specific information for the entry to be viewed, for example the species 
in which a protein has been found, or structures matching an entry. More information on the
:doc:`browsing an InterPro page </browse>` section.

.. _domain_arch_search:

**************************
Domain architecture search
**************************

.. figure:: images/search/ida.png
  :alt: Domain Architecture search
  :width: 800px

This search option allows the retrieval of protein sequences that contain specific Pfam/InterPro domains 
in a particular arrangement referred to as a "domain architecture". For example, protein sequences 
containing both a SH2 domain and SH3 domain can be retrieved. Domains that the proteins should or 
should not contain can be included or excluded from the domain architecture respectively.  
Selecting "**Order of domain matters**" offers the possibility to arrange the domains in a particular order. 
Selecting "**Exact match**" performs the search to find proteins containing the selected domains only 
(no extra domain in the proteins). Domains can be selected by entering a domain name, a Pfam accession, 
or an InterPro accession if a Pfam entry is integrated in it.

Once a search is performed the corresponding results are displayed below the search component and show 
the number of proteins followed by the corresponding domain architecture. For each domain architecture,
the domain size is displayed based on the real length of the domain, using a protein of reference. 
When hovering over a domain, more details are available in a tooltip, including the domain's position. 
Clicking on the number of proteins redirects to the **Browse** tab in the :ref:`navigation menu <navigation_menu>` 
under the protein section, showing the list of proteins which can be filtered to a specific member database, 
if required, as described in the :ref:`browse feature <browse_feature>`.

By default, Pfam entries are shown in the results. This can be changed to show InterPro entries by toggling the 
Pfam checkbox to InterPro and vice versa.

The domain architectures can be downloaded in JSON and TSV formats through the **Export** button.


.. _browse_feature:

**************************************************
Using Browse feature to search and filter InterPro
**************************************************

.. figure:: images/search/browse_page.png
  :alt: Browse search
  :width: 800px

The browse search page can be accessed by clicking on the Browse tab in the :ref:`navigation menu <navigation_menu>`. 
The browse search provides a powerful functionality to select subsets of data available in InterPro by 
selecting filters according to the results required. For example, this page can be used to browse all 
entries which have a contributing signature from a particular member database e.g. HAMAP, or to retrieve 
all proteins from a certain taxon, e.g. *Escherichia coli*, that contain a specific domain e.g. OmpA-like domain.

Below we describe how to use the browse search feature:

1. Select a data type

The browse page opens up with **7 data types** to allow browsing of InterPro entries, Member databases signatures, 
Proteins, Structures, Taxonomies, Proteomes or Clans/Sets.

.. figure:: images/browse/tabs.png
  :alt: Data types
  :width: 800px

2. Select any additional filters

The filters options displayed for each data type will vary as appropriate.

3. Sort by accession

.. figure:: images/browse/sort_by_accession.png
  :alt: Sort by accession
  :width: 80px
  :align: left

The lists can be ordered by accession in ascending or descending order by clicking on the arrow on the right side of the column name
**Accession** when browsing by **InterPro**, **Member DB** and **Clan/Set**.

.. _memberdbFilter:

Member database filter
======================

.. figure:: images/browse/memberdb_filter.png
  :alt: Member database filter
  :width: 200px
  :align: left

The "**Select your database**" option is available when Browsing by Member DB, Protein, Structure, Taxonomy and Set.
It allows results to be retrieved from all or a selection of :doc:`InterPro member databases </databases>`. Only the databases that contain 
signatures for the chosen data type are displayed as options. By default all the member databases are selected, expect 
when Browsing by Member DB, where Pfam is the default option selected.


|
|
|
|
|
|


.. _text_filter:

Text filter
===========
The "**Search entries**" box allows results to be filtered to match the text entered. For example, the text could 
be a keyword that might be found in entry names. It also allows specific protein names or taxa to be entered.
By default the term searched is highlighted in yellow in the results list, this can be disabled by clicking on the
|toggle| symbol appearing between the text box and **Export** button once the search has started, the setting is saved and
also applied to other text searches throughout the website.

.. |toggle| image:: images/browse/toggle.png
  :alt: toggle icon
  :width: 15pt

.. _data_type_filters:

Data-type specific filters
==========================

.. _entry_filters:

InterPro entry filters
----------------------
.. figure:: images/browse/entry_filters.png
  :alt: Entry filters
  :width: 200px
  :align: left

When **Browse by InterPro** is selected, three filter types can be applied:

- **InterPro Type**: limits the data in the :ref:`data views <data_views>` to the selected :ref:`entry_types`.
- **GO Terms**: filters by selected GO terms from `InterPro2GO <https://www.ebi.ac.uk/GOA/InterPro2GO>`_.
- **New entries**: shows all the entries or only the entries created or made available in the most recent release.
- **Curation status**, show all the entries or show:

  - **Curated**: entries that have been created by an InterPro curator
  - **AI-generated (unreviewed)**: entries that have been created automatically by Artificial Intelligence
  - **AI-generated (reviewed)**: entries that have been created automatically by Artificial Intelligence for which the content has been verified by an InterPro curator

:doc:`More information about AI-generated content on the InterPro website. <llm_descriptions>`

|
|
|
|
|
|
|
|
|
|
|
|


.. _memberdb_filters:

Member database filters
-----------------------

.. figure:: images/browse/member_db_filters.png
  :alt: Member database filters
  :width: 200px
  :align: left

When **Browse by Member DB** is selected and a member database has been chosen, subsequent filters can be applied:

- **Member Database Entry Type**: select the types of signatures required. This is dependent on the database type selected. For example, if a database contains both domains and family signatures you can filter the results for a specific type.
- **InterPro state**: select all signatures from the selected database or only those signatures that have been integrated into InterPro.
- **Curation status**, show all the signatures or show:

  - **Curated**: signatures for which the name and description have been created by a scientific curator.
  - **AI-generated (unreviewed)**: signatures for which the name and description have been created automatically by Artificial Intelligence.

:doc:`More information about AI-generated content on the InterPro website. <llm_descriptions>`

|
|
|
|
|
|
|
|
|
|
|
|


Protein filters
---------------
Just as with the :ref:`Member DB <memberdb_filters>` data type, **Protein** filters change based on the selection in the 
:ref:`member database filter <memberdbFilter>` component. The basic filters are displayed irrespective of the 
selection made and an extra filter when the "**All Proteins**" option is selected.

.. figure:: images/browse/proteins_filter.png
  :alt: Proteins filters
  :width: 200px
  :align: left

Database selected
^^^^^^^^^^^^^^^^^

If a member database has been selected, the following filters are displayed:

- **UniProt Curation**: the `UniProtKB <https://www.uniprot.org/help/uniprotkb>`_ is split into two sections. The reviewed set is manually curated (SwissProt) and the unreviewed set is derived from public databases automatically integrated into UniProt (TrEMBL).
- **Taxonomy**: this filter allows the displayed list of proteins to be limited to certain organisms.
- **Sequence Status**: this filter allows proteins to be limited to complete proteins or fragments.

All Proteins
^^^^^^^^^^^^

.. figure:: images/browse/all_proteins_filter.png
  :alt: Matching entries filter
  :width: 200px
  :align: right

Additionally to the filters mentioned above, when the "**All Proteins**" option is selected in the 
:ref:`member database filter <memberdbFilter>` component, the **Matching Entries** filter is displayed. 
This filter allows the selection of proteins which do or do not contain matches to entries in the InterPro dataset.

|
|

Structure filters
-----------------
.. figure:: images/browse/structure_filter.png
  :alt: Structure filters
  :width: 200px
  :align: left
  
Structure filters do not vary depending on which option has been selected in the 
:ref:`member database filter <memberdbFilter>` component.

- **Experiment Type**: this filter allows selection of structures based on the type of experimental data the structure is based on.
- **Resolution**: this filter allows structures to be selected based on the resolution of the structure.

|
|
|
|
|

.. _data_views:

Data Display Options 
====================
The data display is the main part of the results section in the browse page and shows the data selected in the 
:ref:`data type menu <data_type_filters>`. The actual details shown will also be dependent on the selected data type. 

.. figure:: images/browse/data_view.png
  :alt: Data views
  :width: 350px

Tabular view
------------
.. figure:: images/browse/tabular.png
  :alt: Tabular icon
  :width: 100px
  :align: left
The tabular view is the default view and is available for all :ref:`InterPro data types <browse_feature>`. 
The table view icon formats data into a tabular view composed of rows representing individual entities. The table header 
describes the contents of each column. Clicking on one of the rows redirects to the corresponding :doc:`InterPro page </browse>`.

.. figure:: images/browse/entry_data.png
  :alt: Tabular entry view
  :width: 800px

  Tabular view example for InterPro entry data type

Grid view
---------

.. figure:: images/browse/grid.png
  :alt: Grid icon
  :width: 100px
  :align: left
The grid view is available for all :ref:`InterPro data types <browse_feature>`. It displays a series of cards 
summarising details of the entities being viewed. Clicking on one of the cards redirects to the corresponding 
:doc:`InterPro page </browse>`.

.. figure:: images/browse/entry_grid.png
  :alt: Grid entry view
  :width: 800px

  Grid view example for InterPro entry data type

Tree view
---------
.. figure:: images/browse/tree.png
  :alt: Tree icon
  :width: 100px
  :align: left

The tree view is currently only enabled for taxonomy data. The tree view icon is only shown where a tree view is 
possible.
The taxonomy tree viewer can be navigated by clicking on nodes or using keyboard arrow keys. This component is 
also used in the :ref:`taxonomy_page`.

.. figure:: images/browse/taxonomy_tree.png
  :alt: Tree view
  :width: 800px

  Tree view example for Euryarchaeota phylum
