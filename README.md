# HADOOP Installation and Setup

### First - Install Hombrew:
https://brew.sh/

## Open Terminal Window:

### Second - Install Java:

`$ brew install java`

#### Check version: 

`$ java -version` 
(Should be 1.8)

#### Install JDK

`$ brew install adoptopenjdk8`

### Third - Install Hadoop:

`$ brew install hadoop`

* This will be at the path: /usr/local/Cellar/hadoop and should be version 3.3.0 as of today (Nov 23, 2020) *

### Fourth - Changes to files:

I prefer to open up the file itself in my editor (I use VSCode), so I use:

`$ cd /usr/local/Cellar/hadoop`

to access the file from terminal, and then:

`$ code .`

to open it in VSCode. Otherwise, you could do:

`$ cd /usr/local/Cellar`

to access the file from terminal, and then:

`$ open hadoop`

### Now that it is open, we can access the specific files we need to edit.

In "core-site.xml", we will replace the configuration with:

`
<configuration>
  <property>
    <name>fs.defaultFS</name>
    <value>hdfs://localhost:9000</value>
  </property>
</configuration>
`

