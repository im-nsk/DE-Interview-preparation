PySpark Basic

▪️ What is PySpark, and how does it relate to Apache Spark?
Answer: PySpark is the Python API for Apache Spark. Apache Spark is an open-source, distributed computing system that processes large datasets efficiently. PySpark allows Python programmers to write Spark applications using Python code, leveraging Spark's powerful features like parallel computing, fault tolerance, and in-memory processing.

▪️ What are the advantages of using PySpark over other big data tools?
Answer: PySpark offers several advantages:
Scalability: It can scale up to handle large datasets across a cluster of machines.
Speed: In-memory processing speeds up computation compared to disk-based systems like Hadoop.
Ease of Use: PySpark uses Python, which is easier for many developers compared to Java or Scala.
Integration: It integrates well with big data tools like Hadoop, HDFS, and other Spark libraries like MLlib for machine learning.

▪️ What is RDD in PySpark, and how does it differ from DataFrames?
Answer: RDD (Resilient Distributed Dataset) is the core data structure in Spark. It is a distributed collection of objects that can be processed in parallel. RDDs are fault-tolerant and can recover from node failures.
Difference:
RDDs: Low-level, type-safe, and provide more control but are less optimized.
DataFrames: Higher-level, organized like tables with columns, and provide optimization through the Catalyst engine, making them faster and easier to use.

▪️ Explain the concept of lazy evaluation in PySpark.
Answer: Lazy evaluation means that when you define transformations (like map() or filter()), PySpark does not immediately execute them. Instead, it builds a plan (DAG - Directed Acyclic Graph) of transformations. The execution only happens when an action (like collect(), count(), or save()) is called. This approach optimizes the processing by combining and optimizing tasks before execution.

▪️ What are transformations and actions in PySpark? Give examples of each.
Answer:
Transformations: Operations that create a new RDD/DataFrame but do not execute immediately (lazy evaluation). Examples: map(), filter(), select(), groupBy().
Actions: Operations that trigger the execution of transformations and return a result. Examples: collect(), count(), show(), saveAsTextFile().

▪️ How does PySpark handle parallelism and partitioning?
Answer: PySpark divides large datasets into smaller chunks called partitions. These partitions are distributed across different nodes in a cluster, allowing the tasks to run in parallel. This parallelism improves processing speed. You can control partitioning using methods like repartition() and coalesce().

▪️ What is the difference between map() and flatMap() transformations in PySpark?
Answer:
map(): Applies a function to each element of the RDD/DataFrame and returns an RDD/DataFrame with the same number of elements.
flatMap(): Similar to map(), but it can return multiple values (or no value) for each input element. It "flattens" the result, meaning it combines all the returned values into a single collection.

▪️ How do you create a DataFrame in PySpark? List different ways.
Answer: You can create a DataFrame in PySpark in several ways:
From a collection: Using spark.createDataFrame().
From an RDD: By converting an existing RDD to a DataFrame.
From a file: Reading data from sources like CSV, JSON, or Parquet using spark.read.csv(), spark.read.json(), or spark.read.parquet().
From a table: Using SQL to create a DataFrame from a database table.

▪️ Explain the concept of SparkSession and how it is used.
Answer: SparkSession is the entry point for programming with PySpark. It allows you to create DataFrames, access the Spark SQL interface, and interact with various Spark components. You create a SparkSession using:

from pyspark.sql import SparkSession
spark = SparkSession.builder.appName("AppName").getOrCreate()
It combines all previous entry points like SQLContext, HiveContext, and SparkContext.

▪️ How do you perform filtering and aggregation operations on DataFrames in PySpark?
Answer:
Filtering: Use the filter() or where() method to select rows based on conditions.
df.filter(df["age"] > 25).show()

Aggregation: Use the groupBy() method along with aggregation functions like sum(), avg(), count().
df.groupBy("department").agg({"salary": "avg"}).show()


.... coming soon stay update