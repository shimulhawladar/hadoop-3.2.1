# <a href="https://github.com/shimulhawladar/hadoop-3.2.1/blob/main/Hadoop-3.2.1_Install" target="_blank"> Hadoop-3.2.1 </a> single node installation on linux Step by Step guide

##
 Replace User to Current OS User 
##



### Configure core site
Edit `core-site.xml` and replace the `configuration` element with the following:
``` 
<configuration>

    <property>
        	<name>fs.defaultFS</name>
        	<value>hdfs://localhost:9000</value>
    </property>

    <property>
        	<name>hadoop.tmp.dir</name>
        	<value>/usr/local/hadoop/tmp</value>
    </property>
    
</configuration>

```
##

### Configure HDFS
Edit `hdfs-site.xml` and replace the `configuration` element with the following:
```
<configuration>
    <property>
        	<name>dfs.replication</name>
        	<value>1</value>
    </property>

    <property>
        	<name>dfs.name.dir</name>
        	<value>file:///usr/local/hadoop/hadoop_data/namenode</value>
    </property>

    <property>
        	<name>dfs.data.dir</name>
        	<value>file:///usr/local/hadoop/hadoop_data/datanode</value>
    </property>
</configuration>
```
##

### Configure MapReduce and YARN site
Edit `mapred-site.xml` and replace the `configuration` element with the following:
```
<configuration>
  <property>
      	<name>mapreduce.framework.name</name>
      	<value>yarn</value>
  </property>
</configuration>
```

Edit `yarn-site.xml` and replace the `configuration` element with the following
```
<configuration>
	<property>
	    	<name>mapreduceyarn.nodemanager.aux-services</name>
	    	<value>mapreduce_shuffle</value>
	</property>
<!-- Site specific YARN configuration properties -->

</configuration>
```
