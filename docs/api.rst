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

Ongoing issues and future work
==============================

Some care is needed when combining filters to make sure the requested data
matches the intended query. Some responses still contain nested lists that are
limited to a maximum of 20 hits and cannot be paginated.
