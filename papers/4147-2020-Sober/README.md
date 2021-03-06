# SAS4147-2020
##  Best Practices for Converting SAS Code to Leverage CAS
### Coding Examples can be Ran **"As-Is"** with SAS Viya 3.5+
### All examples are for functional testing, not performance testing
#### **S**AS **P**rogram **R**un-time **E**nvironment (**SPRE** - [SAS Viya's Compute Server Engine](https://go.documentation.sas.com/?cdcId=pgmsascdc&cdcVersion=9.4_3.5&docsetId=pgmdiff&docsetTarget=n1t409khqsu0n8n103122kk0bfzn.htm&locale=en))
####  SAS **C**loud **A**nalytic **S**ervices (**CAS** - [SAS Viya's In-Memory Engine](https://go.documentation.sas.com/?cdcId=pgmsascdc&cdcVersion=9.4_3.5&docsetId=casref&docsetTarget=p148gqjwzfm0w1n12hc60f6pfcne.htm&locale=en))

**1. Setup.sas**
- **Required Step** 
- SPRE Enabled
- Sets the SAS macro variable &DATAPATH 
- Copy data used in the CAS coding examples to the path defined by the macro variable &DATAPATH 
- Macro &DATAPATH is used in the CAS coding examples

**2. DATA.Step.Partition.and.OrderBY.sas**
- CAS Enabled
- Example of using DATA Step to partition and order a CAS table
- - Benfit, when a BY statement mactes the partition and ordering, the data is immediately ready for processing by each thread 
- - Note: **If the BY statment does not math the partition and ordering then there is a cost i.e. the BY is done on the fly** to group the data correctly on each thread

**3. Delete.CAS.Table.sas**
- CAS Enabled
- How to delete a CAS table
- **A good programming habit**

**4. Display.Viya.CAS.Information.sas**
- CAS Enabled
- Provides information on your SAS Viya environment

**5. Emulate.PROC.APPEND.sas** 
- CAS Enabled 
- [DATA Step emualtion of PROC APPEND](https://blogs.sas.com/content/sgf/2017/11/20/how-to-emulate-proc-append-in-cas/)
- Note PROC APPEND is not CAS enabled and will run in SPRE

**6. FedSQL.sas**
- CAS Enabled
- [FedSQL is CAS enabled, convert PROC SQL code into FedSQL to leverage CAS](https://blogs.sas.com/content/sgf/2019/10/22/sas-viya-how-to-emulate-proc-sql-using-cas-enabled-proc-fedsql/) 

**7. Formats.sas**
- CAS Enabled
- Ensuring SAS FORMATS are knowing to CAS 

**8. High.Cardinality.DATA.Step.BY.sas**
- SPRE Enabled
- High cardinality of a BY variable may run faster in SPRE. Best practice in how to leverage SPRE with a CAS table

**9. How.to.Achive.Repeatable.Results.NODUP.sas**
- CAS Enabled
- [How to achieve repeatable results with distributed DATA Step BY Groups](https://blogs.sas.com/content/sgf/2018/11/14/how-to-achieve-repeatable-results-with-distributed-data-step-by-groups/)

**10. How.to.Convert.CHARACTER.Data.Type.into.VARCHAR.Data.Type.when.Lifting.a.Table.into.CAS.sas**
- CAS Enabled
- To reduce the size of CAS tables consider converting CHARACTER data types into VARCHAR data type using PROC CASUTIL IMPORTOPTIONS VARCHARCONVERSION= statement
- **A good programing habit**

**11. How.to.Parallel.Load.and.Compress.a.CAS.Table.sas**
- CAS Enabled
- [How to Parallel Load and Compress a CAS Table](https://blogs.sas.com/content/sgf/2019/10/17/how-to-parallel-load-and-compress-a-sas-cloud-analytic-services-cas-table/)
 
**12. Load.SAS7BDAT.To.CAS.Table.sas**
- CAS Enabled
- Best practice to parallel load a SAS7BDAT data set into a CAS table

**13. Load.SASHDAT.To.CAS.Table.sas**
- CAS Enabled
- Best practice to parallel load a SASHDAT table into a CAS table

**14. ODS.Save.CAS.Table.To.CSV.File.sas**
- CAS Enabled
- Leveraging the Output Delivery System to generate a CSV file from a CAS table 

**15. One.Level.Names.Managed.By.CAS.sas** 
- CAS Enabled
- [How to reference CAS tables using a one-level name](https://blogs.sas.com/content/sgf/2018/06/21/how-to-reference-cas-tables-using-a-one-level-name/)

**16. SAS.Viya.3.4.or.Lower.Descending.Numeric.BY.Emulation.sas** 
- CAS Enabled 
- SAS Viya 3.4 or Lower
- [How to Emulate DATA Step DESCENDING BY Statements in SAS Cloud Analytic Services (CAS)](https://blogs.sas.com/content/sgf/2019/10/10/how-to-emulate-data-step-descending-by-statements-in-sas-cloud-analytic-services-cas/)
- **Note: SAS Viya 3.5 or higher supports DESCENDING on a DATA Step BY statement with the caveat that DESCENDING is not not supported on the first variable of the BY statement**
- - Note: if there is a DESCENDING on the first variable of the BY statement the DATA Step will run in SPRE

**17. SAS.Viya.3.4.or.Lower.Emulate.PROC.SORT.NODUPKEY.sas**
- CAS Enabled
- SAS Viya 3.4 or Lower
- DATA Step emulation of PROC SORT NODUPKEY is accomplished by using FIRST. (dot) processing

**18. SAS.Viya.3.5.PROC.SORT.NODUPKEY.NOUNIKEY.sas**
- CAS Enabled 
- Requires SAS Viya 3.5+ 
- PROC SORT NODUPKEY and NOUNIKEY on CAS Table Examples 

**19. Save.CAS.Table.To.SAS7BDAT.sas**
- CAS Enabled
- Best practice to save a CAS table as a SAS7BDAT table  

**20. Save.CAS.Table.To.SASHDAT.sas**
- CAS Enabled
- Best practice to save a CAS table as a SASHDAT table 

**21. Set.The.Active.CASLIB.sas**
- CAS Enabled
- When loading data into CAS you need to change to the active CASLIB prior to accessing that CAS table

**22. Terminate.CAS.Session.sas**
- CAS Enabled
- How to terminate your CAS session 
- If you forget to do this do not worry; all cas session have a default time-out setting which is hit after a period of non activity
- **A good programming habit**
