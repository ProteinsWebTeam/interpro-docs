#################################
Frequently Asked Questions (FAQs)
#################################

.. :ref:go_publication citing.html#go-publication
.. :ref:sequence_search searchways.html#sequence-search
.. :ref:navigation_menu banner.html#navigation-menu

*****************
General Questions
*****************

Why is InterPro useful?
========================
InterPro combines signatures from multiple, diverse databases into a single searchable 
resource, reducing redundancy and helping users interpret their sequence analysis results. 
By uniting the member databases, InterPro capitalises on their individual strengths, 
producing a powerful diagnostic tool and integrated resource.

What do people use InterPro for?
================================
InterPro provides an easy route to many kinds of protein analysis, for example:

- Identify all the proteins that belong to a protein family or contain a particular domain
- Identify what domains and sites are found in a particular protein.
- Identify proteins that share a common domain, even when the names and activities of the proteins are highly variable.
- Examine the species in which a particular protein family or domain is found.
- Annotation of genomes with protein family information as well as GO terms.

Who uses InterPro?
========================
InterPro is used by research scientists interested in the large-scale analysis of whole 
proteomes, genomes and metagenomes, as well as researchers seeking to characterise 
individual protein sequences. Within the EMBL-EBI, InterPro is used to help annotate 
protein sequences in UniProtKB. It is also used by the Gene Ontology Annotation group to 
automatically assign Gene Ontology terms to protein sequences.

What are entry types?
=====================
Each InterPro entry is assigned one of a number of types which tell you what you can infer 
when a protein matches the entry.

|D| **Domain**

Domains are distinct functional, structural or sequence units that may exist in a variety 
of biological contexts. A match to an InterPro entry of this type indicates the presence 
of a domain. Common examples of protein domains are the PH domain, Immunoglobulin domain 
or the classical C2H2 zinc finger. 

|F| **Family**

A protein family is a group of proteins that share a common evolutionary origin reflected 
by their related functions, similarities in sequence, or similar primary, secondary or 
tertiary structure. A match to an InterPro entry of this type indicates membership of a 
protein family.

|H| **Homologous Superfamily**

A homologous superfamily is a group of proteins that share a common evolutionary origin, 
reflected by similarity in their structure. Since superfamily members often display very 
low similarity at the sequence level, this type of InterPro entry is usually based on a 
collection of underlying hidden Markov models, rather than a single signature. Homologous 
superfamilies usually comprise signatures from the SUPERFAMILY and CATH-Gene3D databases.

|R| **Repeat**

A short sequence that is typically repeated within a protein. Repeats are often relatively 
short <50 amino acids in length.  Common repeats examples are Leucine Rich Repeats or WD40 
repeats.

|S| **Site**

InterPro contains data for the following types of sites:

- **Active site** - A short sequence that contains one or more conserved residues, which allow the protein to bind to a ligand and carry out a catalytic activity.
- **Binding site** - A short sequence that contains one or more conserved residues, which form a protein interaction site.
- **Conserved site** - A short sequence that contains one or more conserved residues.
- **PTM site** - A short sequence that contains one or more conserved residues some of which are the site of a Post-translational modification.

|U| **Unintegrated**

In addition to signatures that have been grouped into InterPro entries, you can also find 
signatures from member databases that are "unintegrated" in InterPro. These signatures 
might not yet be curated or might not reach InterPro's standards for integration. However, 
they can still provide important information about a protein of interest.

.. |F| image:: /images/entry_types/family.png
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

What are entry relationships?
=============================
InterPro organises its content into hierarchies, where possible. Entries at the
top of these hierarchies describe broad families or domains that share higher
level structure and/or function, while those entries at the bottom describe more
specific functional subfamilies or structural/functional subclasses of domains.

For example, steroid hormone receptors constitute a family of nuclear receptors
responsible for signal transduction mediated by steroid hormones, and can be
sub-classified into different groups, including the liver X receptor subfamily.
This subfamily consists of nuclear receptors that regulate the metabolism of
several important lipids, including oxysterols.

What are overlapping entries?
=============================
On the entry page, the relationship between homologous superfamilies and other
InterPro entries is calculated by analysing the overlap between matched sequence
sets. An InterPro entry is considered related to a homologous superfamily if its
sequence matches overlap (i.e., the match positions fall within the homologous
superfamily boundaries) and either the Jaccard index (equivalent) or containment
index (parent/child) of the matching sequence sets is greater than 0.75.

What do the colours mean in the graphical view of matches to my protein?
========================================================================
The graphical view of InterPro matches show where the signatures that match your
protein appear on the sequence. There are two ways that these graphical “blobs”
can be coloured. If you select “Colour by: domain relationship”, in the left
hand menu, the domains that are from the same or related InterPro entries will
be coloured the same, allowing easy visualisation of domains we know to be
related. Unintegrated signatures will always be grey blobs, family signatures
will always be shown as white, and sites will always be black when this option
is selected.

If you select “Colour by: member database”, each blob in the
sequence features section will be coloured according to the member database that
provides the signature, as shown in this diagram. However, the sequence summary
view will retain the domain relationship colour scheme.

Why are there no e-values associated with InterPro entries?
===========================================================
The signatures contained within InterPro are produced in different ways by
different member databases, so their e-values and/or scoring systems cannot be
meaningfully compared or combined. For this reason, we do not show e-values on
the InterPro web site. However, e-values can be obtained via the downloadable
InterProScan software package, which outputs detailed individual results for
each member database sequence analysis algorithm.

How are InterPro entries mapped to GO terms?
============================================
The assignment of GO terms to InterPro entries is performed manually, and is an
ongoing process (view related :ref:`publication <go_publication>`).

