---
layout: page
title: Diagnostic Files
permalink: /diagnostic_files/
nav_order: 4
parent: Supplementary
---
# Table of diagnostic files



| filename | description |variables |
|----------|-------------|-----------|
| dicom_paths.tsv | Output of the 'prepare_environment()' function.  <br> Shows the extracted dicom folders, input and output paths, and the applied regular expressions. | Take care, that your "subject/group/session_id" matches the regular expressions.  <br> Inspect the 'output_path' variables to find out, where the data will be saved after converting by dcm2niix cite{Li2016}.  <br> The 'rest_string' variables contain the removed information from the subject names.  |
| json_metadata.tsv | Output of the 'read_JSON_headers()' function.  <br> The 'create_dashboard()' uses the information from this file. | Subject, group, session and sequence variables for identification and all physical MR parameters from the JSON sidecar.  |
| sequence_overview.tsv | The 'sequence_mapper()' creates this file.  <br> It gives an overview of the number of images per unique sequence per session. | The 'sequence' column is the identifier column, 'possible sequence' is based on the regular expression from the 'user_settings.R' file.  <br>  Per session one column is created containing the number of files. <br>  The 'subject_session_merge' column contains each subject with this sequence, up to a number of 30 observations.  |
| sequence_map.tsv | The 'sequence_mapper()' creates and updates this file with each unique sequence ID from the 'json_metadata.tsv'. <br>  Based on this file the 'copy2BIDS' output paths are created. | The variables show the total number of sequences with the unique ID; the sequence type is identified by the regular expression from the 'user_settings.R' file.  <br> 'BIDS_sequence' and 'BIDS_type' need to be manually matched with the sequence_mapper() to the BIDS specification.  <br> The 'relevant' column is used for sequence selection. It is coded with '0' for "no export to BIDS" and '1' for "copy this file into BIDS". |
| copy2bids.tsv | Output of the copy2BIDS() function. <br>  Shows the input and output file paths of each file. | Variables per subject, session and sequence ID.  <br> Main information is in the 'input_file_paths' and 'output_file_path' columns.   |
