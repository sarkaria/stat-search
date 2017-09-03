# stat-search
## Introduction
This project uses Zeppelin and its built-in Spark to analyze the csv file from getstat.com

## Installation
* You will need to download Zeppelin. Use version 0.7.1
* First copy the zeppelin-env.sh file provided into Zeppelin's conf folder
* Start zeppelin: enter> ./zeppelin-0.7.1-bin-all/bin/zeppelin-daemon.sh start
* Wait for it to start then browse to localhost:8098
* Import the getstat.json notebook.
* Modify the "Load Data into Spark" paragraph so that the file path points to the getstat csv file.
* Then run all paragraphs from the "triangle" icon near the top.

