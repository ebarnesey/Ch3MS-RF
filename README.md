# CH3MS-RF
README

CH3MS (Chemical Characterization by Chromatography-MS Random Forest Modeling)is an R-based tool for characterizing properties of organic compounds which have been characterized by chromatography-mass spectrometry techniques but which cannot be identified by matching to publicly available mass spectrometry databases.  It requires the input of a dataset of known compounds which span the expected property (volatility, polarity, etc) distribution of the unknown compounds, and ideally should come from the instrument utilized for characterization of the novel mixture to maximize the consistency in chromatographic retention indexes.  This work is described in full in Franklin et al, "Ch3MS-RF: A Random Forest Model for Chemical Characterization and Improved Quantification of Novel Atmospheric Organics Detected by Chromatography Mass Spectrometry Techniques", which will be linked when a preprint is available. 

CONTENTS

- AppendixB.Rmd: R markdown script which reads in the properties and mass spectra of a known standard mixture, models target properties using a random forest model, and produces predictions for an input file of unknown compounds.

- EBF_GoldsteinGroup_ExternalStandard_GoA2018_ms.csv: csv file containing the unique names and mass spectra of the known input datased of representative organic compounds. Required features include "Name" (unique name of each organic compound), "Retention_Index" (chromatographic elution time of each species relative to some interval standard, in this case a linear deuterated alkane series), and "MS" (unit resolution mass spectrum of each compound, listed as follows: mass intensity; mass intensity; mass intensity; etc).  Additional features provide useful context but are not utilized in the model. 

- EBF_GoldsteinGroup_ExternalStandard_GoA2018_properties.csv: csv file containing the names (consistent with names in the mass spectrum file) and properties of interest of the known representative compound mixture.  Required features include "Name", "Retention_Index" (identical to the prior file definition), "ChemFormula" (chemical formula in CHONS form), and "Func_Group_Cat_3" (functional group categorization, which is important for evenly splitting testing and training data across compound classes). If the property of interest cannot be calculated from che chemical formula, a property feature is also required, which in this example case is "Log_VP" (log of saturation vapor pressure in atm). Other properties can be substituted.

- EBF_GoldsteinGroup_Template_Unknown_Dataset.csv: csv example file containing the names, retention indexes, and mass spectra of unknown compounds that are the subject of interest for property modeling. Required features include "Name", "Retention_Index", and "MS", defined identically to the input files.

- Example_Output_Table.csv: csv file containing the names and predicted properties of the unknown compounds of interest.  This file will be overwritten each time the script is run and it is recommended that it be renamed to reflect the application and use case. 

GITHUB

This work is published on GitHub as a public template and can be found at the following link: https://github.com/ebarnesey/Ch3MS-RF

CONTACT

The primary author of this work is Emily Barnes Franklin, who can be contacted at barnes_emily@berkeley.edu or emilybbarnes@gmail.com.  A secondary contact for this work is Dr. Allen Goldstein (ahg@berkeley.edu). Please contact with any questions or suggestions. 

LICENSE

These scripts are released under the MIT software license. Details can be found in the "LICENSE" script contained within. 

