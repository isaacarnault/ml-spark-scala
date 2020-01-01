[![ml.png](https://i.postimg.cc/bwV30QTH/ml.png)](https://postimg.cc/NKT6B2Z5)

# Machine Learning using Spark-Scala - Hands-on
### Tools used: IntelliJ, Spark • Programming languages: Scala

[![Project Status: Active – The project has reached a stable, usable state and is being actively developed.](https://www.repostatus.org/badges/latest/active.svg)](https://www.repostatus.org/#active)

The following gist is intended to Data Engineers. It focuses on `Spark` and `Scala` for `Machine Learning`.<br>
If we want to handle `batch` and `real-time` data processing, this gist is definitely worth checking.<br>
We'll learn how to install and use `Spark` and `Scala` on a `Linux` system.<br>
We'll learn latest `Spark 2.0` methods and updates to the `MLlib` library working with `Spark SQL` and Dataframes.
Please fork it if we find it relevant for our educational or professional path.

## How is gist is structured
This gist is structured into 2 parts:<br>

### Part 1. Machine Leaning using SPark-Scala (Linear Regression
Check <b>  <b>.
  
## Important
<b>Scala</b><br>
. `Scala` is a general purpose programming language.<br>
. `Scala` was designed by Martin Odersky (Ecole Polytechnique Fédérale de Lausanne).<br>
. `Scala` source code is intended to be compiled to `Java` bytecode to run on a `Java Virtual Machine` (JVM).<br>
. `Java` librairies can be used directly in `Scala`.<br>
. 
<b>Spark</b><br>
. `Spark` is one of the most powerful `Big Data` tools.<br>
. `Spark` runs programs up to 100x faster than Hadoop's `MapReduce`.<br>
. `Spark` can use data stored in `Cassandra`, Amazon `S3`, Hadoop's`HDFS`, etc.<br>
. `MapReduce` requires files to be stored in `HDFS`, `Spark` does not.<br>
. `Spark` performs 100x faster than `Mapreduce` because it writes jobs in-memory. `Mapreduce` writes job on disk.

<b>Data processing</b><br>
. `MapReduce` (Hadoop) writes most data to <b>disk</b> after each `Map` and `Reduce` operation.<br>
. `Spark` keeps most of the data <b>in memory</b> after each transformation.<br>
. At the core of `Spark` there are `Resilient Distributed Datasets` also known as `RDDs`.<br>
. An `RDD` has 4 main features:<br>

1. Distributed collection of data
2. Fault-tolerant
3. Parallel operations which are partitioned
4. An RDD can use many data sources

. `RDDs` are immutable, cacheable and lazily evaluated.<b>
. There are 2 types of `RDD` operations:<br>
  
  1. Transformations: recipes to follow
  2. Actions: performs recipe's instructions and returns a result
  
  <b>Environment options for `Scala` and `Spark`</b>
  
  1. Text editors, such as `Sublime Text` and `Atom`
  2. IDEs (Integrated Development Environments), such as `IntelliJ` and `Eclipse`
  3. Notebooks, such as `Jupyter`, `Zeppelin` and `Databricks`

# Resources

https://twitter.com/ofcwilson
https://www.fathersinfashion.com/blog/2018/10/29/member-spotlight-caleb-wilson
https://twitter.com/_msl92
https://twitter.com/manwellreyes

I've uploaded a `.zip` which contains useful slides `MachineLearning`, `Spark` and `Scala`.<br>
<b>https://bit.ly/2zkcrP7</b>
  
## Author

* **Isaac Arnault** - Introducing Machine Learning using Spark-Scala - Related tags: #EC2 #TLS #AWSCLI #Linux
