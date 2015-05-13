# meetup-spark

# Download

1. [Hadoop](http://spark.apache.org/downloads.html) - download prebuilt for hadoop 2.6
2. [Squirrel SQL](http://sourceforge.net/projects/squirrel-sql/files/) - download and install

# Configure

Copy and edit [the environment settings](https://raw.githubusercontent.com/jeffusan/meetup-spark/master/bashrc) in your shell.

Copy and edit [the hive config](https://raw.githubusercontent.com/jeffusan/meetup-spark/master/conf/hive-site.xml) to $SPARK_HOME/conf.

# Run

```
#> $SPARK_HOME/sbin/start-all.sh
```

Check that you can access the webui http://127.0.0.1:9080

# Add data

Run the glorified scala console.

```
#> $SPARK_HOME/bin/spark-shell
```

```
scala>val df = sqlContext.jsonFile("path/to/data.json")
scala>df.saveAsTable("mydata")
```

close shell

# Start thrift server

```
#> $SPARK_HOME/sbin/start-thriftserver.sh
```

Test with beeline

```
#> $SPARK_HOME/bin/beeline
```

```
beeline> !connect jdbc:hive2://localhost:10000
```

(this prompts for a user and password. user is your system username, password is empty)


# Configure Squirrel


...

[Spark SQL Documentation](https://spark.apache.org/sql/)
