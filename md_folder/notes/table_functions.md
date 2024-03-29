---
layout: page
title: Table of functions
permalink: /functions_table/
nav_order: 3
parent: Supplementary
---
# Table of functions



| function | description | output |
|----------|-------------|--------|
| convert_to_BIDS() | Wrapper function for the whole workflow described below. Performs the setup of the 'user_settings.R' file, DICOM conversion, <br> reads the json sidecar files, starts the 'sequence mapper', copies the file into BIDS standard, creates a diagnostic dashboard and runs the 'Shiny BIDS' viewer. | All the outputs are described below. |
| select_user_settings_file() | Select a 'user_settings.r' file or create one with a point-and-click workflow. | The 'user_settings.R' file and the path to it. |
| prepare_environment() | Uses the input from the 'user_settings.R' file to create all environment variables and runs some checks on the data. | Creates environment variables and dataframes. |
| install_dcm2niix() | Downloads and unpacks 'dcm2niix' cite{Li2016} to the output folder. | Downloads dcm2niix to the output folder.  |
| dcm2nii_converter_anon() | Converts the DICOM images to NIfTI and removes all sensitive information from the header and the json sidecar files. | NIfTI (anonymized header), json sidecar (anonymized) |
| dcm2nii_converter_json() | Extracts only the json sidecar files with the sensitive information from the DICOM images. | json sidecar |
| read_json_headers() | Reads all json sidecars, builds a dataframe containing all this information and saves it. | sequence_overview.tsv, json_metadata.tsv  |
| sequence_mapper() | Starts the 'sequence mapper' shiny app to edit all unique sequence filenames to BIDS. | sequence_map.tsv  |
| check_sequence_map() | Checks if all entries of the 'sequence mapper' were edited. | 
| copy2BIDS() | Copies and renames the files from the temporary folder to a BIDS sourcedata folder. Creates other required BIDS files. | copy2BIDS.tsv, CHANGES, README, dataset_description.json, participants.json, participants.tsv  |
| start_bids_validator() | Starts the BIDS-Validator in Docker (in Docker is installed) on the BIDS folder, otherwise the [BIDS-Validator](https://bids-standard.github.io/bids-validator/) website is launched. | Diagnostic output in the terminal about the BIDS validity of the dataset. |
| run_shiny_BIDS() | Starts the 'Shiny BIDS' MR viewer app. This function can also be used on other datasets, when giving a BIDS path as argument. | 
| delete_temp_nii_files() | Asks the user, if the temporary files should be deleted. Only recommended, when all data is converted and BIDS validity is ensured. | 
