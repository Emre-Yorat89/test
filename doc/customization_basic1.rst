.. SPDX-FileCopyrightText:  PyPSA-Earth and PyPSA-Eur Authors
..
.. SPDX-License-Identifier: CC-BY-4.0

.. _customization_basic1:

#######################
<<<<<<< HEAD
2. Basic customization
#######################

A good starting point to customize your model are settings of the default configuration file `config.default.yaml`. You may want to do a reserve copy of your current configuration file and then overwrite it by a default configuration:

.. code:: bash

    .../pypsa-earth (pypsa-earth) % cp config.default.yaml config.yaml

Specify the country/region of interest
--------------------------------------

The model can be adapted to include any country, multiple countries (e.g. `Nigeria` and `Benin`) or full continents (currently whole regions, such as `Africa`, `Asia`, `Europe`, `Oceania`, `NorthAmerica`, and `SouthAmerica`, are available for simulation) using ``countries`` argument:

.. code:: yaml

    countries: ["NG", "BJ"]

Configure ``enable`` section to download/build data
---------------------------------------------------------

=======
Basic customization
#######################

The goal of this section is to show you how to make basic settings to customize the configuration file and consequently the execution of the tool.
First, it is worth spending a few words on the configuration file.
Within the work folder there is always a configuration file ( typically the file that is read by snakemake is the "config.yaml).
This type of file is used to define and customize the settings and parameters for the execution of the workflow or process, so any customization of the tool will be performed on that file. 
In the next steps we will see the basic settings in order to customize the configuration file, in case you are interested in more in-depth customization, you can refer to the configuration section in the Pypsa-Earth documentation.

Choose the type of simulation:
--------------------------------------
It is possible to run simulations with the Pypsa Distribution tool in two modes:

- tutorial mode: this is a faster simulation in which less data is used. It was created to allow users to become familiar with the tool, without necessarily having to run heavy simulations.For realistic case studies it will be necessary to run the tool in full configuration and not in tutorial one.
- full ( non-tutorial) mode: in this case a full simulation is performed and the use of committed resources is greater.

Since the tutorial mode is designed only to become familiar with the tool, and not to perform analysis in a broad sense, it is possible to run the simulation in tutorial mode for microgrids located in these nations: 

- Nigeria [NG]
- Benin [BJ]
- Botswana [BW]
- Morocco [MA]

The tutorial mode is selectable by placing within the config file:

.. code:: yaml

    tutorial: true

To perform a full simulation it will be necessary to set:

.. code:: yaml

    tutorial: false


Specify the country of interest:
--------------------------------------

Currently Pypsa-Distribution is a tool under development, how soon it will be possible to use it for the study and simulation of microgrids in all countries.
Selection of the country of interest will be possible using the "coutries" argument at the top of the config file.

.. code:: yaml

    countries: ["NG"]


Please remember,before proceeding, that as has already been mentioned, in case you are running a simulation in tutorial mode you will only be able to select one nation from NG,BJ,BW or MA; and that for realistic case studies it will be necessary to run the tool in full configuration

Configure `coordinates`
--------------------------
Currently, the tool allows us to select the microgrid coverage area by going to enter the coordinates of the vertices of the rectangular surface we want to be covered by the microgrid.
At the end of the config.yaml file you will find the microgrid list section where you can go to enter the coordinates. 
You can take advantage of the webb OpenStreetMap application to generate the coordinates.

.. code:: yaml

    microgrids_list:
        your_microgrid:
            lon_max: 41.1141
            lon_min: 41.1086
            lat_min: -2.0596
            lat_max: -2.0526


Configure ``enable`` section to download/build data
---------------------------------------------------------
The tool bases its operation on specific data obtained from open-source platforms. 
>>>>>>> dist_main
For a successful model run, ensure the download of essential open-source data, including databundle and cost data, is activated in the ``enable`` section:

.. code:: yaml

    enable:
<<<<<<< HEAD
        retrieve_databundle: true  #  Recommended 'true', for the first run. Otherwise data might be missing.
        retrieve_cost_data: true  # true: retrieves cost data from technology data and saves in resources/costs.csv, false: uses cost data in data/costs.csv
        download_osm_data: true  # If 'true', OpenStreetMap data will be downloaded for the above given countries
        build_natura_raster: false # If True, than an exclusion raster will be build
        build_cutout: false
        # If "build_cutout" : true, then environmental data is extracted according to `snapshots` date range and `countries`

After the initial run, it is recommended to set the retrieval of databundle and cost data to ``false`` to prevent unnecessary redownloading of data.

When ``build_natura_raster: false`` is utilized, the exclusion raster for protected areas is sourced from the pre-compiled ``data/natura.tiff`` file downloaded with the databundle. Conversely, if ``build_natura_raster`` is set to true, the exclusion raster, delineating areas where renewables cannot be installed, is computed using the ``build_natura_raster rule``.

When using the weather year 2013, it is recommended to use default ``build_cutout: false`` because pre-compiled cutouts are automatically downloaded with ``retrieve_databundle: true``.
On contrary, when simulating a weather year other than 2013, it is crucial to set ``build_cutout: true`` in order to generate custom cutouts. However, it is essential to first configure the `Copernicus Climate Data Store (CDS) API`. Detailed instructions for setting up the `Copernicus API` can be found in :ref:`customization_copernicus`.
After initial run and successful generation of custom cutouts, ``build_cutout`` can be switched to false to avoid reconstructing the cutout.

.. note::

    No need to configure the `Copernicus API` if the weather year 2013 is used, as pre-compiled cutouts are automatically downloaded.

    Additionally, if you encounter issues with failed ``retrieve_databundle``, you can use the following script to debug it through the command line interface (CLI):

    .. code:: bash

        .../pypsa-earth (pypsa-earth) $ python scripts/non_workflow/databundle_cli.py

Specify the weather year scope
------------------------------

=======
        retrieve_databundle: true  # Recommended 'true', for the first run. Otherwise data might be missing.
        retrieve_cost_data: true   # If true, it retrieves cost data from technology data and saves in resources/costs.csv, if false uses cost data in data/costs.csv
        download_osm_data: true  # If true, OpenStreetMap data will be downloaded for the selected countries
        download_osm_buildings: true  # If true, OpenStreetMap buildings will be downloaded for the selected countries
        build_cutout: false
        build_natura_raster: false  # If True, than an exclusion raster will be build
        
        # If "build_cutout" : true, then environmental data is extracted according to `snapshots` date range and `countries`

Regarding topics in the enable section:

- Retrive_databundle and retrive_cost_data: After the initial run, it is a good idea to set retrive databundle and cost data to false to avoid re-downloading unnecessary data.
- Build_cutout: When using weather year 2013 it is advisable to set "build_cutout: false" because the precompiled cutouts are automatically downloaded with the "retrive_databundle: true". When using a weather year other than 2013 it is essential to set "build_cutout: true" to generate custom cutouts.
    Caution: when using the Build_cutout rule, it is essential to first configure the Copernicus Climate Data Store API ( read the instructions).
    After the first run and successful custom cutout generation, build_cutout can be switched to false to avoid rebuilding the cutout.
- Build_nature_raster: When "build_nature_raster" is configured to false, the exclusion raster for protected areas is taken from the precompiled file "data/nature.tiff" downloaded with the databundle.Conversely, if "build_nature_raster" is set to "true" the exclusion raster is calculated using the "build_nature_raster" rule.
  After the initial run, it is recommended to set the retrieval of databundle and cost data to ``false`` to prevent unnecessary redownloading of data.


Specify the weather year scope
------------------------------
With these arguments, it is possible to set the time horizon of the simulation
>>>>>>> dist_main
Likewise, the example's temporal scope can be restricted (e.g. to 7 days):

.. code:: yaml

    snapshots:
        start: "2013-03-01"
        end: "2013-03-07"
        inclusive: "left" # end is not inclusive

.. note::

    Ensure that the selected date range aligns with the dates available in the cutout dataset. If the weather data within the cutouts corresponds to the year 2013, then the range of snapshots should fall within that same year.

Specify the demand year
-----------------------

<<<<<<< HEAD
Year-related parameters are also being used when specifying `load_options`:
=======
This section specifies some parameters needed to generate demand profiles. 
>>>>>>> dist_main

.. code:: yaml

    load_options:
<<<<<<< HEAD
      ssp: "ssp2-2.6"
      weather_year: 2013
      prediction_year: 2030
      scale: 1

The `weather_year` value corresponds to the weather data which was used to generate the electricity demand profiles for a selected area while `prediction_year` corresponds to the point of a `Shared Socioeconomic Pathways (SSP) <https://en.wikipedia.org/wiki/Shared_Socioeconomic_Pathways>`__ trajectory. PyPSA-Earth uses SSP2-2.6 scenario within the Shared Socioeconomic Pathways framework, which is characterized by medium challenges to mitigation and adaptation efforts, as supported in `GlobalEnergyGIS <https://github.com/niclasmattsson/GlobalEnergyGIS>`__.
The available values for `weather_year` and `prediction_year` can be checked by looking into `pypsa-earth/data/ssp2-2.6` folder. Currently, there are pre-calculated demand data for 2011, 2013, 2018 weather years and for 2030, 2040, 2050, and 2100 scenario prediction years.

Use custom demand data
----------------------

It is possible to implement custom demand profiles. It can be done by creating a dedicated custom demand sub-folder in a scenario folder `pypsa-earth/data/ssp2-2.6` and placing there a custom demand file. The name of a custom demand sub-folder should correspond to `weather_year` argument which stands in this case for general identification of a demand input. The name of a demand input file should be a continent name to which belongs a country of initerest. Both csv and nc formats can be used for demand files.

For example, to  `pypsa-earth/data/ssp2-2.6/2013_custom/`

.. note::

    For example, to provide custom inputs for Nigeria, you can put the time-series into `Africa.csv` file and place the file into `pypsa-earth/data/ssp2-2.6/2013_custom/` folder. To make it fetched, you'll need to specify `weather_year: 2013_custom` under `load_options`.

A format of the custom csv demand file should correspond to the csv files supplied with the model: there are `region_code`, `time`, `region_name` and `Electricity demand` columns, while a semicolon is used as a separator.

=======
        ssp: "ssp2-2.6"
        weather_year: 2013
        prediction_year: 2030
        scale: 1

The arguments you see are relative:
- Weather_year: sets the year referenced by the weather data for calculating electricity demand profiles for the selected area.
- Prediction_year: sets the Shared Socioeconomic Pathways (SSP) trajectory. Pypsa Earth uses the SSP2-2.6 scenario characterized by average challenges for mitigation and adaptation efforts to avoid global resgliding of about 2.6° by the end of the 21st century. Available values for weather_year and prediction_year can be checked by consulting the pypsa-earth/data/ssp2-2.6 folder
	Currently, pre-calculated demand data are available for weather years 2011, 2013, 2018 and prediction years 2030, 2040, 2050 and 2100.
>>>>>>> dist_main

Configure `atlite` section
--------------------------

<<<<<<< HEAD
To accurately model the temporal and spatial availability of renewables such as wind and solar energy, we process historical weather data using `atlite <https://atlite.readthedocs.io/en/latest/>`__ package.
Atlite configurations can be adjusted in ``config.yaml``:
=======
To accurately model both temporally and spatially renewable availabilities such as wind and solar energy, historical climate data are processed with the atlite package.
>>>>>>> dist_main

.. code:: yaml

    atlite:
        nprocesses: 4
        cutouts:
            cutout-2013-era5:
                module: era5
                dx: 0.3  # cutout resolution
                dy: 0.3  # cutout resolution
                # The cutout time is automatically set by the snapshot range.

<<<<<<< HEAD
.. note::

    No adjustments are required when utilizing pre-compiled cutouts. When using custom cutouts generated by ``build_cutout`` rule, replace all entries of ``cutout-2013-era5`` with the custom cutout name for a region of interest. For example, when simulating Kazakhstan with ``cutouts: asia-2013-era5``, every occurrence of ``cutout-2013-era5`` should be updated to ``asia-2013-era5`` which refers to ``asia-2013-era5.nc`` file generated in ``cutouts`` folder.

Please note that a temporal dimension of the cutout should be consistent with the values set for `snapshots` parameter. A time range of the cutout is determined by the parameters set when building this cutout while the time resolution corresponds to those of the used climate archives. In case of ERA5 dataset used in PyPSA-Earth by default, hourly resolution is implied.

To delve into the specifics of the provided configurations and explore additional settings, please refer to the :ref:`config` page.
There are many more configuration options beyond what is adapted for the tutorial!
=======
When you use precompiled cutouts, no editing of this section is required. 
However, when using precompiled cutouts, you must replace all "cutout-2013-era5" entries with the name of the custom cutout.
E.g.: if you simulate Kazakhstan with cutout: asia-2013-era5, each occurrence of cutout-2013-era5 should be updated to asia-2013-era5, which refers to the asia-2013-era5.nc file generated in the cutout folder.
>>>>>>> dist_main
