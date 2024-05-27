# [Ifremer DOI](https://ocean-indien.ifremer.fr/)

## [Plancha project](https://ocean-indien.ifremer.fr/en/Projects/Technological-innovations/PLANCHA-2021-2023)

The main objective of the Plancha project (Planche instrumentée pour l'évaluation de l'état de santé des Habitats récifaux de la biodiversité associée par ADNe) is to map the bathymetry and major morphotype classes (according to scenario 2 of the [Global Coral Reef Monitoring Network](https://gcrmn.net/)) for the back reef depressions and outer slopes of Reunion Island.

Acquiring data on coral ecosystems is a major challenge in the context of global change and the impacts of rising ocean temperatures and acidification, as well as increasing anthropogenic pressures. The ability to monitor these ecosystems is either via regular scientific monitoring along transects by divers, and therefore very localized, or by telemetry tools (drones, aerial tracking, satellite) which are either expensive or unable to produce a fine-scale estimate of habitat modifications.

This project proposes to use an innovative bathymetric and habitat/species data acquisition platform and environmental DNA methods to map Réunion's reef ecosystems and their biodiversity.


The Plancha project collects raw data from the field, which is stored in a folder called plancha-session structured as follows: 

```text
YYYYMMDD_COUNTRYCODE-optionalplace_device_session-number 
├── DCIM :  folder to store videos and photos depending on the media collected. 
├── GPS :  folder to store any positioning related file. If any kind of correction is possible on files (e.g. Post-Processed Kinematic thanks to rinex data) then the distinction between device data and base data is made. If, on the other hand, only device position data are present and the files cannot be corrected by post-processing techniques (e.g. gpx files), then the distinction between base and device is not made and the files are placed directly at the root of the GPS folder. 
│   ├── BASE :  files coming from rtk station or any static positioning instrument. 
│   └── DEVICE : files coming from the device. 
├── METADATA : folder with general information files about the session. 
├── PROCESSED_DATA : contain all the folders needed to store the results of the data processing of the current session. 
│   ├── BATHY :  output folder for bathymetry raw data extracted from mission logs. 
│   ├── FRAMES :  output folder for georeferenced frames extracted from DCIM videos. 
│   ├── IA :  destination folder for image recognition predictions. 
│   └── PHOTOGRAMMETRY :  destination folder for reconstructed models in photogrammetry. 
└── SENSORS : folder to store files coming from other sources (bathymetry data from the echosounder, log file from the autopilot,  mission plan etc.).      
```

The raw data are processed by [plancha-workflow](https://github.com/SeatizenDOI/plancha-workflow), then predictions are made using [plancha-inference](https://github.com/SeatizenDOI/plancha-inference).

If you want to visualize the predictions, you can load the plancha-session into fiftyone with [fiftyone-tools](https://github.com/SeatizenDOI/fiftyone-tools).
You can also upload the data to zenodo with [zenodo-tools](https://github.com/SeatizenDOI/zenodo-tools).
