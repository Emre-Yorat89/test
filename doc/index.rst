<<<<<<< HEAD
.. SPDX-FileCopyrightText:  PyPSA-Earth and PyPSA-Eur Authors
..
.. SPDX-License-Identifier: CC-BY-4.0

=======
>>>>>>> dist_main
.. PyPSA meets Earth documentation master file, created by
   sphinx-quickstart on Sat May 15 22:52:54 2021.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

<<<<<<< HEAD
Welcome to the PyPSA-Earth documentation!
================================================


.. image:: https://img.shields.io/github/v/release/pypsa-meets-earth/pypsa-earth?include_prereleases
    :alt: GitHub release (latest by date including pre-releases)

.. image:: https://github.com/pypsa-meets-earth/pypsa-earth/actions/workflows/test.yml/badge.svg
    :target: https://github.com/pypsa-meets-earth/pypsa-earth/actions/workflows/test.yml
    :alt: CI

.. image:: https://readthedocs.org/projects/pypsa-earth/badge/?version=latest
    :target: https://pypsa-earth.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status

.. image:: https://img.shields.io/github/repo-size/pypsa-meets-earth/pypsa-earth
    :alt: GitHub repo size

.. image:: https://img.shields.io/badge/License-AGPLv3-blue.svg
    :target: https://www.gnu.org/licenses/agpl-3.0
    :alt: License

.. image:: https://api.reuse.software/badge/github.com/pypsa-meets-earth/pypsa-earth
    :target: https://api.reuse.software/info/github.com/pypsa-meets-earth/pypsa-earth
    :alt: REUSE
=======
Welcome to the PyPSA-Distribution documentation!
================================================

.. note::
    This documentation is under construction and will be updated soon!
    Anyone interested in the project is welcome to join and collaborate with us!

.. image:: https://img.shields.io/github/v/release/pypsa-meets-earth/pypsa-distribution?include_prereleases
    :alt: GitHub release (latest by date including pre-releases)

.. image:: https://github.com/pypsa-meets-earth/pypsa-distribution/actions/workflows/ci-linux.yaml/badge.svg
    :target: https://github.com/pypsa-meets-earth/pypsa-distribution/actions

.. image:: https://readthedocs.org/projects/pypsa-distribution/badge/?version=latest
    :target: https://pypsa-distribution.readthedocs.io/en/latest/?badge=latest
    :alt: Documentation Status

.. image:: https://img.shields.io/github/repo-size/pypsa-meets-earth/pypsa-distribution
    :alt: GitHub repo size

.. image:: https://img.shields.io/badge/License-GPLv3-blue.svg
    :target: https://www.gnu.org/licenses/gpl-3.0
>>>>>>> dist_main

.. image:: https://img.shields.io/badge/code%20style-black-000000.svg
    :target: https://github.com/psf/black
    :alt: Code style Black

<<<<<<< HEAD
.. image:: https://results.pre-commit.ci/badge/github/pypsa-meets-earth/pypsa-earth/main.svg
    :target: https://results.pre-commit.ci/latest/github/pypsa-meets-earth/pypsa-earth/main
=======
.. image:: https://results.pre-commit.ci/badge/github/pypsa-meets-earth/pypsa-distribution/main.svg
    :target: https://results.pre-commit.ci/latest/github/pypsa-meets-earth/pypsa-distribution/main
>>>>>>> dist_main
    :alt: Pre-commit CI-status

.. image:: https://img.shields.io/discord/911692131440148490?logo=discord
    :target: https://discord.gg/AnuJBk23FU
    :alt: Discord

.. image:: https://img.shields.io/badge/Google%20Drive-4285F4?style=flat&logo=googledrive&logoColor=white
    :target: https://drive.google.com/drive/folders/1U7fgktbxlaGzWxT2C0-Xv-_ffWCxAKZz
    :alt: Google Drive

*Motivation*. Closed-source models are the current standard for most policy and industry decisions. However, open models have proven to be
competitive alternatives that promote science, robust technical analysis, collaboration and transparent policy decision making.
Yet, two issues slow the adoption: open models are often designed with limited geographic scope, hindering synergies to collaborate,
or are based on low spatially resolved data, limiting their utility.

<<<<<<< HEAD
PyPSA-Earth is the first open-source global cross-sectoral energy system model with high spatial and temporal resolution. The workflow
provide capabilities for modelling the energy systems of any country in the world, enabling large-scale collaboration and transparent
analysis for an inclusive and sustainable energy future. PyPSA-Earth is suitable for both operational studies and capacity expansion
studies. Its sector-coupled modeling capabilities enable features for the detailed optimization of multi-energy systems, covering
electricity, heating, transport, industry, hydrogen and more.

*PyPSA meets Earth initiative* members are maintaining the *PyPSA-Earth* repository as well as many other tools.
The `website <https://pypsa-meets-earth.github.io/>`_ provides more context of the initiative and the associated projects.

.. list-table::
   :width: 100%
   :class: borderless

   * - .. image:: https://forum.openmod.org/uploads/db8804/original/1X/ddf041d1b98ca8f8c310f1c6393ec426ab5594cf.png
     - .. image:: https://forum.openmod.org/uploads/db8804/original/1X/940b2673cfc31c4a6f01b7908f546d39d67df27e.png
     - .. image:: https://forum.openmod.org/uploads/db8804/original/1X/6af089c376b19b72ad148e4e4326c162b94db68f.png

**Figure:** Example power systems build with PyPSA-Earth. See images of ~193 more countries at https://zenodo.org/records/10080766

