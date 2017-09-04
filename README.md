# stat-search
## Introduction
This project uses Zeppelin and its built-in Spark to analyze the csv file from getstat.com

## Approach
1. Spark is the de-facto solution for performing analytics on large data sets within a distributed computing environment. In this project we have chosen to process a tiny sample of data using a local (single instance) deployment of Spark. This means that it runs on a single machine with all the data available locally. Spark can be easily deployed and configured to run on a cluster. In this case, Spark will automatically deploy executors that will operate on data local to each compute instance. We have every reason to believe, that even a modestly sized cluster will be able to process billions of rows of data every day.
1. Spark is used to process the CSV file directly without transformation. Once loaded, it is possible to save the CSV as a parquet file. While access to CSV off file is good. Parquet is better and memory is best. In this project, we cache the data in Spark's memory.
1. Spark is very powerful and has a rich set of functionality available via Python or Scala. The language of choice is Scala, although the solution code is quite simple and uses mainly those operations that could also have been implemented in SQL. Far more powerful operations, such as map-reduce operations can be used to solve more complex operations such as word-counting.

## Installation
1. It is recommended that these steps are followed in a Linux environment such as Ubuntu or RedHat.
1. You will need to download [Zeppelin](https://zeppelin.apache.org). Use version 0.7.1. This comes with a built-in version of Spark v2.1.0 which is what we shall use here. (It is easy to install another version of Spark and point Zeppelin to that too.)
1. First copy the _zeppelin-env.sh_ file provided in this project, into Zeppelin's _conf_ folder. This configures Zeppelin to run on port 8098 and specifies a dependency on the spark-csv package. This provides us support for reading CSV files.
1. Start zeppelin: enter> _./zeppelin-0.7.1-bin-all/bin/zeppelin-daemon.sh start_
1. Wait for it to start then browse to _localhost:8098_
1. Import the _getstat.json_ notebook.
1. Modify the *Load Data into Spark* paragraph so that the file path points to the getstat CSV file.
1. Then run all paragraphs. While it is possible to do so from the "triangle" icon near the top, I find it easier to click on the "triangle" for each paragraph individually. This can be found to the right of each paragraph.

## Notes
* The notebook takes advantage of Zeppelin's built-in visualization mechanisms which by the way are interactive.
* Zeppelin is a data scientists tool. It's purpose is to explore and process data, typically in an interactive manner. With a little effort, the Scala code here could easily be written as a class with methods providing specific behaviours or functions against the data. The intent being to package the functionality into a JAR and incorporate it into a production pipeline.

## Sample Screenshot
Here is a sample output from the notebook:

![Market Analysis Sample Output](https://github.com/sarkaria/stat-search/blob/master/market-analysis.jpg)

