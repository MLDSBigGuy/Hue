# Spark Stream Processing to view stream in DSrteams and RDDs (streaming ---windowing, watermarking)
- Spark is built on top of hadoop 
- Basic transfromation on Dstreams to extract info we need
- Hadoop distrubuted computing framework has hdfs which takes care of storeage and multiple 
- maprreduce to process data across multple servers 
  Map phase - runs on multiple clusters. Mapper runs on file input
  Reduce - works on output produced ny map phase and extract useful info. Reduce runs on map files to produce fina l file
  MR are batch joibs (ruuns for hours / days ) 
  
- Traditional DS dontnot support realt itme strrmeaing. MR faile in real time processing

- Imp of real time processing 
- Banking system with monthly, weekly reports - daily hourly jobs run to check for fraduleant transactions. This can be solved with tradidtionla longruniing mr jibs
- Bunch of requests to server. critical failure. Thousands of bank customers in pain. Here u ned real time monitring. . Logs cannot be stored for later processing in this case

- Spark is replacement of MR Batch processing

- Spark works on datasets loaded into memory 

- Spark packages in python /Scala: 
  - Spark SQL
  - MLLib
  - Graphx for data in groah like social n/w
  - Saprk Streaming
  
- Spark streaming processeinf used for 
  - map route of car using gps location,
  - refernces for atest movies
  - Trigger an alert 
  
- Essence of spark - track statistics (avg), taruins ml models, detects anomalies in real time ex: erros in ur bank websites
- RDD - holds data in inmemory is analogous to collection object in java. 


- spark interactvive shell 

  - print conetent of rdd with studemts.collect()
  - stu.take(4) - first 4 elements 
- from pyspark import sparkcontext as sc
  sc.textfile(airlinesdata)
  arlinesfilteres = airlines.filteres(lamba x: 'luftansa' not in x) (airlines other than luftansa are stored in rd)
  airlinefiletered.taje/5) - first 5 entries 
  
- Charaacteristis od rdd
  - partitioned (data split in mmultiple clusters)
  - rdds once created cannot be changed (iimutable)
    - 2 operation perimitted in rd 
      - read (- take , - collect )
      - Transformation 
  - resilient (rdd can be reconstructed eben if a nde crahses)
  


  - count the number of time a word occurs in  a text file 
    line = sc. texzFile("")
    words = lines. flatMap(lamba line: line.split(""))
    counts = words.map(lamba word: (word,1).reducebyKey(lamba a,b:a+b) -- MR in spark 
    reducebyKey takes all values from map and then sums up the result (map key gives count 1 for all the words that exists)
    
  - Streaming log messages from website/server 
  -  DStream = Sequence of rdds 
  
  - Listen for error messsages - spark app - https://drive.google.com/file/d/127uDTTC6Q8K1efb35zgdfRLNwJvfAMbz/view
    -  from pyspark.streaming import StreamingContext
    - All mesages with in internl 2se form m1 rdd
  
  

- To do all data manipulations, u can do it ión pandas and convert pandas dataframe to Spark RDD and viceversa 


