**********************
Using the InterPro API
**********************

This guide provides an introduction to the InterPro API. The query syntax is
flexible and makes it possible to fetch and filter many different kinds of data
from the InterPro databases.

The `InterPro website <https://www.ebi.ac.uk/interpro/>`_ is built on top of
the API and provides many practical examples of how the API can be used to
fetch data. The `script generator <https://www.ebi.ac.uk/interpro/result/download/#/entry/InterPro/|accession>`_
is particularly useful for generating examples to download InterPro data in
Python 3, Perl and JavaScript.

Getting started with examples
=============================

How many entries are there in the InterPro API?
-----------------------------------------------

This query returns counts for all the different sources of entries in the
InterPro dataset. It also includes counts for member database entries that are
integrated into InterPro and those that are still unintegrated.

`/api/entry <https://www.ebi.ac.uk/interpro/api/entry>`_

How do I get a list of all CDD entries in the InterPro API?
-----------------------------------------------------------

This query returns a paginated list of summary information about CDD entries in
the dataset. The response returns the first 20 hits and provides a link to the
next page of results.

`/api/entry/cdd <https://www.ebi.ac.uk/interpro/api/entry/cdd>`_

How many entries match human P53 protein (UniProt accession P04637)?
--------------------------------------------------------------------

This query returns counts for entries linked to P53 across the different data
sources represented in InterPro.

`/api/entry/protein/uniprot/P04637 <https://www.ebi.ac.uk/interpro/api/entry/protein/uniprot/P04637>`_

How do I retrieve all InterPro entries found in human P53 protein (P04637)?
---------------------------------------------------------------------------

This query returns the list of InterPro entries mapped to human P53 protein.

`/api/entry/interpro/protein/uniprot/P04637 <https://www.ebi.ac.uk/interpro/api/entry/interpro/protein/uniprot/P04637>`_

How do I retrieve UniProtKB reviewed proteins containing IPR002117?
-------------------------------------------------------------------

This query returns proteins that contain IPR002117, together with the location
of that match in each protein sequence.

`/api/protein/reviewed/entry/interpro/ipr002117 <https://www.ebi.ac.uk/interpro/api/protein/reviewed/entry/interpro/ipr002117>`_

How do I retrieve organisms that possess IPR026381?
---------------------------------------------------

This query returns organisms that have at least one protein containing a match
to IPR026381.

`/api/taxonomy/uniprot/entry/interpro/IPR026381 <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/entry/interpro/IPR026381>`_

Key concepts
============

Main data types
---------------

Currently, six main types of data are available through the API:

+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Type      | Description                                                            | Source                                                                                                                                 |
+===========+========================================================================+========================================================================================================================================+
| Entry     | Predicted functional and structural domains on proteins                | InterPro, CATH-Gene3D, CDD, HAMAP, PANTHER, Pfam, PIRSF, PRINTS, PROSITE Patterns, PROSITE Profiles, SMART, SFLD, SUPERFAMILY, NCBIfam |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Protein   | Protein sequence                                                       | UniProtKB, including reviewed and unreviewed proteins                                                                                  |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Structure | Macromolecular structures involving proteins                           | PDB                                                                                                                                    |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Set       | Sets describing relationships between entries                          | Pfam, CDD, PIRSF                                                                                                                       |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Taxonomy  | Taxonomic information about proteins                                   | UniProtKB                                                                                                                              |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+
| Proteome  | Collections of proteins defined from whole genome sequencing projects  | UniProtKB                                                                                                                              |
+-----------+------------------------------------------------------------------------+----------------------------------------------------------------------------------------------------------------------------------------+

REST interface
--------------

Queries are expressed as URLs. In general, a short query returns broad summary
data, while a more specific query returns more detailed data.

The most general query is:

`https://www.ebi.ac.uk/interpro/api/ <https://www.ebi.ac.uk/interpro/api/>`_

The JSON response includes, among other fields, a list of supported endpoints.

Main endpoints
--------------

The main data types are the most important endpoints because they determine the
type of data returned by a query.

