# Oracle E-Business Suite Integrated SOA Gateway


<br>

## Create a custom PL/SQL package as an Oracle REST-API web service
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

### Find business entity SQL 
```sql
  SELECT FL.LOOKUP_CODE, FL.MEANING, FL.DESCRIPTION
    FROM FND_LOOKUPS FL
   WHERE     FL.LOOKUP_TYPE = 'BUSINESS_ENTITY'
         --         AND FL.LOOKUP_CODE = 'PER_EMPLOYEE'
         AND FL.ENABLED_FLAG = 'Y'
         AND (   TRUNC (SYSDATE) BETWEEN TRUNC (FL.START_DATE_ACTIVE)
                                     AND TRUNC (FL.END_DATE_ACTIVE)
              OR FL.END_DATE_ACTIVE IS NULL)
ORDER BY FL.LOOKUP_CODE NULLS LAST

```


<br>

```
$FND_TOP/bin/FNDLOAD apps/<password> 0 Y UPLOAD $FND_TOP/patch/115/import/wfirep.lct $FND_TOP/patch/115/irep/patch/115/sql/AFCPREQS_pls.ildt
```
