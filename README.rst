##############################################################################
Conda Content Trust: Signing and verification tools for Conda
##############################################################################

.. image:: https://github.com/conda/conda-content-trust/workflows/CI/badge.svg
  :target: https://github.com/conda/conda-content-trust/actions
  :alt: GitHub Actions
.. image:: https://codecov.io/gh/conda/conda-content-trust/branch/master/graph/badge.svg
  :target: https://codecov.io/gh/conda/conda-content-trust
  :alt: Test coverage

**What:** Based on `The Update Framework (TUF) <https://theupdateframework.io/>`_, conda-content-trust is intended to ensure that when users in the conda ecosystem obtain a package or data about that package, they can know whether or not it is trustworthy (e.g. originally comes from a reliable source and has not been tampered with).  A basic library and basic CLI are included to provide signing, verification, and trust delegation functionality.

**Why:** This exists as an alteration of TUF because of the very particular needs of the conda ecosystem.  (Developers are encouraged to *just use TUF* whenever possible!)

**Where:** This tool is general purpose.  It is currently used in conda 4.10.1+ to verify package metadata signatures when they are available (`announcement <https://www.anaconda.com/blog/conda-signature-verification>`_, `instructions <https://docs.anaconda.com/anaconda-commercial/security>`_).


**************
Installation
**************

Installation can be accomplished via conda:
  ``conda install conda-content-trust``

Or via pip:
  ``pip install conda-content-trust``

(If you intend to tinker with the code, use an editable install instead, of course: ``pip install -e .``)

========================================================================
Optional Dependencies for Producing Signatures with GPG Keys / YubiKeys
========================================================================

If you intend to *create* *GPG* key signatures (as opposed to the typical non-GPG signatures), and/or you intend to use the YubiKey interface, you will need to install two optional dependencies:
 | - ``GPG`` (any gpg client that provides command-line gpg functionality should do)
 | - ``securesystemslib`` (``pip install securesystemslib``)


*********************
Demonstration and Use
*********************

Use of the command-line utility provides help functionality::
  ``conda-content-trust --help``

You should be able to run the demo after installing:
  ``python3 demo.py``

(Portions of the demo may require the optional dependencies above.)


*******************
Testing
*******************

Each set of tests is a module in the `tests/` directory.  These can all be run with:
  ``pytest``