- `/api/entry <https://www.ebi.ac.uk/interpro/api/entry>`_
- `/api/protein <https://www.ebi.ac.uk/interpro/api/protein>`_
- `/api/structure <https://www.ebi.ac.uk/interpro/api/structure>`_
- `/api/set <https://www.ebi.ac.uk/interpro/api/set>`_
- `/api/taxonomy <https://www.ebi.ac.uk/interpro/api/taxonomy>`_
- `/api/proteome <https://www.ebi.ac.uk/interpro/api/proteome>`_

Endpoint blocks
---------------

An endpoint block can contain up to three parts: a data type, a source
database, and a unique identifier. The type is mandatory, while the source and
identifier are optional.

These parts determine the response:

- A query with only a data type returns aggregated counts grouped by source.
- A query with a data type and source returns a paginated list of entities.
- A query that also includes an accession returns detailed information about a
  single entity.

Examples:

.. list-table::
   :header-rows: 1

   * - Query
     - Response type
     - Description
   * - `/api/entry <https://www.ebi.ac.uk/interpro/api/entry>`_
     - List of counts
     - Counts of entries in InterPro and member databases
   * - `/api/protein <https://www.ebi.ac.uk/interpro/api/protein>`_
     - List of counts
     - Counts of proteins in UniProtKB and its reviewed and unreviewed sets
   * - `/api/structure <https://www.ebi.ac.uk/interpro/api/structure>`_
     - List of counts
     - Counts of structures in PDB
   * - `/api/entry/interpro <https://www.ebi.ac.uk/interpro/api/entry/interpro>`_
     - List of entities
     - List of InterPro entries
   * - `/api/entry/cdd <https://www.ebi.ac.uk/interpro/api/entry/cdd>`_
     - List of entities
     - List of CDD entries
   * - `/api/proteome/uniprot <https://www.ebi.ac.uk/interpro/api/proteome/uniprot>`_
     - List of entities
     - List of proteomes
   * - `/api/entry/interpro/ipr023411 <https://www.ebi.ac.uk/interpro/api/entry/interpro/ipr023411>`_
     - Detailed object
     - Details of InterPro entry IPR023411
   * - `/api/entry/pfam/pf06235 <https://www.ebi.ac.uk/interpro/api/entry/pfam/pf06235>`_
     - Detailed object
     - Details of Pfam entry PF06235
   * - `/api/taxonomy/uniprot/9606 <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/9606>`_
     - Detailed object
     - Details of taxonomy identifier 9606

Filtering data
--------------

The first endpoint block defines the main type of data returned. Additional
endpoint blocks then filter that main dataset.

Examples:

- `/api/entry <https://www.ebi.ac.uk/interpro/api/entry>`_ returns counts for
  all entry sources.
- `/api/entry/protein <https://www.ebi.ac.uk/interpro/api/entry/protein>`_
  returns entries that map to proteins.
- `/api/entry/interpro/structure <https://www.ebi.ac.uk/interpro/api/entry/interpro/structure>`_
  returns InterPro entries that map to proteins with at least one structure.
- `/api/protein/reviewed/entry/interpro/ipr002117/taxonomy/uniprot/9606 <https://www.ebi.ac.uk/interpro/api/protein/reviewed/entry/interpro/ipr002117/taxonomy/uniprot/9606>`_
  returns reviewed proteins in taxonomy 9606 that contain IPR002117.


API query modifiers
=====================

Modifiers allow filtering and/or ordering the data returned by an API call.
They are appended to the URL as query parameters (e.g. ``?page_size=100``).
Multiple compatible modifiers can be combined with ``&``.

Apply to any API call
---------------------

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``page_size=<number up to 200>``
     - Yes
     - Number of results returned at a time (default=20)
     - `/api/protein/reviewed?page_size=100 <https://www.ebi.ac.uk/interpro/api/protein/reviewed?page_size=100>`_
   * - ``search=<text>``
     - Yes
     - Entries matching the text search
     - `/api/taxonomy/uniprot/?search=9606 <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/?search=9606>`_

