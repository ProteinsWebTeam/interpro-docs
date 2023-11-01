#########################
AI-generated descriptions
#########################

To address the absence of annotations for specific families, we've been exploring 
the application of GPT-4, a Large Language Model (LLM) developed by OpenAI, 
for generating text summaries. We've devised a strategy that involves 
extracting description lines and function comments from Swiss-Prot entries 
within the family and aggregating them into a prompt submitted to the OpenAI API. 
We evaluated that GPT-4 generally produces reasonably high-quality summaries 
when supplied with sufficient information from Swiss-Prot. 

An example of input prompt for `the RBM25 protein family (PTHR18806) <https://www.ebi.ac.uk/interpro/entry/panther/PTHR18806/>`_ is shown below:

.. code-block:: text

    A protein family matches 3 Swiss-Prot proteins. The proteins are listed below:

    1. US107_SCHPO
    Name: U1 snRNP-associated protein usp107
    Comments (grouped by topic and separated by semicolons):
        - Function: Component of the U1 snRNP particle, which recognizes and binds 
          the 5'-splice site of pre-mRNA. Together with other non-snRNP factors, 
          U1 snRNP forms the spliceosomal commitment complex, that targets pre-mRNA 
          to the splicing pathway
    2. RBM25_MOUSE
    Name: RNA-binding protein 25
    Comments (grouped by topic and separated by semicolons):
        - Domain: The PWI domain binds nucleic acids with significant help from 
          its N-terminal flanking basic region. It has an equal preference for 
          binding to single- or double-stranded species, and it contributes to 
          RBM25 role in modulation of alternative splicing, maybe by mediating 
          RNA-dependent association with LUC7L3
        - Function: RNA-binding protein that acts as a regulator of alternative 
          pre-mRNA splicing. Involved in apoptotic cell death through the regulation 
          of the apoptotic factor BCL2L1 isoform expression. Modulates the ratio 
          of proapoptotic BCL2L1 isoform S to antiapoptotic BCL2L1 isoform L mRNA expression. 
          When overexpressed, stimulates proapoptotic BCL2L1 isoform S 5'-splice 
          site (5'-ss) selection, whereas its depletion caused the accumulation 
          of antiapoptotic BCL2L1 isoform L. Promotes BCL2L1 isoform S 5'-ss usage 
          through the 5'-CGGGCA-3' RNA sequence. Its association with LUC7L3 
          promotes U1 snRNP binding to a weak 5' ss in a 5'-CGGGCA-3'-dependent manner. 
          Binds to the exonic splicing enhancer 5'-CGGGCA-3' RNA sequence located 
          within exon 2 of the BCL2L1 pre-mRNA
    3. RBM25_HUMAN
    Name: RNA-binding protein 25
    Comments (grouped by topic and separated by semicolons):
        - Function: RNA-binding protein that acts as a regulator of alternative 
          pre-mRNA splicing. Involved in apoptotic cell death through the regulation 
          of the apoptotic factor BCL2L1 isoform expression. Modulates the ratio 
          of proapoptotic BCL2L1 isoform S to antiapoptotic BCL2L1 isoform L mRNA 
          expression. When overexpressed, stimulates proapoptotic BCL2L1 
          isoform S 5'-splice site (5'-ss) selection, whereas its depletion caused 
          the accumulation of antiapoptotic BCL2L1 isoform L. Promotes 
          BCL2L1 isoform S 5'-ss usage through the 5'-CGGGCA-3' RNA sequence. 
          Its association with LUC7L3 promotes U1 snRNP binding to a weak 5' ss 
          in a 5'-CGGGCA-3'-dependent manner. Binds to the exonic splicing 
          enhancer 5'-CGGGCA-3' RNA sequence located within exon 2 of 
          the BCL2L1 pre-mRNA. Also involved in the generation of an abnormal 
          and truncated splice form of SCN5A in heart failure
        - Domain: The PWI domain binds nucleic acids with significant help 
          from its N-terminal flanking basic region. It has an equal preference 
          for binding to single- or double-stranded species, and it contributes 
          to RBM25 role in modulation of alternative splicing, maybe 
          by mediating RNA-dependent association with LUC7L3

    Additionally, the family has been annotated with the following GO terms:
    - GO:0003729: mRNA binding
    - GO:0000381: regulation of alternative mRNA splicing, via spliceosome
    - GO:0005681: spliceosomal complex

With the release of InterPro 97.0, we've successfully generated descriptions 
for approximately 5,500 unintegrated PANTHER families. We intend to further explore 
leveraging Large Language Models to generate summaries for families 
within other member databases and InterPro entries. 

**Please note that our approach to generate descriptions is subject to change in the future.**