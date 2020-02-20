####################
InterPro Entry Types
####################

All the different types of functional models in InterPro are referred to as
Entries. These entries are subdivided into different entry types based on the
criteria described below.

Note that these definitions refer only to InterPro entries.
:doc:`/member_databases` may have their own definitions of entry types which
are likely to differ from types defined here.

******
Domain
******

.. image:: images/entry_types/domain.png
  :alt: Domain entry type icon
  :width: 75pt

Domains are distinct functional, structural or sequence units that may exist in
a variety of biological contexts. A match to an InterPro entry of this type
indicates the presence of a domain

******
Family
******

.. image:: images/entry_types/family.png
  :alt: Family entry type icon
  :width: 75pt

A protein family is a group of proteins that share a common evolutionary origin
reflected by their related functions, similarities in sequence, or similar
primary, secondary or tertiary structure. A match to an InterPro entry of this
type indicates membership of a protein family.

**********************
Homologous Superfamily
**********************

.. image:: images/entry_types/homologous.png
  :alt: Homologous Superfamily entry type icon
  :width: 75pt

A homologous superfamily is a group of proteins that share a common evolutionary
origin, reflected by similarity in their structure. Since superfamily members
often display very low similarity at the sequence level, this type of InterPro
entry is usually based on a collection of underlying hidden Markov models,
rather than a single signature.

******
Repeat
******

.. image:: images/entry_types/repeat.png
  :alt: Repeat entry type icon
  :width: 75pt

A short sequence that is typically repeated within a protein.

****
Site
****

.. image:: images/entry_types/site.png
  :alt: Site type icon
  :width: 75pt

InterPro contains data for the following types of sites.

Active
======

A short sequence that contains one or more conserved residues, which allow the
protein to bind to a ligand.

Binding
=======

A short sequence that contains one or more conserved residues, which form a
protein interaction site.

Conserved
=========

A short sequence that contains one or more conserved residues, which form a
protein interaction site.

PTM
===

A short sequence that contains one or more conserved residues.
Post-translational modification site.