/api/entry
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 35 15 35 15

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=type``
     - No
     - Number of entries for each entry type (e.g. family, domain, site...)
     - `/api/entry?group_by=type <https://www.ebi.ac.uk/interpro/api/entry?group_by=type>`_
   * - ``group_by=source_database``
     - No
     - Number of entries for each member database (e.g. pfam, CDD...)
     - `/api/entry?group_by=source_database <https://www.ebi.ac.uk/interpro/api/entry?group_by=source_database>`_
   * - ``group_by=tax_id``
     - No
     - Number of entries (InterPro+member database) for key species
     - `/api/entry?group_by=tax_id <https://www.ebi.ac.uk/interpro/api/entry?group_by=tax_id>`_
   * - ``group_by=go_terms``
     - No
     - Number of entries (InterPro+member database) for each GO term
     - `/api/entry?group_by=go_terms <https://www.ebi.ac.uk/interpro/api/entry?group_by=go_terms>`_
   * - ``type=<entry type>``
     - Yes
     - List of signatures with the entry type specified
     - `/api/entry?type=family <https://www.ebi.ac.uk/interpro/api/entry?type=family>`_
   * - ``go_category=[F, C, P]``
     - Yes
     - List of GO terms for the category specified (P for Biological Process, F for Molecular Function, and C for Cellular Component)
     - `/api/entry?go_category=F <https://www.ebi.ac.uk/interpro/api/entry?go_category=F>`_
   * - ``go_term=<GO identifier>``
     - Yes
     - Count entries that have been annotated with the given GO term, group by member database
     - `/api/entry?go_term=GO:0004298 <https://www.ebi.ac.uk/interpro/api/entry?go_term=GO:0004298>`_
   * - ``ida_search``
     - Yes
     - List of InterPro domain architectures with protein count
     - `/api/entry?ida_search <https://www.ebi.ac.uk/interpro/api/entry?ida_search>`_
   * - ``ida_search=<ipr1,pf2,ipr3>``
     - Yes
     - List of ida and protein count for the specified domain accessions
     - `/api/entry?ida_search=IPR003100,IPR003165 <https://www.ebi.ac.uk/interpro/api/entry?ida_search=IPR003100,IPR003165>`_
   * - ``ida_search=<ipr1,pf2,ipr3>&ordered``
     - Only with ``ida_search``
     - List of ida and protein count for the specified domain accessions where the accession order matters
     - `/api/entry?ida_search=IPR003100,IPR003165&ordered <https://www.ebi.ac.uk/interpro/api/entry?ida_search=IPR003100,IPR003165&ordered>`_
   * - ``ida_search=<ipr1,pf2,ipr3>&ordered&exact``
     - Only with ``ida_search`` + ``ordered``
     - Protein count for proteins containing specified domain accessions only
     - `/api/entry?ida_search=IPR003100,IPR003165&exact <https://www.ebi.ac.uk/interpro/api/entry?ida_search=IPR003100,IPR003165&exact>`_
   * - ``ida_search=<ipr1,pf2,ipr3>&ida-ignore=<ipr4,pf6>``
     - Only with ``ida_search``
     - List of ida and protein count for the specified domain accessions where the last accessions specified shouldn't be in the ida
     - `/api/entry?ida_search=IPR003100,IPR003165&ida_ignore=PF08699 <https://www.ebi.ac.uk/interpro/api/entry?ida_search=IPR003100,IPR003165&ida_ignore=PF08699>`_

/api/entry/<database name>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Database name can be: ``interpro``, ``pfam``, ``cdd``, ``panther``, ``sfld``,
``cathgene3d``, ``ssf``, ``hamap``, ``pirsf``, ``prints``, ``prosite``,
``profile``, ``smart``, ``ncbifam``.

.. note::

   Since InterPro 94.0, ``tigrfams`` has been replaced by ``ncbifam``.
   Temporary redirects are in place, but users are recommended to update to
   ``ncbifam`` to avoid any problems.

