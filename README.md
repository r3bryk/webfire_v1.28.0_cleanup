# webfire_v1.28.0_cleanup

## Description

`webfire_v1.28.0_cleanup` is designed to clean the `WebFIRE v1.28.0` database up.
`WebFIRE` is the US EPA’s online repository for emissions factors, providing recommended values for criteria and hazardous air pollutants (HAP) from industrial and non-industrial sources. It also includes the underlying measurement data and detailed metadata such as source categories, control technologies, pollutants, and supporting documentation.
More information is available at https://www.epa.gov/electronic-reporting-air-emissions/webfire.

## What does the script do

Main cleanup steps:

1. Check Name and CAS for odd characters and edit values.

2. Format CAS and ensure text format to avoid unwanted Excel conversion.

3. Save unique Name and CAS# set for PubChem InChIkeys and other useful data retrieval.

- Retrieve data using PubChem_Retriever (available at https://github.com/r3bryk/PubChem_Retriever).
- Update WebFIRE with the retrieved data using Data_Retriever (available at https://github.com/r3bryk/Data_Retriever).

4. Write filtered WebFIRE (intermediate) to CSV file if needed.

5. Load WebFIRE updated with PubChem InChIKeys and other data.

6. Remove compounds:

- With no InChIKey values.
- With specific InChIKey values (e.g., mixtures, inorganic compounds & inorganic mixtures, etc.).
- With unwanted keywords (e.g., mixtures, minerals, inorganic compounds & inorganic mixtures, etc.).

7. Sort and save filtered WebFIRE as CSV file.

## Prerequisites

1. The script is written in Python 3; https://www.python.org/downloads/windows/.
2. The script is run in JupyterLab Notebook; https://jupyter.org/.

## How to use the script

Run the script cell by cell in JupyterLab Notebook.

## License

[![MIT License](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/license/mit)

Intended for academic and research use.
