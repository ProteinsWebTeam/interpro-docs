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
:ref:`structure <structure_page>` pages). It summarises the InterPro entries (IPR) (top colored
bar) and member database signatures matches to the protein or structure
being looked at, represented by the grey bar at the top of the viewer, categorised by :ref:`entry_types`. 

The purple/grey bar below the amino acids indicates the predicted hydrophobicity of the sequence residues. 
When zoomed in at the residue level and hovering, a tooltip shows hydrophobicity score, using the 
`Wimley–White whole residue hydropathy scale <https://en.wikipedia.org/wiki/Hydrophobicity_scales>`_  
(the more positive the value, the more hydrophobic is the amino acid). 
The color scale varies from -3 (colored as bright yellow) for hydrophilic residues and 3 (colored as 
bright blue) for hydrophobic ones.


.. protein used: https://www.ebi.ac.uk/interpro/protein/UniProt/A0R5X8/

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

B. The labels on the right side of the viewer can be customised. The **Accession** labels are shown by default. To see names along with accession, the name checkbox should be ticked or if the user prefers to see the names alone, the respective options should be selected.

C. **Snapshot** has two options: **Save as image** allows to take a snapshot of the viewer and is saved as an image (.png). **Print** allows the user to print the viewer, thus supporting the download in PDF format.

D. **Collapse All** allows to collapse all the signatures bars displayed in the viewer at once to only display the InterPro entries bars. 

.. figure:: images/protein_viewer/pv_collapsed_tracks.png
  :alt: Protein sequence viewer collapsed
  :width: 800px

  Collapsed categories view.

E. The tooltips are shown when hovering over each bar. They can be disabled by unchecking the **Tooltip Active** option.

.. figure:: images/protein_viewer/pv_tooltip.png
  :alt: Protein sequence viewer toolti
  :width: 800px

  Tooltip example.

4. Residues annotations are provided by the CDD, SFLD and PIRSR databases.

5. On the :ref:`protein_page`, clicking on the **Fetch conservation** button, will display the conservation information based on the PANTHER signatures. 
The conservation scores are generated using the following process: 

- The HMM model from the PANTHER database is run against the SwissProt database using hmmsearch, generating an HMM profile and a :ref:`logo <signature>` (graphical representation of the amino acid conservation).
- The conservation score for each residue is determined, from the logo data, using the following formula: :math:`\frac {\sum (height\_arr)} {max\_height\_theory} \times 10`
- The model is aligned against the protein sequence.

.. figure:: images/protein_viewer/pv_conservation.png
  :alt: Protein sequence viewer conservation track
  :width: 800px

6. Clicking on the header of a category (say Unintegrated) hides the bars for the entire category.

When zoomed in, panning can be achieved by either dragging the scale at the top or by dragging any bar in the desired direction (see figure below).

.. figure:: images/protein_viewer/pv_panning.png
  :alt: Protein sequence viewer panning
  :width: 800px


