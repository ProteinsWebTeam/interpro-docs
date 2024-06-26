***********************
Protein sequence viewer
***********************

.. :ref:sequence_search searchways.html#sequence-search
.. :ref:protein_page browse.html#protein-page
.. :ref:structure_page browse.html#structure-page
.. :ref:entry_types entries_info.html#entry-types
.. :ref:signature browse.html#signature

A common element on several InterPro website pages is the protein sequence viewer (in the 
:ref:`sequence search result <sequence_search>`, on the :ref:`protein <protein_page>` and 
:ref:`structure <structure_page>` pages). It summarises the InterPro entries (IPR) (top coloured
bar) and member database signatures matches to the protein or structure
being looked at, represented by the grey bar at the top of the viewer, categorised by :ref:`entry_types`. 

The *AlphaFold confidence* track is displayed in the protein sequence viewer in the :ref:`protein page <protein_page>` 
and in the :ref:`AlphaFold subpage <alphafold1>` when a predicted structure is available.

The *Representative Domains* track is displayed in the protein sequence viewer in the :ref:`protein page <protein_page>`. This representation is generated automatically using the type of the member databases models, which might differ from the InterPro entries types. When multiple models are overlapping, the representative domain is chosen by selecting the model covering the longest region of the protein. Be aware that in case of models made of multiple fragments, not all the fragments are necessarily chosen as representative, they are considered as individual entities for the selection.

.. protein used: https://www.ebi.ac.uk/interpro/protein/UniProt/A0Q9F3/

.. figure:: images/protein_viewer/pv_help.png
  :alt: Protein sequence viewer
  :width: 800px

Various options, make it easy to work with (as illustrated in the figure above):

1. Clicking on the Full screen button at the top of the viewer will switch to full screen view.

2. The viewer can be zoomed in and out by:

  a. Clicking the two buttons (+ and -) at the top right corner.
  b. Dragging the grey scale at the top to the desired positions on both left and right sides
  c. Pressing the [Ctrl] key and scroll through the viewer 

3. More options that customise the viewer are grouped under **Options** dropdown.

.. figure:: images/protein_viewer/pv_options_dropdown.png
  :alt: Protein sequence viewer options
  :align: left
  :width: 350px

A. **Colour By** allows to change the colours in which the InterPro entries and signatures bars based on accession, member database or domain relationship. 

B. The labels on the right side of the viewer can be customised. The **Accession** labels are shown by default. To see names and/or short names along with accession, the name/short name checkboxes should be ticked or if the user prefers to see the names/short names alone, the respective options should be selected.

C. **Save as image** allows to take a snapshot of the viewer and is saved as an image (.png).

D. The tooltips are shown when hovering over each bar. They can be disabled by unchecking the **Tooltip Active** option.

.. figure:: images/protein_viewer/pv_tooltip.png
  :alt: Protein sequence viewer tooltip
  :width: 800px

  Tooltip example.

4. Residues annotations are provided by the CDD, SFLD and PIRSR databases.

.. 5. On the :ref:`protein_page`, clicking on the **Fetch conservation** button, will display the conservation information based on the PANTHER signatures. 
.. The conservation scores are generated using the following process: 

.. - The HMM model from the PANTHER database is run against the SwissProt database using hmmsearch, generating an HMM profile and a :ref:`logo <signature>` (graphical representation of the amino acid conservation).
.. - The conservation score for each residue is determined, from the logo data, using the following formula: :math:`\frac {\sum (height\_arr)} {max\_height\_theory} \times 10`
.. - The model is aligned against the protein sequence.

.. .. figure:: images/protein_viewer/pv_conservation.png
..   :alt: Protein sequence viewer conservation track
..   :width: 800px

5. Clicking on the header of a category (say Unintegrated) hides the bars for the entire category.

When zoomed in, panning can be achieved by either dragging the scale at the top or by dragging any bar in the desired direction (see figure below).

.. figure:: images/protein_viewer/pv_panning.png
  :alt: Protein sequence viewer panning
  :width: 800px

For some proteins, additional information are provided by resources other than the member 
database consortium, they are displayed under the **Other features** category of the viewer.
Available data include:

- Disordered regions from `MobiDB <https://www.mobidb.org/>`_
- Transmembrane regions from `Phobius <https://phobius.sbc.su.se/>`_ and/or `TMHMM <https://services.healthtech.dtu.dk/service.php?TMHMM-2.0>`_
- Coiled regions from COILS
- Cytoplasmic/non-cytoplasmic domains from Phobius
- Signal peptide regions from `SignalP <https://services.healthtech.dtu.dk/service.php?SignalP-5.0>`_ and/or Phobius
- Spurious protein from :doc:`AntiFam </antifam>`
- `CATH-FunFams <https://github.com/UCLOrengoGroup/cath-funfam-docs>`_ is an automatically generated profile HMM database, with FunFams entries segregated by an entropy-based approach  that distinguishes different patterns of conserved residues, corresponding to differences in functional determinants
- `Pfam-N annotations <hxfam.wordpress.com/2024/05/31/pfam-n-version-3-enhancing-pfam-coverage-of-uniprot-with-computer-vision-deep-learning-techniques/>`_ result from a deep learning methodology developed by the Google Research team led by Dr Lucy Colwell to increase the Pfam coverage of protein sequences
- Eukaryotic linear motifs from `ELM <http://elm.eu.org/>`_

For some proteins, we also have annotations that are fetched directly from the resource API.
These annotations are displayed under the **External Sources** category of the viewer. Note: by default this
category is collapsed. Available data include:

- 3D structure and domain predictions from the `Genome3D consortium <http://genome3d.net/resource>`_ 
- Intrinsically disordered proteins from `DisProt <https://www.disprot.org/>`_
- Tandem repeat from `RepeatsDB <https://repeatsdb.bio.unipd.it/>`_

.. figure:: images/protein_viewer/pv_external_sources.png
  :alt: Protein sequence viewer External Sources for the protein O75069
  :width: 800px

  Protein sequence viewer External Sources for `O75069 <https://www.ebi.ac.uk/interpro/protein/UniProt/O75069/>`_

For some proteins, information about pathogenic and likely pathogenic residue variants in 
protein sequences is available under the **Clinical Significance: Pathogenic And Likely 
Pathogenic Variants** category of the viewer. Please note that the data can differ from the  data provided on the UniProt website as we are applying a *Clinical significance* filter,  
which is different from the one used by UniProt. 

.. figure:: images/protein_viewer/pv_variants.png
  :alt: Protein sequence viewer Clinical Significance: Pathogenic And Likely Pathogenic Variants for the protein P99999
  :width: 800px

  Protein sequence viewer Clinical Significance: Pathogenic And Likely Pathogenic Variants for `P99999 <https://www.ebi.ac.uk/interpro/protein/UniProt/P99999/>`_