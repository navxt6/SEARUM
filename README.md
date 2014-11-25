SEARUM
======

Hadoop MapReduce implementation for Association Rule Mining technique

Description
===========
Parallel FP-Growth and Association Rule mining MapReduce implementation. 

It runs each stage of PFPGrowth as described in the paper http://infolab.stanford.edu/~echang/recsys08-69.pdf, modified for and integrated with SEARUM as described in the paper http://www.ict-mplane.eu/sites/default/files/public/publications/386ispa2013grimaudo.pdf.

Prerequisites
=============
- Java JDK 1.7
- Apache Maven

How to compile and build the jar
================================
- Download the code `git clone https://github.com/navxt6/SEARUM.git`
- Compile `mvn compile`
- Package the jar `mvn package`

How to run SEARUM
=================
Run SEARUM like this:

````java
hadoop jar searum-0.0.1-jar-with-dependencies.jar Searum <input_file> <output_directory> <discretize (true|false)> <min_sup (0.0-1.0)> [<min_confidence (0.0-1.0)>]
````
Parameters:

  - *input_file*:  input dataset
  - *output_directory*: output directory that hold intermidiate and final results
  - *discretize*: true if you need a discretization step (you have to implement your own MapReduce job for that), false otherwise
  - *min_sup*: minimum support value for frequent itemset mining
  - *min_confidence*: minimum confidence value for association rule generation (optional)

Example
=======
In the data folder there is an example dataset already discretized that can be used to test SEARUM
- Create a directory on HDFS: `hadoop fs -mkdir searum_test`
- Create a sub-directory to hold the example dataset: `hadoop fs -mkdir searum_test/data`
- Upload the example dataset in HDFS: `hadoop fs -put data/example_dataset.dat`

Let's extract all frequent itemsets with minimum support of 