How do I contribute to InterPro?
================================
We welcome your contributions. To report errors or problems with the database,
please `get in touch via EBI support <https://www.ebi.ac.uk/support/interpro>`_.

********************************
Sequence searches (InterProScan)
********************************

How can I ensure privacy for my sequence searches?
=================================================
We adhere to EMBL standards on data privacy which can be found `here <https://www.ebi.ac.uk/data-protection/privacy-notice/embl-ebi-public-website>`_. 
However, if you have privacy concerns about submitting sequences for analysis via the web, 
the InterProScan software package can be downloaded for local installation from the EBI's 
`downloads page <https://www.ebi.ac.uk/interpro/download/>`_.


Can I access InterProScan programmatically?
=================================================
InterProScan can be accessed programmatically via Web services that allow up to
one sequence per request, and up to 25 requests in parallel (both
`SOAP <https://www.ebi.ac.uk/seqdb/confluence/pages/viewpage.action?pageId=68165103>`_
and `REST <https://www.ebi.ac.uk/seqdb/confluence/pages/viewpage.action?pageId=68165098>`_
-based services are available).

How do I interpret my InterProScan results?
===========================================

Please see the :ref:`sequence_search` section.

Can I trust my sequence search results?
=======================================
We make every effort to ensure that signatures integrated into InterPro are
accurate. Before being integrated, signatures are manually checked by curators
to ensure that they are of a high quality (i.e., they match the proteins they
are supposed to and hit as few incorrect proteins as possible).

While matches to InterPro should therefore be trustworthy, there are some
caveats. Most proteins are currently uncharacterised, so quality checks can only
ever be based on the subset of characterised proteins that match the signature.
It is therefore possible that signatures can match false positives that have not
been detected.

A useful rule of thumb is that the more signatures within an InterPro entry that
match a protein, the more likely it is that the match is correct. Matches within
the same hierarchy would also tend to increase confidence, as they all imply
membership of a particular group.

Nevertheless, please bear in mind that the member database signatures are
computational predictions. If you think one of our signatures matches false
positives, please `contact us <https://www.ebi.ac.uk/support/interpro>`_.

*************
Web Interface
*************

How do I view entry names instead of accessions in the graphical protein viewer?
================================================================================
The **Options** dropdown at the top right corner of the protein viewer above the protein 
scroll bar has labelling options grouped under "**Label by**". Please select the **Name**
option to see Entry names.

How do I explore the Taxonomy Tree viewer?
==========================================
The taxonomy tree viewer can be navigated by clicking on nodes or using keyboard
arrow keys.

I have selected a node in the Taxonomy tree viewer, how do I see data matching my selected taxonomy?
====================================================================================================
The information bar above the taxonomy viewer contains links on the right which
lead to data filtered to match the selected taxonomy node.

Can I still view the old InterPro website?
==========================================
Yes, for now you can! There two ways to access the old (legacy) website:

#. Navigate to this URL: `<https://www.ebi.ac.uk/interpro/legacy/>`_
#. Click on the Settings link from the InterPro Menu section of the sidebar

   a) Click on the “hamburger” icon above the magnifying glass icon to open the InterPro Menu sidebar.
   b) Then click the See this page in the old website link to be taken to the nearest matching page in the legacy website.

Please note that the legacy website isn't updated anymore and will be shut down after 
October 8, 2020 .

***************************************
Application Programming Interface (API)
***************************************

How do I get started using the REST API?
=========================================
Documentation for the API is available at our
`GitHub repository <https://github.com/ProteinsWebTeam/interpro7-api/tree/master/docs>`_.

If you'd like to see some example scripts in Perl, Python 2, Python 3 or
Javascript we have a script generator. Please follow the steps below:

#. Click on the `Results <https://www.ebi.ac.uk/interpro/result/download/>`_ tab in the :ref:`navigation menu <navigation_menu>`.
#. Click the `Your downloads <https://www.ebi.ac.uk/interpro/result/download/>`_ section.
#. Select the filters you'd like to apply.
#. Click on the **Copy code to clipboard** or **Download script file** buttons.

You can select the data type you're interested in and apply filters to your
query on this page. The corresponding API call is given under the **Results** section. 
The Code snippet section shows an example of code which you
can run on your computer to fetch the data from the InterPro API.

Why do I get HTTP timeouts (code 408) when running queries?
===========================================================
Certain queries of the InterPro API may take a long time to run. Any request
that takes longer than a few minutes is moved to run in the background and the
API will return the HTTP status code 408 corresponding to a timeout. The query
will continue to run in the background and the data will eventually become
available.

The `Select and Download InterPro data page <https://www.ebi.ac.uk/interpro/result/download/#/entry/InterPro/|accession>`_
shows examples of code which handles
these timeout codes to allow fetching of data from the API.

***************
Troubleshooting
***************

Why doesn't the website work properly in Web Browser private/incognito mode?
============================================================================

Some functionality of the InterPro website, particularly InterProScan searches
and downloading data make use of Browser storage. These functions require the
user to agree to EMBl-EBI cookies and are incompatible with browser
Incognito/Privacy modes.

Please grant permission for cookies and browse the site in a standard user
session to fully enable functionality of the InterPro website.

Click on the "hamburger" icon above the magnifying glass icon to open the InterPro Menu 
sidebar. The **Connection status**, provides information on the status of the different
resources used by InterPro. If all the lights are green it means all the resources are 
working as expected, otherwise you can see which resource has an issue.

***************
Additional help
***************

Click `here <https://www.ebi.ac.uk/support/interpro>`_ to submit a ticket to our helpdesk 
if you cannot find the answer to your questions here.