.. list-table::
   :header-rows: 1
   :widths: 40 15 30 15

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=type``
     - No
     - Number of signatures for each member database entry type (e.g. family, domain...) for the database selected
     - `/api/entry/pfam?group_by=type <https://www.ebi.ac.uk/interpro/api/entry/pfam?group_by=type>`_
   * - ``group_by=source_database``
     - No
     - Number of signatures for the database selected
     - `/api/entry/pfam?group_by=source_database <https://www.ebi.ac.uk/interpro/api/entry/pfam?group_by=source_database>`_
   * - ``group_by=go_categories``
     - No
     - Number of signatures for each GO term category for the database selected
     - `/api/entry/cathgene3d?group_by=go_categories <https://www.ebi.ac.uk/interpro/api/entry/cathgene3d?group_by=go_categories>`_
   * - ``group_by=tax_id``
     - No
     - Number of signatures for key species for the database selected
     - `/api/entry/cathgene3d?group_by=tax_id <https://www.ebi.ac.uk/interpro/api/entry/cathgene3d?group_by=tax_id>`_
   * - ``group_by=go_terms``
     - No
     - Number of entries for each GO term for the database selected
     - `/api/entry/integrated?group_by=go_terms <https://www.ebi.ac.uk/interpro/api/entry/integrated?group_by=go_terms>`_
   * - ``type=<entry_type>``
     - Yes
     - List of signatures with the entry type specified for the database selected
     - `/api/entry/smart?type=domain <https://www.ebi.ac.uk/interpro/api/entry/smart?type=domain>`_
   * - ``sort_by=accession``
     - Yes
     - List of signatures sorted by accession (low to high) for the database selected
     - `/api/entry/pfam?sort_by=accession <https://www.ebi.ac.uk/interpro/api/entry/pfam?sort_by=accession>`_
   * - ``sort_by=integrated``
     - Yes
     - List of signatures sorted by integrated ones first for the database selected
     - `/api/entry/pfam?sort_by=integrated <https://www.ebi.ac.uk/interpro/api/entry/pfam?sort_by=integrated>`_
   * - ``extra_fields=[counters, entry_id, short_name, description, wikipedia, literature, hierarchy, cross_references, entry_date, is_featured, overlaps_with]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/entry/InterPro?signature_in=hamap&extra_fields=description <https://www.ebi.ac.uk/interpro/api/entry/InterPro?signature_in=hamap&extra_fields=description>`_
   * - ``annotation=[hmm, alignment, logo]``
     - No
     - List of entries which have an annotation of the given type (hmm, alignment, logo)
     - `/api/entry/pfam?annotation=hmm <https://www.ebi.ac.uk/interpro/api/entry/pfam?annotation=hmm>`_

/api/entry/<integrated, unintegrated>
^^^^^^^^^^^^^^^^^^^^^^^^^^

Information on member database signatures integrated/unintegrated in InterPro entries.

.. list-table::
   :header-rows: 1
   :widths: 40 15 30 15

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=type``
     - No
     - Number of integrated/unintegrated entries for each entry type (e.g. family, domain, site...)
     - `/api/entry/unintegrated?group_by=type <https://www.ebi.ac.uk/interpro/api/entry/unintegrated?group_by=type>`_
   * - ``group_by=source_database``
     - No
     - Number of integrated/unintegrated entries for each member database (e.g. pfam, CDD...)
     - `/api/entry/unintegrated?group_by=source_database <https://www.ebi.ac.uk/interpro/api/entry/unintegrated?group_by=source_database>`_
   * - ``group_by=tax_id``
     - No
     - Number of integrated/unintegrated entries for key species
     - `/api/entry/unintegrated?group_by=tax_id <https://www.ebi.ac.uk/interpro/api/entry/unintegrated?group_by=tax_id>`_
   * - ``group_by=go_terms``
     - No
     - Number of integrated/unintegrated entries for each GO term
     - `/api/entry/integrated?group_by=go_terms <https://www.ebi.ac.uk/interpro/api/entry/integrated?group_by=go_terms>`_
   * - ``extra_fields=[counters, entry_id, short_name, description, wikipedia, literature, hierarchy, cross_references, entry_date, is_featured, overlaps_with]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/entry/integrated?group_by=go_terms&extra_fields=counters <https://www.ebi.ac.uk/interpro/api/entry/integrated?group_by=go_terms&extra_fields=counters>`_

