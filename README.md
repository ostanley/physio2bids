### Physio2bids

This python script was created to cconvert data from the Siemens 7T Magnetom to BIDS format. I rquires a directory of physio files (\*.puls and \*.resp). 

## Usage

```python write_physio_to_bids.py -p physio_dir -b bids_dir```

or 

```python write_physio_to_bids.py --physio_dir physio_dir --bids_dir bids_dir```

## Assumptions

This code is based on the information from: https://cfn.upenn.edu/aguirre/wiki/public:pulse-oximetry_during_fmri_scanning and makes the following assumptions:

* \*.puls and \*.resp files will be kept together in the same directory
* MDHLogStartTime and MDHLogStopTime are what should be linked to the acquisition times in the DICOMs
* A physio recording which starts before a functional run and ends after the function run is intended for that run
* The reported values for the physio data are not linked to a log of the times they were recorded and are instead assumed to be sampled at a rate specified in the json file.

