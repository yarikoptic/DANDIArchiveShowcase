# DANDI Archive Showcase

Scripts for interacting with the [DANDI Archive](https://www.dandiarchive.org/), particularly from [OSBv2](https://docs.opensourcebrain.org/OSBv2/Overview.html).
 For information about the NWB dandisets that is generated by the scripts in this repo, please visit [here](validation_folder/README.md).

## Installation instruction
The scripts in this repo work best in an
[Anaconda](https://www.anaconda.com/distribution/#download-section) environment, and [git](https://git-scm.com/downloads) is required for running one of the packages, 
so please make sure they are installed and added to the system path. 
In addition, a local installation of [NWB Explorer](https://github.com/MetaCell/nwb-explorer) is advised for the purpose of testing files' compatibility with the app.

In your git terminal, navigate to the directory in which you want to clone the DandiArchiveSHOWCASE repo. Run the following commands:

```commandline
conda create --name dandiarchiveshowcase python=3.9 --yes
conda activate dandiarchiveshowcase
conda install --channel conda-forge datalad h5py
git clone https://github.com/OpenSourceBrain/DANDIArchiveShowcase
git clone --branch development https://github.com/MetaCell/nwb-explorer
pip install --requirement DANDIArchiveShowcase/requirements.txt
pip install --editable nwb-explorer
python nwb-explorer/utilities/install.py
cd DANDIArchiveShowcase
```

## Scripts information
The nwb_table_readme.py script allows one to parse through all the dandisets in DANDIArchive, extract metadata information
and validate files in each dandiset against NWBInspector, as well as testing their compatibility with NWB Explorer. 
Validation results and summary information are saved in a directory called validation_folder.
```
nwb_table_readme.py
Usage: python nwb_table_readme.py [OPTIONS]

  Parse through all the dandisets in DANDIArchive, extract metadata information and
   validate files in each dandiset against NWBInspector.
   
Options:
  --no_download                 Files will not be downloaded for testing if so chosen
  --no_sizelimit                No size limit will be capped for downloading files if so chosen
  --dandiset_limit              Only process first 10 dandisets if so chosen'
  --update_readme_option        Update readme file after summary file is created
  --update_readme_only          Update readme file without creating summary file
```