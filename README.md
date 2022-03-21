# Oracle E-Business Suite Integrated SOA Gateway


<br>

## Create custom PL/SQL package as Oracle REST-API web service
- Prerequisite
- Create the PL/SQL package in the database
- Create a annotated interface file based on annotation standards.
- Run the Standalone IREP Parser(irep_parser.sh) which generates the *.ildt files.
- Use FNDLOAD to upload these ildt files
- Verify uploaded interface in IREP UI
- Create the integration repository loader file (iLDT) file using Putty
- Deploy the custom PL/SQL interface as REST services in the Oracle Integration Repository
- Deploy the Service by pressing "Deploy" button
- Create the necessary security grants for the custom integration interfaces
- Test the REST-API web service





<br>

```
$FND_TOP/bin/FNDLOAD apps/<password> 0 Y UPLOAD $FND_TOP/patch/115/import/wfirep.lct $FND_TOP/patch/115/irep/patch/115/sql/AFCPREQS_pls.ildt
```
