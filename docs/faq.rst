#################################
Frequently Asked Questions (FAQs)
#################################

*****************
General Questions
*****************

What are entry types and why are they important?
------------------------------------------------

Each InterPro entry is assigned one of a number of types which tell you what
you can infer when a protein matches the entry. The entry types are described
in the :doc:`/data_types` section.

What are entry relationships?
-----------------------------

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
------------------------------

On the entry page, the relationship between homologous superfamilies and other
InterPro entries is calculated by analysing the overlap between matched sequence
sets. An InterPro entry is considered related to a homologous superfamily if its
sequence matches overlap (i.e., the match positions fall within the homologous
superfamily boundaries) and either the Jaccard index (equivalent) or containment
index (parent/child) of the matching sequence sets is greater than 0.75.

What do the colours mean in the graphical view of matches to my protein?
------------------------------------------------------------------------

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
-----------------------------------------------------------

The signatures contained within InterPro are produced in different ways by
different member databases, so their e-values and/or scoring systems cannot be
meaningfully compared or combined. For this reason, we do not show e-values on
the InterPro web site. However, e-values can be obtained via the downloadable
InterProScan software package, which outputs detailed individual results for
each member database sequence analysis algorithm.

How are InterPro entries mapped to GO terms?
--------------------------------------------

The assignment of GO terms to InterPro entries is performed manually, and is an
ongoing process (view related `publication
<https://www.ebi.ac.uk/interpro/help/documentation/publication/>`_).

How do I download InterPro?
---------------------------

The database and related software are freely available from the
`ftp site <ftp://ftp.ebi.ac.uk/pub/databases/interpro/>`_ for download.

How do I contribute to InterPro?
--------------------------------

We welcome your contributions. To report errors or problems with the database,
please `get in touch via EBI support <https://www.ebi.ac.uk/support/interpro>`_.

How do I collaborate?
---------------------

If you are interested in potential collaborations with InterPro, please
`contact us via EBI support <https://www.ebi.ac.uk/support/interpro>`_.

How do I cite InterPro?
-----------------------

Please see the details `here <https://www.ebi.ac.uk/interpro/about/citation/>`_.

********************************
Sequence searches (InterProScan)
********************************

How can I ensure privacy for my sequence searches?
--------------------------------------------------

We adhere to EMBL standards on data privacy. However, if you have privacy
concerns about submitting sequences for analysis via the web, the InterProScan
software package can be downloaded for local installation from the
`EBI's FTP server <ftp://ftp.ebi.ac.uk/pub/software/unix/iprscan>`_.

Can I access InterProScan programmatically?
-------------------------------------------

InterProScan can be accessed programmatically via Web services that allow up to
one sequence per request, and up to 25 requests in parallel (both
`SOAP <https://www.ebi.ac.uk/seqdb/confluence/pages/viewpage.action?pageId=68165103>`_
and `REST <https://www.ebi.ac.uk/seqdb/confluence/pages/viewpage.action?pageId=68165098>`_
-based services are available).

How do I interpret my InterProScan results?
-------------------------------------------

Please see the online tutorials section on the
`Training & tutorials <https://www.ebi.ac.uk/interpro/help/tutorial/>`_ page.

Can I trust my sequence search results?
---------------------------------------

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
--------------------------------------------------------------------------------

Please click on the "tag" icon in the top right corner of the protein viewer
above the protein scroll bar. This will toggle between showing Entry accession
values and names.

How do I explore the Taxonomy Tree viewer?
------------------------------------------

The taxonomy tree viewer can be navigated by clicking on nodes or using keyboard
arrow keys.

I have selected a node in the Taxonomy tree viewer, how do I see data matching my selected taxonomy?
----------------------------------------------------------------------------------------------------

The information bar above the taxonomy viewer contains links on the right which
lead to data filtered to match the selected taxonomy node.

***************************************
Application Programming Interface (API)
***************************************

How do I get started using the REST API?
----------------------------------------

Documentation for the API is available at our
`GitHub repository <https://github.com/ProteinsWebTeam/interpro7-api/tree/master/docs>`_

If you'd like to see some example scripts in Perl, Python 2, Python 3 or
Javascript we have a script generator. Please follow the steps below: The
resulting page allows combinations

#. Click on the `Results <https://www.ebi.ac.uk/interpro/result/download/>`_ tab in the tab list.
#. Click the `Your downloads <https://www.ebi.ac.uk/interpro/result/download/>`_ sub-tab.
#. Click the `Select and Download InterPro data <https://www.ebi.ac.uk/interpro/result/download/#/entry/InterPro/|accession>`_ button.

You can select the data type you're interested in and apply filters to your
query on this page. The Code snippet section shows an example of code which you
can run on your computer to fetch the data from the InterPro API.

Why do I get HTTP timeouts (code 408) when running queries?
-----------------------------------------------------------

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
----------------------------------------------------------------------------

Some functionality of the InterPro website, particularly InterProScan searches
and downloading data make use of Browser storage. These functions require the
user to agree to EMBl-EBI cookies and are incompatible with browser
Incognito/Privacy modes.

Please grant permission for cookies and browse the site in a standard user
session to fully enable functionality of the InterPro website.

Can I still view the old InterPro website?
------------------------------------------

Yes you can! There two ways to access the old (legacy) website:

#. Navigate to this URL: https://www.ebi.ac.uk/interpro/legacy/
#. Click on the Settings link from the InterPro Menu section of the sidebar

        * Click on the "hamburger" icon above the magnifying glass icon to open the InterPro Menu sidebar.
        * Then click the See this page in the old website link to be taken to the nearest matching page in the legacy website.

Please note we will continue to update the legacy website for a few releases,
but due to planned changes in our infrastructure, the legacy site will
eventually cease to be updated with new data.

* Click on the "hamburger" icon above the magnifying glass icon to open the InterPro Menu sidebar.

***************
Additional help
***************

`Submit a ticket <https://www.ebi.ac.uk/support/interpro>`_
