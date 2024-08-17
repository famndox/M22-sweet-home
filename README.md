# Module 22 Sweet Home

## Overview of the Analysis

An exploration of pySpark, Hadoop, and Parquet [using Windows]*. SQL in Python... nothing crazy.

## Implementation

Foreward

* I respect that GoogleColab exists and is especially useful for 'one off needs' such as this class
* In spite of its 'lowest common denominator' value to my instructors, I attempted a local install:
    1. install java https://www.oracle.com/java/technologies/downloads/#jdk22-windows
    2. pip install pyspark
    3. conda install -c conda-forge findspar
    4. conda install -c conda-forge pyarrow
    5. conda install -c conda-forge fastparquet
    6. HADOOP can be cloned in git from https://github.com/steveloughran/winutils.git
    7. Then your HADOOP_HOME environment variable just needs to map to Steve's 'hadoop-3.0.0' folder you just dl'd
    8. I needed to delete /bin from the environment variable path (which is probably part of my Parquet* issue) 

## Parquet Issue and '*' References

* You'll have noticed a couple * above
* Notebook cells #10 - #12 fail, yet create a folder
* Notebook cell reference #13 uses the 'home_sales' view instead of the Parquet 'p_sales' as commented
* Observation: Hadoop version check through cmd fails to return using the winutils.git resources
* Observation: Class files do suggest a zip installation of pyspark, inslusive to Hadoop, instead of using pip
* Assessment: The 'pyspark' install via pip set the appropriate SPARK_HOME env variable, but did not include critical Parquet support files


## Summary

Having witnessesed GoogleColab runtime in class, as no attempt was made install local files for jupyter notebook, I'd wager that my unCached runtime is signifacantly quicker than any of my classmates Cached or Parqued* runtimes as throttled through the cloud. 

Parqued* in my case is a second Cached run:

* unCached--- 0.42646312713623047 seconds ---
* Cached--- 0.26602983474731445 seconds ---
* Parqed*--- 0.2599978446960449 seconds ---
* Delta between C&P*--- 0.006031990051269531 seconds ---

## Conclusion

Thank you for reading my bitter tale. If you must, take my ~30 points for attempting what my teacher(s) gave up on. 

From Requirements:
* 9. A partition of the home sales dataset by the "date_built" field is created, and the formatted parquet data is read. (10 points)
* 10. A temporary table of the parquet data is created. (10 points)
* 11. The query from step 6 is run on the parquet temporary table, and the run time is computed. (10 points)