/api/entry/interpro
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=member_databases``
     - No
     - Number of integrated signatures for each member database (e.g. pfam, CDD...)
     - `/api/entry/interpro?group_by=member_databases <https://www.ebi.ac.uk/interpro/api/entry/interpro?group_by=member_databases>`_
   * - ``latest_entries``
     - No
     - List of InterPro entries integrated in the last InterPro release
     - `/api/entry/interpro?latest_entries <https://www.ebi.ac.uk/interpro/api/entry/interpro?latest_entries>`_
   * - ``signature_in=<memberdb>``
     - Yes
     - List of InterPro entries that have a match with the given memberDB
     - `/api/entry/InterPro?signature_in=hamap <https://www.ebi.ac.uk/interpro/api/entry/InterPro?signature_in=hamap>`_
   * - ``go_category=[F, C, P]``
     - Yes
     - List of GO terms for the category specified (P for Biological Process, F for Molecular Function, and C for Cellular Component)
     - `/api/entry/interpro?go_category=F <https://www.ebi.ac.uk/interpro/api/entry/interpro?go_category=F>`_
   * - ``go_term=<GO identifier>``
     - No
     - List of InterPro entries that have been annotated with the given GO term
     - `/api/entry/interpro?go_term=GO:0004298 <https://www.ebi.ac.uk/interpro/api/entry/interpro?go_term=GO:0004298>`_

/api/entry/interpro/<InterPro entry accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 40 15 30 15

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``interactions``
     - No
     - List of interactions proteins matching the entry are involved in (obtained from Intact database)
     - `/api/entry/InterPro/IPR000477?interactions <https://www.ebi.ac.uk/interpro/api/entry/InterPro/IPR000477?interactions>`_
   * - ``pathways``
     - No
     - List of pathways proteins matching the entry are involved in (obtained from MetaCyc and Reactome databases)
     - `/api/entry/InterPro/IPR024156?pathways <https://www.ebi.ac.uk/interpro/api/entry/InterPro/IPR024156?pathways>`_
   * - ``annotation:info``
     - No
     - Entry information
     - `/api/entry/InterPro/IPR025743?annotation:info <https://www.ebi.ac.uk/interpro/api/entry/InterPro/IPR025743?annotation:info>`_
   * - ``extra_fields=[counters, entry_id, short_name, description, wikipedia, literature, hierarchy, cross_references, entry_date, is_featured, overlaps_with]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/entry/InterPro/IPR024156?extra_fields=short_name <https://www.ebi.ac.uk/interpro/api/entry/InterPro/IPR024156?extra_fields=short_name>`_

/api/entry/<member database>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::

   Not available for InterPro.

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``interpro_status``
     - Yes
     - Number of signatures integrated and unintegrated in InterPro entries for the member database selected
     - `/api/entry/panther?interpro_status <https://www.ebi.ac.uk/interpro/api/entry/panther?interpro_status>`_
   * - ``integrated=<interpro accession>``
     - Yes
     - List of signatures integrated in the specified InterPro entry
     - `/api/entry/pfam?integrated=IPR003165 <https://www.ebi.ac.uk/interpro/api/entry/pfam?integrated=IPR003165>`_

/api/entry/<member database>/<accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``annotation=[hmm, alignment, logo]``
     - No
     - Download compressed signature hmm file if it exists
     - `/api/entry/pfam/pf02171?annotation=hmm <https://www.ebi.ac.uk/interpro/api/entry/pfam/pf02171?annotation=hmm>`_

/api/entry/protein
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=type``
     - No
     - Number of proteins for each entry type (e.g. family, domain, site...)
     - `/api/entry/protein?group_by=type <https://www.ebi.ac.uk/interpro/api/entry/protein?group_by=type>`_

/api/protein
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=tax_id``
     - No
     - Number of proteins for each taxon
     - `/api/protein?group_by=tax_id <https://www.ebi.ac.uk/interpro/api/protein?group_by=tax_id>`_
   * - ``group_by=go_terms``
     - No
     - Number of proteins for each GO term
     - `/api/protein?group_by=go_terms <https://www.ebi.ac.uk/interpro/api/protein?group_by=go_terms>`_
   * - ``group_by=match_presence``
     - No
     - Number of proteins with/without an InterPro entry match
     - `/api/protein?group_by=match_presence <https://www.ebi.ac.uk/interpro/api/protein?group_by=match_presence>`_
   * - ``group_by=is_fragment``
     - No
     - Number of full/fragmented proteins
     - `/api/protein?group_by=is_fragment <https://www.ebi.ac.uk/interpro/api/protein?group_by=is_fragment>`_
   * - ``group_by=source_database``
     - No
     - Number of reviewed and unreviewed proteins
     - `/api/protein?group_by=source_database <https://www.ebi.ac.uk/interpro/api/protein?group_by=source_database>`_
   * - ``match_presence=[true,false]``
     - Yes
     - Number of proteins with [true]/without [false] a match to an InterPro entry
     - `/api/protein?match_presence=false <https://www.ebi.ac.uk/interpro/api/protein?match_presence=false>`_
   * - ``tax_id=<accession>``
     - Yes
     - Number of proteins that belong to this taxonomy id
     - `/api/protein?tax_id=2711 <https://www.ebi.ac.uk/interpro/api/protein?tax_id=2711>`_
   * - ``is_fragment=[true,false]``
     - Yes
     - Number of proteins that are [true]/aren't [false] fragments
     - `/api/protein?is_fragment=true <https://www.ebi.ac.uk/interpro/api/protein?is_fragment=true>`_

