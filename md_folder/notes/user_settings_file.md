---
layout: page
title: User_settings.R file description
permalink: /user_settings/
nav_order: 2
parent: Supplementary
---
# What is in my ‘user_settings.R’ file?

You can also edit the file “user_settings.R” manually to your needs.

| Variable                 | Example                                                                                                                   | Description                                                                                                                                     |
|--------------------------|---------------------------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------|
| path_input_dicom         | “/media/niklas/BIDS_data/dicom/”                                                                                          | Input path, where your DICOM folders are inside of session folders                                                                              |
| path_output              | “/media/niklas/BIDS_data/BIDSconvertR”                                                                                    | A path, where all the output of the converter should be written to.                                                                             |
| study_name               | “BiDirect Study”                                                                                                          | Your study name, only needed for the dashboard rendering.                                                                                       |
| regex_subject_id         | “\[:digit:\]{5}”                                                                                                          | Regex defining your unique subject ID’s.                                                                                                        |
| regex_group_id           | “\[:digit:\]{1}(?=\[:digit:\]{4})”                                                                                        | Regex defining the group ID (if present).                                                                                                       |
| regex_remove_pattern     | “\[:punct:\]{1}\|\[:blank:\]{1}\|((b\|d)i(d\|b)i\|bid\|bd\|bdi)(ect\|rect)($\|(rs\|T2TSE\|neu\))”                         | These regex will be removed from the file names.                                                                                                |
| sessions_id_old          | c(“Baseline”, “FollowUp”, “FollowUp2”, “FollowUp3”)                                                                       | The folder (and session) names before conversion                                                                                                |
| sessions_id_new          | c(“0”, “2”, “4”, “6”)                                                                                                     | The folder (and session) names after conversion. These can be identical to “sessions_id_old”. But note, that in BIDS a number is the way to go. |
| mri_sequences            | “T1\|T2\|DTI\|fmr\|rest\|rs\|func\|FLAIR\|smartbrain\|survey\|smart\|ffe\|tse”                                            | These are regular expressions, which should be matched to your MRI sequence ID’s.                                                               |
| dcm2niix_argument_string | “-ba y -f %d -z y -w 0 -i y”                                                                                              | string of the arguments, which are used for dcm2niix, can be changed.                                                                           |

Table 1: Information in the user settings file
