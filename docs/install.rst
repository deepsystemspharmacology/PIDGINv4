Setup and Installation
==========================================================================================

Development and documentation occurs on GitHub_.

PIDGIN is currently only compatible with Python 2.7.x.
It also has the following dependencies:

Required dependencies
~~~~~~~~~~~~~~~~~~~~~

- NumPy_
- SciPy_
- RDKit_
- Scikit-learn_
- Standardiser_
- python_utilities_


Install with Conda
~~~~~~~~~~~~~~~~~~

Follow these steps on Linux/OSX:

1. ``Download and install Anaconda2 for Python 2.7 from https://www.continuum.io/downloads``

2. Open terminal in Mac/Linux and run ``conda env create -f pidgin4_env.yml --name pidgin4_env``

* N.B. Rdkit may not import on some systems due to a bug. If this happens upgrade to the latest version of conda before creating the above environment using: ``conda update conda``

* N.B. Installs the IMI eTOX `flatkinson standardiser`_ (replaces ChemAxon's standardizer used in previous PIDGIN versions) and statsmodels for p-value correction in predict_enriched.py

If you encounter an issue (usually occurs when installing the environment on non-Linux systems) try the following:

``conda create -c rdkit -c conda-forge --name pidgin4_env python=2.7 rdkit scikit-learn=0.19.0 pydot graphviz standardiser statsmodels``

3. Now run: ``source activate pidgin4_env`` (This activates the PIDGINv4 virtual environment. N.B This is required for each new terminal session in order to run PIDGIN in the future)

4. Navigate the directory you wish to install PIDGINv4 and in Mac/Linux terminal run ``git clone https://github.com/BenderGroup/PIDGINv4.git`` (recommended) or download/extract the zip from `GitHub`_ webpage (not recommended due to inability to pull updates)

5. (17GB) Download and unzip `no_ortho.zip`_ (md5sum: bddc0794bd8d04e106fe8f9e4b9d283) into the PIDGINv4 main directory (leave all subsequent files compressed)

6. (optional 43GB) Models are also available when mapping data between orthologues, as in [1]_. N.B The files are 43GB and many models are based solely on orthologue data. To include this functionality, download `ortho.zip`_ (md5sum: 58db44625f7906ef17f3d79537771aa3) to the PIDGINv4 main directory and unzip `ortho.zip`_ (leave all subsequent files compressed)

* N.B Depending on bandwidth, Step 5/6 may take some time

NOTE: For the older (ChEMBL 26) models, please download and unzip `no_ortho_ChEMBL26.zip`_ and/or `ortho_ChEMBL26.zip`_ ensuring you clone the ChEMBL26 branch of PIDGINv4 (https://github.com/BenderGroup/PIDGINv4/tree/ChEMBL_26) and move the model directory/s to your local PIDGIN ChEMBL26 directory.


Filetree structure
~~~~~~~~~~~~~~~~~~

Once the models are downloaded and the main zip uncompressed, you should find the 
following filetree structure within the PIDGINv4 directory (located for this snippet at
``$PV4``) if both the optional orthologs (ortho) and models without orthologs (no_ortho)
files are used:

.. code-block:: shell-session

	$PV4 tree -L 2
	.
	├── biosystems.txt
	├── DisGeNET_diseases.txt
	├── docs
	│   ├── conf.py
	│   ├── dev
	│   ├── index.rst
	│   ├── install.rst
	│   ├── make.bat
	│   ├── Makefile
	│   ├── overview.rst
	│   ├── substitutions.rst
	│   └── usage
	├── examples
	│   ├── test2.smi
	│   └── test.smi
	├── LICENSE
	├── nontoxic_background.csv
	├── no_ortho
	│   ├── ad_analysis
	│   ├── bioactivity_dataset
	│   ├── pkls
	│   ├── training_log.txt
	│   ├── training_results
	│   └── uniprot_information.txt
	├── no_ortho.zip
	├── ortho
	│   ├── ad_analysis
	│   ├── bioactivity_dataset
	│   ├── check_ad2.py
	│   ├── check_ad.py
	│   ├── pkls
	│   ├── training_log.txt
	│   ├── training_results
	│   └── uniprot_information.txt
	├── ortho.zip
	├── pidgin4_env.yml
	├── sim_to_train.py
	├── predict_enriched.py
	├── predict.py
	└── README.rst

.. [1] |mervin2018|

.. include:: substitutions.rst
