# orcid_finder
## Processing Steps
* Download the EML files
  * In Jupyter notebook download_eml.ipynb, run get_all_eml_async()
  * File knb-lter-kbs.140.5.xml will be empty because the package is not public, so delete the file
* Collect all of the responsible parties in ../eml_files/responsible_parties.txt
  * In parse_eml.py, run:
    - collect_responsible_parties(f"{EML_FILES_PATH}/responsible_parties.txt")
* Create database
  - psql -U postgres
    + create database orcid_finder with encoding 'utf8';
  * In directory db:
    - psql orcid_finder -U postgres -h localhost < create_eml_schemas.sql
* Populate the table eml_files.responsible_parties_raw with the responsible parties as found in the EML files
  - In db.py, run: 
    - build_responsible_party_raw_db()
