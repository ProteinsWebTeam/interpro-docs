###################
InterPro Data Types
###################

InterPro entries reference a variety of different data types, so we store
these matching data in our databases.

*****
Entry
*****

Entries are the main data type of InterPro and subdivided into
:doc:`entry_types`. We also store all entries defined by :doc:`/entry_types`,
including both entries that have been **integrated** into an InterPro entry and
those which are **unintegrated**.

*******
Protein
*******

Every InterPro release involves matching all entries from InterPro and
the :doc:`member_databases` against all protein sequences in the
`UnitProtKB <https://www.uniprot.org/help/uniprotkb>`_. These matches are
calculated using the :doc:`/interproscan` tool.

*********
Structure
*********

Structure data from `PDBe <https://www.ebi.ac.uk/pdbe/>`_ is mapped to all
protein sequences and we use this relationship to match Entries to Structures.

********
Taxonomy
********

All protein sequences are assigned a value from the
`UniProt Taxonomy <https://www.uniprot.org/help/taxonomy>`_. This allows the
relationship between entries and all matching taxa to be calculated.

********
Proteome
********

Proteomes represent sets of proteins whose genome have been fully sequenced. A
given taxonomy node may have one or more Proteomes, for example, to reflect
different assemblies of a genome.

Proteome data is imported from
`UniProt proteomes <https://www.uniprot.org/help/proteome>`_. The mapping
between entries and proteomes is handled similarly to taxa.

***
Set
***

Some :doc:`member_databases` group related entries together into sets. For
example, Pfam defines **clans** as a collection of families that have arisen
from a single evolutionary origin. We import this type of data from member
databases where this is available.
