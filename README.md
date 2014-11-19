SEARUM
======

MapReduce implementation for association rule mining

Description
===========
Parallel FP-Growth and Association Rule mining MapReduce implementation. 

It runs each stage of PFPGrowth as described in the paper http://infolab.stanford.edu/~echang/recsys08-69.pdf, modified for and integrated with SEARUM as described in the paper http://www.ict-mplane.eu/sites/default/files/public/publications/386ispa2013grimaudo.pdf.

Prerequisites
=============
- Java JDK 1.6
- Apache Maven

How to compile and build the jar
================================
- Compile: *mvn compile*
- Package the jar: *mvn package*

How to run
==========
hadoop jar searum-0.0.1-jar-with-dependencies.jar Searum <input_file> <output_directory> <discretize (true|false)> <min_sup (0.0-1.0)> [<min_confidence (0.0-1.0)>]
