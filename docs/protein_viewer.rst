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
:ref:`structure <structure_page>` pages). It summarises the InterPro entries (IPR) and 
member database signatures matches to the protein or structure
being looked at, represented by the grey bar at the top of the viewer. 

The *AlphaFold confidence* track is displayed in the protein sequence viewer in the :ref:`protein page <protein_page>` 
and in the :ref:`AlphaFold subpage <alphafold1>` when a predicted structure is available.

By default, a summarised view of the InterPro entries (IPR) and member database signatures matches is displayed.
It provides information about the protein family membership in the Families category ([6] in the figure below), the 
different domains that compose the protein in the Domains category [7]. In addition, Intrinsically disordered regions 
from `MobiDB <https://www.mobidb.org/>`_ [8],
conserved residues provided by the CDD, SFLD and PIRSR databases [9] and pathogenic variants [10] are also displayed when available.

The top line in the *Domains* track shows a summary of the domains that compose the protein. This representation is 
generated automatically using the type of the member databases models, which might differ from the InterPro entries types. 
When multiple models are overlapping, the representative domain is chosen by selecting the model covering the longest 
region of the protein. Be aware that in case of models made of multiple fragments, not all the fragments are necessarily 
chosen as representative, they are considered as individual entities for the selection.

Information about pathogenic and likely pathogenic residue variants in protein sequences is available under the **Pathogenic And Likely 
Pathogenic Variants** category of the viewer. Please note that the data can differ from the  data provided on the UniProt website as we 
are applying a *Clinical significance* filter, which is different from the one used by UniProt. 

.. protein used: https://wwwdev.ebi.ac.uk/interpro/protein/UniProt/P05067/

.. figure:: images/protein_viewer/pv_help.png
  :alt: Protein sequence viewer summary
  :width: 800px

  Summary view of the InterPro annotations of a protein.

Various options, make it easy to work with (as illustrated in the figure above):

1. Clicking on the Full screen button at the top of the viewer will switch to full screen view.

2. The viewer can be zoomed in and out by:

  a. Clicking the two buttons (+ and -) at the top right corner.
  b. Dragging the grey scale at the top to the desired positions on both left and right sides
  c. Pressing the [Ctrl] key and scroll through the viewer 

3. The viewer can be expended to display all the annotations by clicking on **Show all annotations** (you can try it for `P05067 <https://www.ebi.ac.uk/interpro/protein/UniProt/P05067/>`_ shown in the figure above). Data include, when available:

- Expended view of the Families and Domains matches
- Conserved sites
- Coiled-coils from COILS, Signal peptides from `SignalP <https://services.healthtech.dtu.dk/service.php?SignalP-5.0>`_ and/or Phobius, Transmembrane regions from `Phobius <https://phobius.sbc.su.se/>`_ and/or `TMHMM <https://services.healthtech.dtu.dk/service.php?TMHMM-2.0>`_.
- Cytoplasmic/non-cytoplasmic domains from Phobius
- Spurious proteins from :doc:`AntiFam </antifam>`
- `Pfam-N annotations <hxfam.wordpress.com/2024/05/31/pfam-n-version-3-enhancing-pfam-coverage-of-uniprot-with-computer-vision-deep-learning-techniques/>`_ result from a deep learning methodology developed by the Google Research team led by Dr Lucy Colwell to increase the Pfam coverage of protein sequences.
- `Funfam <https://github.com/UCLOrengoGroup/cath-funfam-docs>`_, provided by CATH-Gene3D, is an automatically generated profile HMM database, with FunFams entries segregated by an entropy-based approach  that distinguishes different patterns of conserved residues, corresponding to differences in functional determinants.
- Short linear motifs from `ELM <http://elm.eu.org/>`_
- External resources annotations that are fetched directly from the resource API:

  - Intrinsically disordered proteins from `DisProt <https://www.disprot.org/>`_
  - Tandem repeat from `RepeatsDB <https://repeatsdb.bio.unipd.it/>`_

4. More options that customise the viewer are grouped under **Options** dropdown.

.. figure:: images/protein_viewer/pv_options_dropdown.png
  :alt: Protein sequence viewer options
  :align: left
  :width: 350px

A. **Colour By** allows to change the colours in which the InterPro entries and signatures bars based on accession, member database or domain relationship. 

B. The labels on the right side of the viewer can be customised. The **Accession** labels are shown by default. To see names and/or short names along with accession, the name/short name checkboxes should be ticked or if the user prefers to see the names/short names alone, the respective options should be selected.

C. **Save as image** allows to take a snapshot of the viewer and is saved as an image (.png).

D. The tooltips are shown when hovering over each bar. They contain the signature accession and name, and the InterPro entry accession when the signature is integrated in an InterPro entry, which can be clicked on to access the InterPro entry page. The tooltips can be disabled by unchecking the **Tooltip Active** option.

.. figure:: images/protein_viewer/pv_tooltip.png
  :alt: Protein sequence viewer tooltip
  :width: 800px

  Tooltip example.

5. Clicking on the header of a category expends or hides the matches for the entire category.

When zoomed in, panning can be achieved by either dragging the scale at the top or by dragging any bar in the desired direction (see figure below).

.. figure:: images/protein_viewer/pv_panning.png
  :alt: Protein sequence viewer panning
  :width: 800px