/api/protein/<uniprot/reviewed/unreviewed>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 40 15 30 15

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=go_terms``
     - No
     - List of proteins for each GO term for the protein source selected
     - `/api/protein/reviewed?group_by=go_terms <https://www.ebi.ac.uk/interpro/api/protein/reviewed?group_by=go_terms>`_
   * - ``group_by=is_fragment``
     - No
     - Number of proteins that are and aren't fragments for the protein source selected
     - `/api/protein/reviewed?group_by=is_fragment <https://www.ebi.ac.uk/interpro/api/protein/reviewed?group_by=is_fragment>`_
   * - ``group_by=match_presence``
     - No
     - Number of proteins that have and don't have matches to InterPro entries for the protein source selected
     - `/api/protein/reviewed?group_by=match_presence <https://www.ebi.ac.uk/interpro/api/protein/reviewed?group_by=match_presence>`_
   * - ``group_by=tax_id``
     - No
     - Number of proteins for each taxon for the protein source selected
     - `/api/protein/uniprot?group_by=tax_id <https://www.ebi.ac.uk/interpro/api/protein/uniprot?group_by=tax_id>`_
   * - ``group_by=source_database``
     - No
     - Number of proteins for the protein source selected
     - `/api/protein/unreviewed?group_by=source_database <https://www.ebi.ac.uk/interpro/api/protein/unreviewed?group_by=source_database>`_
   * - ``go_term=<GO identifier>``
     - Yes
     - List of proteins for the GO term and protein source selected
     - `/api/protein/reviewed?go_term=GO:0004298 <https://www.ebi.ac.uk/interpro/api/protein/reviewed?go_term=GO:0004298>`_
   * - ``id=<Uniprot identifier>``
     - Yes
     - Information about the protein with the specified UniProt identifier
     - `/api/protein/reviewed?id=CYC_HUMAN <https://www.ebi.ac.uk/interpro/api/protein/reviewed?id=CYC_HUMAN>`_
   * - ``tax_id=<accession>``
     - Yes
     - List of proteins corresponding to the tax_id specified for the protein resource selected
     - `/api/protein/uniprot?tax_id=2711 <https://www.ebi.ac.uk/interpro/api/protein/uniprot?tax_id=2711>`_
   * - ``ida=<ida_accession>``
     - Yes
     - List of proteins with the specified domain architecture for the protein source selected
     - `/api/protein/reviewed?ida=6ad3f81f5ba41a43b4c938fb2018f519f64e0548 <https://www.ebi.ac.uk/interpro/api/protein/reviewed?ida=6ad3f81f5ba41a43b4c938fb2018f519f64e0548>`_
   * - ``match_presence=[true,false]``
     - Yes
     - List of proteins for the protein source selected with [true]/without [false] a match to an InterPro entry
     - `/api/protein/reviewed?match_presence=true <https://www.ebi.ac.uk/interpro/api/protein/reviewed?match_presence=true>`_
   * - ``is_fragment=[true,false]``
     - Yes
     - List of proteins for the protein source selected that are [true]/aren't [false] fragments
     - `/api/protein/reviewed?is_fragment=true <https://www.ebi.ac.uk/interpro/api/protein/reviewed?is_fragment=true>`_
   * - ``extra_fields=[counters, identifier, description, sequence, gene, go_terms, evidence_code, residues, tax_id, proteome, extra_features, structure, is_fragment, ida_id, ida]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/protein/reviewed?id=CYC_HUMAN&extra_fields=sequence <https://www.ebi.ac.uk/interpro/api/protein/reviewed?id=CYC_HUMAN&extra_fields=sequence>`_

