# orcid_finder
## Processing Steps
* Download the EML files
  * In Jupyter notebook download_eml.ipynb, run get_all_eml_async()
  * File knb-lter-kbs.140.5.xml will be empty because the package is not public, so delete the file
* Collect all of the responsible parties in ../eml_files/responsible_parties.txt
  * In parse_eml.py, run:
    * collect_responsible_parties(f'{EML_FILES_PATH}/responsible_parties.txt') 
