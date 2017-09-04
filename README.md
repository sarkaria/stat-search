# stat-search
## Introduction
This project uses Zeppelin and its built-in Spark to analyze the csv file from getstat.com

## Installation
* It is recommended that you do this in a Linux environment such as Ubuntu or Redhat.
* You will need to download [Zeppelin](https://zeppelin.apache.org). Use version 0.7.1. This comes with a built-in version of Spark v2.1.0 which is what we shall use here. (It is easy to install your independent Spark and point Zeppelin to that too.)
* First copy the zeppelin-env.sh file provided in this project, into Zeppelin's conf folder. This configures Zeppelin to run on port 8098 and specifies a dependency on the spark-csv package. This provides us support for reading CSV files.
* Start zeppelin: enter> _./zeppelin-0.7.1-bin-all/bin/zeppelin-daemon.sh start_
* Wait for it to start then browse to localhost:8098
* Import the getstat.json notebook.
* Modify the "Load Data into Spark" paragraph so that the file path points to the getstat csv file.
* Then run all paragraphs from the "triangle" icon near the top.

## Notes
* Spark is the de-facto solution for performing analytics on large data sets with a distributed computing environment. In this project a small sample set of data is operated upon using a local (single instance) deployment of Spark. This means that it runs on a single machine with all the data available locally. Spark can be easily deployed and configured to run on a cluster. In this case, Spark will automatically deploy (Spark) executors that will operate on data local to each compute instance.
* Spark is very powerful and has a rich set of functionality available via Python or Scala. Here we have kept the code quite simple and used mainly those operations that could also have been implemented in SQL. Far more powerful operations, such as map-reduce operations can be used to solve more complex operations such as word-counting.