/api/protein/<uniprot/reviewed/unreviewed>/<protein accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``residues``
     - No
     - Residues annotations for the protein selected
     - `/api/protein/uniprot/A0A000?residues <https://www.ebi.ac.uk/interpro/api/protein/uniprot/A0A000?residues>`_
   * - ``structureinfo``
     - No
     - CATH/SCOP domains matching the protein selected
     - `/api/protein/uniprot/P02185?structureinfo <https://www.ebi.ac.uk/interpro/api/protein/uniprot/P02185?structureinfo>`_
   * - ``ida``
     - No
     - Information about the protein domains arrangement based on Pfam domains
     - `/api/protein/reviewed/D4A7N1?ida <https://www.ebi.ac.uk/interpro/api/protein/reviewed/D4A7N1?ida>`_
   * - ``extra_features``
     - No
     - Matches from the extra feature section (e.g. Mobidb-lite, Coil)
     - `/api/protein/reviewed/D4A7N1?extra_features <https://www.ebi.ac.uk/interpro/api/protein/reviewed/D4A7N1?extra_features>`_
   * - ``isoforms``
     - No
     - Different isoforms of the protein
     - `/api/protein/reviewed/Q6ZNL6?isoforms <https://www.ebi.ac.uk/interpro/api/protein/reviewed/Q6ZNL6?isoforms>`_
   * - ``isoforms=<isoform_id>``
     - No
     - Information about the isoform selected
     - `/api/protein/reviewed/Q6ZNL6?isoforms=Q6ZNL6-1 <https://www.ebi.ac.uk/interpro/api/protein/reviewed/Q6ZNL6?isoforms=Q6ZNL6-1>`_
   * - ``extra_fields=[counters, identifier, description, sequence, gene, go_terms, evidence_code, residues, tax_id, proteome, extra_features, structure, is_fragment, ida_id, ida]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/protein/reviewed/Q6ZNL6?extra_fields=sequence <https://www.ebi.ac.uk/interpro/api/protein/reviewed/Q6ZNL6?extra_fields=sequence>`_
   * - ``conservation=<member database>``
     - No
     - Residue conservation calculated using HMMER for the member database specified
     - `/api/protein/reviewed/D4A7N1?conservation=panther <https://www.ebi.ac.uk/interpro/api/protein/reviewed/D4A7N1?conservation=panther>`_

/api/proteome/uniprot
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``group_by=proteome_is_reference``
     - No
     - Number of UniProt proteomes that are/aren't from the UniProt reference proteome
     - `/api/proteome/uniprot?group_by=proteome_is_reference <https://www.ebi.ac.uk/interpro/api/proteome/uniprot?group_by=proteome_is_reference>`_
   * - ``extra_fields=[counters, strain, assembly]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/proteome/uniprot?extra_fields=counters <https://www.ebi.ac.uk/interpro/api/proteome/uniprot?extra_fields=counters>`_

/api/set/<all, cdd, pfam>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``extra_fields=[counters, description, relationships]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/set/cdd?extra_fields=counters <https://www.ebi.ac.uk/interpro/api/set/cdd?extra_fields=counters>`_

/api/set/<all, cdd, pfam>/<accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``alignments``
     - No
     - Alignment information for the database and set specified
     - `/api/set/cdd/cl00014/?alignments= <https://www.ebi.ac.uk/interpro/api/set/cdd/cl00014/?alignments=>`_

/api/structure
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``experiment_type=[x_ray,nmr,em]``
     - No
     - Number of structures for the experiment type selected
     - `/api/structure?experiment_type=nmr <https://www.ebi.ac.uk/interpro/api/structure?experiment_type=nmr>`_
   * - ``group_by=experiment_type``
     - No
     - Number of structures for each experiment type
     - `/api/structure?group_by=experiment_type <https://www.ebi.ac.uk/interpro/api/structure?group_by=experiment_type>`_