=======
*PyPSA-Distribution* aims to promote open-source global energy system model at distribution scale with data in high spatial and temporal resolution.
It enables large-scale collaboration by providing a tool that can model the distribution system of any region in the world.
This work leverages on significant previous work by PyPSA-Earth, PyPSA-Eur and the references and contributions discussed in the repository.
from the European PyPSA-Eur model using new data and functions. It is suitable for operational as well as combined generation,
storage and transmission expansion studies. We work hard to extend the PyPSA-Earth model by end of this year to include sector-coupling,
myopic and perfect pathway expansion capabilities.

Example of desired studies are: microgrids planning, distribution system planning, distribution system operation, distribution network tariff design, ...
**Are we missing something?** Please let us know if you have any other ideas for applications of the model!

*PyPSA meets Earth initiative* members are maintaining the *PyPSA-Distribution* repository.
The `website <https://pypsa-meets-earth.github.io/>`_ provides more context of the initiative and the associated projects. 
>>>>>>> dist_main

==============
Get Involved
==============

<<<<<<< HEAD
There are multiple ways to get involved and learn more about our work:
    1. **Join our forum** and communication platform on `PyPSA-meets-Earth <https://discord.gg/AnuJBk23FU>`__ Discord Server
    2. **Chat on Discord with us** in the following meetings:
        - General initiative meeting for project news and `high-level code updates <https://docs.google.com/document/d/1r6wm2RBe0DWFngmItpFfSFHA-CnUmVcVTkIKmthdW3g/edit?usp=sharing>`__. Held every `fourth Thursday 16-17:00 (UK time) <https://drive.google.com/file/d/1naH4WwW9drkOkOJ3PLO4fyWdkZQi5-_w/view?usp=share_link>`__ and is a perfect place to meet the community and get a high-level update on PyPSA ecosystem relevant for PyPSA-Earth developments.
        - Weekly developers meetings
            - Eastern-Hemisphere friendly *Morning meeting* every `Thursday at 09:00 (UK time) <https://drive.google.com/file/d/1PDdmjsKhzyGRo0_YrP4wPQkn2XTNh6jA/view?usp=share_link>`__.
            - Western-Hemisphere friendly *Evening meeting* every `Thursday 16:00 (UK time) <https://drive.google.com/file/d/1gaLmyV4qGPXsogkeRcAPWjC0ESebUxU-/view?usp=share_link>`__. Every forth Thursday is replaced by the General initiative meeting which has a more high-level perspective, but you can also join to discuss more particular questions.
    3. **Look at public materials** at `google Drive <https://drive.google.com/drive/folders/13Z8Y9zgsh5IZaDNkkRyo1wkoMgbdUxT5?usp=sharing>`__ to share to minutes, presentations, lists and documents. Feel gree to get a look!
    4. **Notify your interest** to on-demand meetings:
        - Demand creation and prediction meeting
        - AI asset detection meeting
        - Outreach meeting for planning, discussing events, workshops, communication, community activities
    5. Join us and **propose your stream**.
=======
Discussions on the PyPSA-Distribution tool are hosted on the `PyPSA meets Earth Discord <https://discord.gg/AnuJBk23FU>`_.

The recurrent meeting on PyPSA-Distribution is every second Tuesday at 17:00 AM (CEST time) on Discord, please reach out and join! A calendar invitation may be loaded `here <https://drive.google.com/file/d/1qGsUOKfoBt3FtXnEXiiLC-H16DiQvyVy/view?usp=drive_link>`_.
>>>>>>> dist_main

=============
Documentation
=============

**Getting Started**

* :doc:`introduction`
* :doc:`installation`
<<<<<<< HEAD
* :doc:`tutorial_electricity`
* :doc:`tutorial_sector`
* :doc:`model_customization`
* :doc:`custom_data`
* :doc:`data_workflow`
* :doc:`notebooks`
=======
* :doc:`short_tutorial`

>>>>>>> dist_main

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Getting Started

   introduction
   installation
<<<<<<< HEAD
   tutorial_electricity
   tutorial_sector
   model_customization
   custom_data
   optimization
   data_workflow
   notebooks

**Configuration**

* :doc:`wildcards`
* :doc:`configuration`
* :doc:`costs`
=======
   short_tutorial

**Model Costumization**

* :doc:`customization_basic`
* :doc:`Run_your_personal_case`
  
>>>>>>> dist_main

.. toctree::
   :hidden:
   :maxdepth: 2
<<<<<<< HEAD
   :caption: Configuration

   wildcards
   configuration
   costs

**Work flow and API**

* :doc:`structure`
* :doc:`rules_overview`
=======
   :caption: Model Costumization

    customization_basic
    Run_your_personal_case



.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Model Costumization

    customization_basic


**Work flow and API**

>>>>>>> dist_main
* :doc:`api_reference`

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Work flow and API

<<<<<<< HEAD
   structure
   rules_overview
   api_reference

**Advanced Usage**

* :doc:`monte_carlo`

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Advanced Usage

   monte_carlo

**Support and Contributing**

* :doc:`release_notes`
* :doc:`how_to_contribute`
* :doc:`software_hints`
* :doc:`learning_materials`

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Support

   release_notes
   how_to_contribute
   software_hints
   learning_materials

**References**

* :doc:`users_list`
* :doc:`project_structure_and_credits`
* :doc:`talks_and_papers`
=======
   api_reference

**Help and References**

* :doc:`release_notes`
* :doc:`how_to_contribute`
>>>>>>> dist_main

.. toctree::
   :hidden:
   :maxdepth: 2
   :caption: Project Info

<<<<<<< HEAD
   users_list
   project_structure_and_credits
   talks_and_papers
=======
   release_notes
   how_to_contribute
   
>>>>>>> dist_main
