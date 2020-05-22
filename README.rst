######################
InterPro Documentation
######################

This repository is the source code for InterPro documentation hosted on  `Read The Docs <https://interpro-documentation.readthedocs.io/en/latest/>`_.

************
Installation
************

.. code-block:: bash

  # download a copy of the document repository
  git clone https://github.com/ProteinsWebTeam/interpro-docs.git
  cd interpro-docs
  # set-up python project dependancies
  python3 -m venv venv
  source ./venv/bin/activate
  pip install -r requirements.txt
  # build the docs (this will have to be repeated on every edit)
  sphinx-build docs build
  # or for a dynamic auto reloading
  sphinx-autobuild docs build
  # view documentation at
  http://localhost:8000/


*****************
How to Contribute
*****************

Please get in touch with us at interpro-help@ebi.ac.uk with details of how you'd like to help and we'll get back to you.

*******
Contact
*******

interpro-help@ebi.ac.uk
