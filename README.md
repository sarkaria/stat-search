# stat-search
## Introduction
This project uses Zeppelin and its built-in Spark to analyze the csv file from getstat.com

## Installation
* You will need to download [Zeppelin](https://zeppelin.apache.org). Use version 0.7.1
* First copy the zeppelin-env.sh file provided into Zeppelin's conf folder
* Start zeppelin: enter> ./zeppelin-0.7.1-bin-all/bin/zeppelin-daemon.sh start
* Wait for it to start then browse to localhost:8098
* Import the getstat.json notebook.
* Modify the "Load Data into Spark" paragraph so that the file path points to the getstat csv file.
* Then run all paragraphs from the "triangle" icon near the top.

## Notes
* Spark is the de-facto solution for performing analytics on large data sets using distributed computing. In this project a small sample set of data is operated upon using a local (single instance) deployment of Spark. This means that it runs on a single machine with all the data available locally. Spark can be easily deployed and configured to run on a cluster. In this case, Spark will automatically deploy (Spark) executors that will operate on data locally.
* Spark is very powerful and has a rich set of functionality available via Python or Scala. Here we have kept the code quite simple and used mainly those operations that could also have easily been implemented in SQL. Far more powerful operations, such as map-reduce procedures can be used implement more complex operations such as word-counting.

