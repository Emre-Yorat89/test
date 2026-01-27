<<<<<<< HEAD
.. SPDX-FileCopyrightText:  PyPSA-Earth and PyPSA-Eur Authors
..
.. SPDX-License-Identifier: CC-BY-4.0
=======
..
  SPDX-FileCopyrightText: 2021 The PyPSA meets Earth authors

  SPDX-License-Identifier: CC-BY-4.0
>>>>>>> dist_main

.. _introduction:

##########################################
Introduction
##########################################

<<<<<<< HEAD
A short video explaining the logic of PyPSA-EuR, which is built on principles similar to PyPSA-Earth but tailored for Europe:

.. raw:: html

    <iframe width="832" height="468" src="https://www.youtube.com/embed/ty47YU1_eeQ" frameborder="0" allow="accelerometer; autoplay; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>

For more details on PyPSA-Earth read the below milestone paper.
For citations, please use the following BibTeX: ::

  @misc{PyPSAEarth,
  author = {Parzen, Maximilian and Abdel-Khalek, Hazem and Fedorova, Ekaterina and Mahmood, Matin and Frysztacki, Martha Maria and Hampp, Johannes and Franken, Lukas and Schumm, Leon and Neumann, Fabian and Poli, Davide and Kiprakis, Aristides and Fioriti, Davide},
  title = {PyPSA-Earth. A new global open energy system optimization model demonstrated in Africa},
  publisher = {Applied Energy},
  year = {2023},
  url = {https://www.sciencedirect.com/science/article/pii/S030626192300460},
  doi = {https://doi.org/10.1016/j.apenergy.2023.121096},
  }
=======
PyPSA-Distribution aims at providing a global, open, free, fully transparent, and reproducible energy system model for distribution applications.
It is based on the `PyPSA <https://pypsa.org/>`_ framework and uses the `OpenStreetMap <https://www.openstreetmap.org/>`_ data to create a detailed representation of the distribution energy system.

Examples of possible applications of the model are:

- **Microgrids planning**: The model can be used to plan the expansion of a network of microgrids, e.g. to integrate new renewable energy sources or to electrify heating and transport.
- **Distribution system planning**: The model can be used to plan the expansion of the distribution network, e.g. to integrate new renewable energy sources or to electrify heating and transport.
- **Distribution system operation**: The model can be used to operate the distribution network, e.g. to optimize the dispatch of distributed energy resources or to avoid congestions.
- **Distribution network tariff design**: The model can be used to design tariffs for the distribution network, e.g. to incentivize the use of renewable energy sources or to avoid congestions.
- **Are we missing something?**: Please let us know if you have any other ideas for applications of the model!

.. image:: doc/.png
  :alt: Exemple of application of the model
  :align: center
>>>>>>> dist_main


Workflow
========

<<<<<<< HEAD
The generation of the model is controlled by the workflow management system `Snakemake <https://snakemake.bitbucket.io/>`_. In a nutshell,
the ``Snakefile`` declares for each python script in the ``scripts`` directory a rule which describes which files the scripts consume and
produce (their corresponding input and output files). The ``snakemake`` tool then runs the scripts in the correct order according to the
rules' input/output dependencies. Moreover, it is able to track, what parts of the workflow have to be regenerated, when a data file or a
script is modified/updated. For example, by executing the following snakemake routine

.. code:: bash

    .../pypsa-earth % snakemake -j 1 networks/elec_s_128.nc

the following workflow is automatically executed.

.. image:: img/workflow_introduction.png
    :align: center

The **blocks** represent the individual rules which are required to create the file ``networks/elec_s_128.nc``.
Each rule requires scripts (e.g. Python) to convert inputs to outputs.
The **arrows** indicate the outputs from preceding rules which a particular rule takes as input data.

.. note::
    For reproducibility purposes, the image can be obtained through
    ``snakemake --dag networks/elec_s_128.nc | dot -Tpng -o workflow.png``
    using `Graphviz <https://graphviz.org/>`_

=======
As `PyPSA-Earth <https://pypsa-earth.readthedocs.io/en/latest/>`_,
the generation of the model is controlled by the workflow management system `Snakemake <https://snakemake.bitbucket.io/>`_. In a nutshell,
the ``Snakefile`` declares for each python script in the ``scripts`` directory a rule which describes which files the scripts consume and
produce (their corresponding input and output files). The ``snakemake`` tool then runs the scripts in the correct order according to the
rules' input/output dependencies. Moreover, it is able to track, what parts of the workflow have to be regenerated, when a data file or a
script is modified/updated. Please, refer to PyPSA-Earth documentation for more.
The following image represents the workflow performed by snakemake.
.. image:: doc/workflow.png
  :alt: Workflow Diagram
  :align: center

The blocks represent the individual rules which are required to create the file networks/elec_s_128.nc. Each rule requires scripts (e.g. Python) 
to convert inputs to outputs. The arrows indicate the outputs from preceding rules which a particular rule takes as input data.
>>>>>>> dist_main

Folder structure
================

The content in this package is organized in folders as described below; for more details, please see the documentation.

- ``data``: Includes input data that is not produced by any ``snakemake`` rule.
- ``scripts``: Includes all the Python scripts executed by the ``snakemake`` rules.
<<<<<<< HEAD
- ``resources``: Stores intermediate results of the workflow which can be picked up again by subsequent rules.
- ``networks``: Stores intermediate, unsolved stages of the PyPSA network that describes the energy system model.
=======
- ``resources``: Stores intermediate results of the PyPSA-Distribution workflow which can be picked up again by subsequent rules.
- ``networks``: Stores intermediate, unsolved stages of the PyPSA network that describes the energy system model of PyPSA-Distribution.
>>>>>>> dist_main
- ``results``: Stores the solved PyPSA network data, summary files and plots.
- ``benchmarks``: Stores ``snakemake`` benchmarks.
- ``logs``: Stores log files about solving, including the solver output, console output and the output of a memory logger.
- ``envs``: Stores the conda environment files to successfully run the workflow.


License
=======

<<<<<<< HEAD
PyPSA-Earth work is released under multiple licenses:

* All original source code is licensed as free software under `AGPL-3.0 License <https://github.com/pypsa-meets-earth/pypsa-earth/blob/main/LICENSES>`_.
=======
PyPSA-Distribution work is released under multiple licenses, equivalent to those of PyPSA-Earth.

* All original source code is licensed as free software under `GPL-3.0 License <https://github.com/pypsa-meets-earth/pypsa-earth/blob/main/LICENSE>`_.
>>>>>>> dist_main
* The documentation is licensed under `CC-BY-4.0 <https://creativecommons.org/licenses/by/4.0/>`_.
* Configuration files are mostly licensed under `CC0-1.0 <https://creativecommons.org/publicdomain/zero/1.0/>`_.
* Data files are licensed under different licenses as noted below.

<<<<<<< HEAD
Individual files contain license information in the header or in the `dep5 <.reuse/dep5>`_.
Additional licenses and urls of the data used in PyPSA-Earth:

.. csv-table::
   :header-rows: 1
   :file: configtables/licenses.csv

=======
For licenses and urls of the data used in PyPSA-Earth, please, refer to `PyPSA-Earth License section <https://pypsa-earth.readthedocs.io/en/latest/introduction.html#license>`_.
>>>>>>> dist_main

* *BY: Attribute Source*
* *NC: Non-Commercial Use Only*
* *SA: Share Alike*