/api/structure/pdb
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 35 15 30 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``experiment_type=[x_ray,nmr,em]``
     - Yes
     - List of PDB structures for the experiment type selected
     - `/api/structure/PDB/?experiment_type=x-ray <https://www.ebi.ac.uk/interpro/api/structure/PDB/?experiment_type=x-ray>`_
   * - ``resolution=<start-end>``
     - Yes
     - List of PDB structures between the resolution range selected
     - `/api/structure/pdb?resolution=1.0-2.5 <https://www.ebi.ac.uk/interpro/api/structure/pdb?resolution=1.0-2.5>`_
   * - ``group_by=experiment_type``
     - No
     - Number of PDB structures for each experiment type
     - `/api/structure/pdb?group_by=experiment_type <https://www.ebi.ac.uk/interpro/api/structure/pdb?group_by=experiment_type>`_
   * - ``extra_fields=[release_date, literature, chains, secondary_structures, counters]``
     - Yes
     - Includes the value of the selected fields in the results
     - `/api/structure/pdb?resolution=1.0-2.5&extra_field=secondary_structures <https://www.ebi.ac.uk/interpro/api/structure/pdb?resolution=1.0-2.5&extra_field=secondary_structures>`_

/api/structure/pdb/<pdb accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 35 15 30 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``extra_fields=[release_date, literature, chains, secondary_structures, counters]``
     - No
     - Includes the value of the selected fields in the results
     - `/api/structure/pdb/101m?extra_field=release_date <https://www.ebi.ac.uk/interpro/api/structure/pdb/101m?extra_field=release_date>`_

/api/taxonomy/uniprot
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``scientific_name=<name>``
     - No
     - Taxon hierarchy and counters
     - `/api/taxonomy/uniprot?scientific_name=Bacteria <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot?scientific_name=Bacteria>`_
   * - ``key_species``
     - No
     - Taxonomy info for key species
     - `/api/taxonomy/uniprot?key_species <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot?key_species>`_
   * - ``extra_fields=[counters, scientific_name, full_name, lineage, rank]``
     - Yes
     - Includes the value of the selected fields in the results
     - `/api/taxonomy/uniprot?extra_fields=full_name <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot?extra_fields=full_name>`_

/api/taxonomy/uniprot/<taxonomy accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``with_names``
     - No
     - Selected taxon hierarchy and names
     - `/api/taxonomy/uniprot/1?with_names <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/1?with_names>`_
   * - ``filter_by_entry=<InterPro accession>``
     - No
     - Selected taxon hierarchy and counters for the InterPro entry accession specified
     - `/api/taxonomy/uniprot/1?filter_by_entry=IPR001165 <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/1?filter_by_entry=IPR001165>`_
   * - ``filter_by_entry_db=<db name>``
     - No
     - Selected taxon hierarchy and counters for the database name specified (e.g. interpro, pfam, smart...)
     - `/api/taxonomy/uniprot/1?filter_by_entry_db=interpro <https://www.ebi.ac.uk/interpro/api/taxonomy/uniprot/1?filter_by_entry_db=interpro>`_

/api/protein/uniprot/entry/<source database>/<interpro accession>
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Proteins with an AlphaFold model.

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``has_model=[true,false]``
     - No
     - List of proteins with/without an AlphaFold prediction for the source database entry selected
     - `/api/protein/uniprot/entry/InterPro/IPR000001/?has_model=true <https://www.ebi.ac.uk/interpro/api/protein/uniprot/entry/InterPro/IPR000001/?has_model=true>`_

Proteins with an AlphaFold or BFVD model.

.. list-table::
   :header-rows: 1
   :widths: 30 15 35 20

   * - Modifier
     - Combinable
     - Data returned
     - Example
   * - ``with=[alphafold,bfvd]``
     - No
     - List of proteins with an AlphaFold prediction or a BFVD prediction for the source database entry selected
     - `/api/protein/uniprot/entry/InterPro/IPR000001/?with=alphafold <https://www.ebi.ac.uk/interpro/api/protein/uniprot/entry/InterPro/IPR000001/?with=alphafold>`_


Ongoing issues and future work
==============================

Some care is needed when combining filters to make sure the requested data
matches the intended query. Some responses still contain nested lists that are
limited to a maximum of 20 hits and cannot be paginated.
