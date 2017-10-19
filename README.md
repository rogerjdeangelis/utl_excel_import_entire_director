# utl_excel_import_entire_director
Import an entire directory of excel files. Big data analytics. Machine learning. Data management.

    ```  Importing entire directory of XLS file into SAS                                                                                                              ```
    ```                                                                                                                                                               ```
    ```  Need to Import more than 3000 xlsx files in sas                                                                                                              ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  WORKING CODE                                                                                                                                                 ```
    ```  ============                                                                                                                                                 ```
    ```                                                                                                                                                               ```
    ```          rc=filename("mydir","d:\xls");                                                                                                                       ```
    ```          did=dopen("mydir");                                                                                                                                  ```
    ```          memcount=dnum(did);                                                                                                                                  ```
    ```          do i=1 to memcount;                                                                                                                                  ```
    ```            rc=dosubl('                                                                                                                                        ```
    ```               libname xel  "d:/xls/&mem..xlsx";                                                                                                               ```
    ```               data &mem;                                                                                                                                      ```
    ```                 set xel.&mem;                                                                                                                                 ```
    ```                                                                                                                                                               ```
    ```  FYI It is trivial to add a pop up window and ask the user if the process should continue?                                                                    ```
    ```    4 lines of code? see some of my previous posts.                                                                                                            ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  This requires full SAS so if yo get a error you may                                                                                                          ```
    ```  want to contact your IT dept and show them the error.                                                                                                        ```
    ```                                                                                                                                                               ```
    ```  https://goo.gl/F9N5Jq                                                                                                                                        ```
    ```  https://communities.sas.com/t5/Base-SAS-Programming/Need-to-Import-more-than-3000-xlsx-files-in-sas/m-p/403451                                               ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  HAVE                                                                                                                                                         ```
    ```  ====                                                                                                                                                         ```
    ```                                                                                                                                                               ```
    ```   Directory of                                                                                                                                                ```
    ```                                                                                                                                                               ```
    ```    d:\xls                                                                                                                                                     ```
    ```                                                                                                                                                               ```
    ```    cars.xlsx    04/04/2017  04:53 PM  49,376                                                                                                                  ```
    ```    class.xlsx   04/04/2017  04:53 PM   9,253                                                                                                                  ```
    ```    iris.xlsx    04/04/2017  04:53 PM  12,870                                                                                                                  ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  WANT  (Log dataset and three SAS datasets)                                                                                                                   ```
    ```  ===========================================                                                                                                                  ```
    ```                                                                                                                                                               ```
    ```   Create datasets                                                                                                                                             ```
    ```     WORK.LOG                                                                                                                                                    ```
    ```     WORK.CARS                                                                                                                                                 ```
    ```     WORK.CLASS                                                                                                                                                ```
    ```     WORK.IRIS                                                                                                                                                 ```
    ```                                          Libname Ok      Data step ok            Text of error                                                                ```
    ```                                                                                                                                                               ```
    ```    WORKBOOK      STATUS      MEMCOUNT    ERRORCODELIB    ERRORCODEDATA     ERRORTEXTLIB    ERRORTEXTDATA                                                      ```
    ```                                                                                                                                                               ```
    ```   cars.xlsx     Completed        3            0                0                                                                                              ```
    ```   class.xlsx    Completed        3            0                0                                                                                              ```
    ```   iris.xlsx     Completed        3            0                0                                                                                              ```
    ```                                                                                                                                                               ```
    ```  *                _                  _       _                                                                                                                ```
    ```   _ __ ___   __ _| | _____        __| | __ _| |_ __ _                                                                                                         ```
    ```  | '_ ` _ \ / _` | |/ / _ \_____ / _` |/ _` | __/ _` |                                                                                                        ```
    ```  | | | | | | (_| |   <  __/_____| (_| | (_| | || (_| |                                                                                                        ```
    ```  |_| |_| |_|\__,_|_|\_\___|      \__,_|\__,_|\__\__,_|                                                                                                        ```
    ```                                                                                                                                                               ```
    ```  ;                                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  CREATE A DIRECTORY OF EXCEL FILES                                                                                                                            ```
    ```  =================================                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  dm "dexport sashelp.class 'd:\xls\class.xlsx' replace";                                                                                                      ```
    ```  dm "dexport sashelp.cars  'd:\xls\cars.xlsx' replace";                                                                                                       ```
    ```  dm "dexport sashelp.iris  'd:\xls\iris.xlsx' replace";                                                                                                       ```
    ```                                                                                                                                                               ```
    ```  /* LOG                                                                                                                                                       ```
    ```  1     dm "dexport sashelp.class 'd:\xls\class.xlsx' replace";                                                                                                ```
    ```  NOTE: "CLASS" range/sheet was successfully created.                                                                                                          ```
    ```  2     dm "dexport sashelp.cars  'd:\xls\cars.xlsx' replace";                                                                                                 ```
    ```  NOTE: File "d:\xls\cars.xlsx" will be created if the export process succeeds.                                                                                ```
    ```  NOTE: "CARS" range/sheet was successfully created.                                                                                                           ```
    ```  3     dm "dexport sashelp.iris  'd:\xls\iris.xlsx' replace";                                                                                                 ```
    ```  NOTE: File "d:\xls\iris.xlsx" will be created if the export process succeeds.                                                                                ```
    ```  NOTE: "IRIS" range/sheet was successfully created.                                                                                                           ```
    ```  */                                                                                                                                                           ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  *          _       _   _                                                                                                                                     ```
    ```   ___  ___ | |_   _| |_(_) ___  _ __                                                                                                                          ```
    ```  / __|/ _ \| | | | | __| |/ _ \| '_ \                                                                                                                         ```
    ```  \__ \ (_) | | |_| | |_| | (_) | | | |                                                                                                                        ```
    ```  |___/\___/|_|\__,_|\__|_|\___/|_| |_|                                                                                                                        ```
    ```                                                                                                                                                               ```
    ```  ;                                                                                                                                                            ```
    ```                                                                                                                                                               ```
    ```  %symdel mem / nowarn;                                                                                                                                        ```
    ```                                                                                                                                                               ```
    ```  data log(keep=workbook status memcount errortextlib errortextdata errorcodelib errorcodedata);                                                               ```
    ```                                                                                                                                                               ```
    ```     retain                                                                                                                                                    ```
    ```       workbook status memcount errortextlib errortextdata errorcodelib errorcodedata;                                                                         ```
    ```     length                                                                                                                                                    ```
    ```        ErrorTextLib                                                                                                                                           ```
    ```        ErrorTextData                                                                                                                                          ```
    ```        ErrorCodeLib                                                                                                                                           ```
    ```        ErrorCodeData                                                                                                                                          ```
    ```        workbook        $96;                                                                                                                                   ```
    ```                                                                                                                                                               ```
    ```     rc=filename("mydir","d:\xls");                                                                                                                            ```
    ```     did=dopen("mydir");                                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```     if did > 0 then do;                                                                                                                                       ```
    ```          memcount=dnum(did);                                                                                                                                  ```
    ```          do i=1 to memcount;                                                                                                                                  ```
    ```             name=dread(did,i);                                                                                                                                ```
    ```             call symputx('mem',scan(name,1,'.'));                                                                                                             ```
    ```             put name=;                                                                                                                                        ```
    ```             rc=dosubl('                                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```                libname xel  "d:/xls/&mem..xlsx";                                                                                                              ```
    ```                %let ErrortextLib= &syserrortext;                                                                                                              ```
    ```                %let ErrorcodeLib= &syserr;                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```                data &mem;                                                                                                                                     ```
    ```                  retain fro "&mem.";                                                                                                                          ```
    ```                  set xel.&mem;                                                                                                                                ```
    ```                run;quit;                                                                                                                                      ```
    ```                %let ErrortextData= &syserrortext;                                                                                                             ```
    ```                %let ErrorcodeData= &syserr;                                                                                                                   ```
    ```                                                                                                                                                               ```
    ```                libname xel clear;                                                                                                                             ```
    ```             ');                                                                                                                                               ```
    ```             workbook      =  name;                                                                                                                            ```
    ```             ErrorTextLib  =  symget('ErrorTextLib');                                                                                                          ```
    ```             ErrorTextData =  symget('ErrorTextData');                                                                                                         ```
    ```             ErrorCodeLib  =  symget('ErrorCodeLib');                                                                                                          ```
    ```             ErrorCodeData =  symget('ErrorCodeData');                                                                                                         ```
    ```                                                                                                                                                               ```
    ```             if    rc ne 0                                                                                                                                     ```
    ```                or ErrorCodeLib  ne "0"                                                                                                                        ```
    ```                or ErrorCodeData ne "0" Then do;                                                                                                               ```
    ```                 Status        =  "Failed      ";                                                                                                              ```
    ```                 stop;                                                                                                                                         ```
    ```             end;                                                                                                                                              ```
    ```             else do;                                                                                                                                          ```
    ```                Status="Completed";                                                                                                                            ```
    ```             end;                                                                                                                                              ```
    ```             output;                                                                                                                                           ```
    ```          end;                                                                                                                                                 ```
    ```      end;                                                                                                                                                     ```
    ```      stop;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```  run;quit;                                                                                                                                                    ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```
    ```  NAME=cars.xlsx                                                                                                                                               ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to cars                                                                                                              ```
    ```  NOTE: Libref XEL was successfully assigned as follows:                                                                                                       ```
    ```        Engine:        EXCEL                                                                                                                                   ```
    ```        Physical Name: d:/xls/cars.xlsx                                                                                                                        ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to cars                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to cars                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to cars                                                                                                              ```
    ```  NOTE: There were 428 observations read from the data set XEL.cars.                                                                                           ```
    ```  NOTE: The data set WORK.CARS has 428 observations and 16 variables.                                                                                          ```
    ```  NOTE: DATA statement used (Total process time):                                                                                                              ```
    ```        real time           0.08 seconds                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  NOTE: Libref XEL has been deassigned.                                                                                                                        ```
    ```  NAME=class.xlsx                                                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to class                                                                                                             ```
    ```  NOTE: Libref XEL was successfully assigned as follows:                                                                                                       ```
    ```        Engine:        EXCEL                                                                                                                                   ```
    ```        Physical Name: d:/xls/class.xlsx                                                                                                                       ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to class                                                                                                             ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to class                                                                                                             ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to class                                                                                                             ```
    ```  NOTE: There were 19 observations read from the data set XEL.class.                                                                                           ```
    ```  NOTE: The data set WORK.CLASS has 19 observations and 6 variables.                                                                                           ```
    ```  NOTE: DATA statement used (Total process time):                                                                                                              ```
    ```        real time           0.02 seconds                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  NOTE: Libref XEL has been deassigned.                                                                                                                        ```
    ```  NAME=iris.xlsx                                                                                                                                               ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to iris                                                                                                              ```
    ```  NOTE: Libref XEL was successfully assigned as follows:                                                                                                       ```
    ```        Engine:        EXCEL                                                                                                                                   ```
    ```        Physical Name: d:/xls/iris.xlsx                                                                                                                        ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to iris                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to iris                                                                                                              ```
    ```  SYMBOLGEN:  Macro variable MEM resolves to iris                                                                                                              ```
    ```  NOTE: There were 150 observations read from the data set XEL.iris.                                                                                           ```
    ```  NOTE: The data set WORK.IRIS has 150 observations and 6 variables.                                                                                           ```
    ```  NOTE: DATA statement used (Total process time):                                                                                                              ```
    ```        real time           0.05 seconds                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```  SYMBOLGEN:  Macro variable SYSERRORTEXT resolves to                                                                                                          ```
    ```  SYMBOLGEN:  Macro variable SYSERR resolves to 0                                                                                                              ```
    ```  NOTE: Libref XEL has been deassigned.                                                                                                                        ```
    ```  NOTE: The data set WORK.LOG has 3 observations and 7 variables.                                                                                              ```
    ```  NOTE: DATA statement used (Total process time):                                                                                                              ```
    ```        real time           0.66 seconds                                                                                                                       ```
    ```                                                                                                                                                               ```
    ```                                                                                                                                                               ```

