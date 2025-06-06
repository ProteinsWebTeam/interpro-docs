Representative Domain and Family selection
##########################################

InterPro selects representative domains and families from protein signatures to provide a non-redundant view of protein features. This section describes the selection criteria and process.

Representative Domain selection
*******************************

Member database type filtering
==============================
The selection process begins by filtering protein signatures based on their signature type in the member database. Only signatures classified as domains, repeats or homologous superfamily are considered for representative domain selection, while other types such as families and sites are excluded from this process. It's important to note that this signature type may differ from the InterPro entry type in which the signature has been integrated. The representative domain selection strictly uses the original signature type from the member database, not the InterPro entry type. This approach maximizes the coverage of protein length by considering all eligible signatures, including those that haven't been integrated into InterPro entries.

Eligible member databases
=========================
Representative domains are selected exclusively from a specific set of member databases: Pfam, CDD, PROSITE profiles, SMART, NCBIfam, CATH-Gene3D and SUPERFAMILY. These databases have been chosen based on their reliability and coverage of domain annotations.

Selection process
=================
The selection of representative domains follows a systematic approach that begins with initial filtering of signatures. The system first narrows down the candidates by including only domain, repeat and homologous superfamily types from the eligible member databases listed above.

The next step groups candidate domain, repeat and homologous superfamily signatures that overlap along the protein sequence.

Within each group of overlapping signatures, we first narrow down the candidates to the top 20 domains based on the extent of protein coverage. Then, we explore different ways to combine these domains, allowing only combinations where domains either do not overlap or overlap by less than 30% of the shorter domain’s length. Each potential combination is evaluated by the total number of unique residue positions it covers across the protein sequence. The combination that covers the most unique residue positions is then marked as the representative set of domains.

.. note::
    The representative domain selection is protein-specific, meaning that the same signature might be selected as representative in one protein but not in another. This dynamic selection ensures the most appropriate representation for each specific protein context, taking into account the unique characteristics and structure of each protein.

Key considerations
==================
The selection process is designed to be deterministic for a given protein and set of matches, ensuring consistency in results. However, as member databases are updated, the selection results may change to reflect latest annotations. The protein-specific nature of the selection process means that domain representation can vary across different proteins, providing the most contextually appropriate annotations for each case.

Examples
========
**Example 1: Distinction between signature and InterPro types**

Consider an InterPro entry IPR123456 of type 'family' that contains two overlapping signatures:

#. A Pfam signature (positions 15-90)

   * Signature type: domain

   * Integrated in InterPro family entry IPR123456

   * Length: 75 AA

#. A CDD signature (positions 10-100)

   * Signature type: family

   * Integrated in same InterPro family entry IPR123756

   * Length: 90 AA

#. A SMART signature (positions 20-110)

   * Signature type: domain

   * Integrated in different InterPro domain entry IPR874321

   * Length: 90 AA

This example illustrates that even though Pfam and CDD signatures are integrated in the same InterPro family entry, only the Pfam signature is eligible for representative domain selection because it is of type 'domain'. The CDD signature, despite being in the same InterPro entry and covering a longer region, is excluded because its signature type is 'family'. The SMART signature, though in a different InterPro entry, is also considered because it is of type 'domain'. Between the two eligible signatures, SMART would be selected as representative because it covers a longer region (90 vs 75 amino acids (AA) in length).

**Example 2: Multidomain protein**

Consider a protein with multiple domain regions and the following signatures:

- Region 1 (N-terminal):

    - Pfam domain: positions 50-250
    - SMART domain: positions 70-230
    - CDD domain: positions 30-270

- Region 2 (C-terminal):

    - Pfam domain: positions 350-650
    - SMART domain: positions 400-600

In this case, two representative domains would be selected:

#. The CDD domain for Region 1, as it covers the longest region (240 AA)

#. The Pfam domain for Region 2, as it covers the longest region (300 AA)

.. figure:: images/representative_dom.png
    :alt: Representative Domain Selection
    :width: 800px
    
    Example of a representative domain selection process for a multidomain protein.

The diagram above illustrates how overlapping domains are grouped and representative domains are selected for each region. Note that different member database signatures can be selected as representative in different regions of the same protein.

Representative Families selection
*********************************

The process for selecting representative families follows similar principles to domain selection, but considers signatures of type 'family' instead of 'domain', 'repeat' or 'homologous superfamily'. Like domain selection, it uses the signature type from member databases rather than the InterPro entry type. Representative families are selected from the following member databases: Pfam, PIRSF, PANTHER, NCBIfam, HAMAP and SFLD. When signatures overlap, the longest one is selected as representative, ensuring comprehensive coverage of the protein sequence.

InterPro-N
**********
The presence of InterPro-N entries in the representative domains and families will depend on the **Display matches** mode selected under the 
**Options** dropdown on top of the protein sequence viewer:

    - Default/Stacked: if InterPro or InterPro-N matches are used for representative.
    - InterPro only: InterPro matches are used for representative.
    - InterPro-N only: InterPro-N are used for representative.

InterPro-N annotations are distinguished by a leading sparkles icon (|sparkles_icon|) on the right hand label in the protein sequence viewer and by a top right 
superscript (|interpro-n_tag|) on the InterPro or member database accession number in the tooltip.

.. |sparkles_icon| image:: images/icons/sparkles_icon.png
  :alt: sparkles icon
  :width: 18pt

.. |interpro-n_tag| image:: images/icons/interpro-n_tag.png
  :alt: InterPro-N tag
  :width: 70pt

Technical corner
****************

Implementation
==============
The selection logic is implemented in the `select_repr_domains` function within the `InterPro Github codebase <https://github.com/ProteinsWebTeam/interpro7-dw/blob/main/interpro7dw/interpro/oracle/matches.py>`_. This function processes protein matches systematically to determine representative domains based on the criteria described above.

Availability Through the InterPro API
=====================================
Representative domains can be accessed through the InterPro API. For each protein entry, the API response includes a 'representative' field set to true or false in the JSON output. This field indicates whether a particular signature has been selected as representative for that protein.

Example API endpoint: https://www.ebi.ac.uk/interpro/api/entry/pfam/protein/reviewed/O09185/

In the JSON response, each match contains a 'representative' field:

.. code-block:: json
    :emphasize-lines: 20

    {
    "results": [
        {
        "metadata": {
            "accession": "PF00001",
            "name": "Example Domain",
            "type": "domain"
        },
        "proteins": [
            {
            "signature": {...},
            "entry_protein_locations": [
                {
                "fragments":[
                    {
                    "start": 10,
                    "end": 100
                    }
                ],
                "representative": true  // Indicates a representative match
                }
            ],
            }
        ],
        }
    ],
    }