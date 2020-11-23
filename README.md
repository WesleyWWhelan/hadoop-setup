# HADOOP Single Node Setup (Mac)

## Installation and Setup

### First - Install Hombrew:
https://brew.sh/



### Second - Install Java:

Open Terminal Window

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

#### Now that it is open, we can access the specific files we need to edit.

In this repo, there are four files in the "changes" folder. Replace the files in hadoop on your computer, with these four files. Optionally, you could just copy the code out and replace the code instead of downloading the files.

### Fifth - Remove need for password:

`$ ssh-keygen -t rsa -P '' -f ~/.ssh/id_rsa`

`$ cat ~/.ssh/id_rsa.pub >> ~/.ssh/authorized_keys`

`$ chmod 0600 ~/.ssh/authorized_keys`

Check that it worked: 

`$ ssh localhost`

### Sixth - Format NameNode:

`$ cd /usr/local/cellar/hadoop/3.3.0/libexec/bin`

`$ hdfs namenode -format`

If prompted to re-format file system, press Y and accept.

## Run Session

1. Access sbin: `$ cd /usr/local/cellar/hadoop/3.3.0/libexec/sbin`

2. Run: `$ ./start-all.sh`

3. Check that running: `$ jps`

This should give something like:

```
99909 ResourceManager
7736 NameNode
86984 QuorumPeerMain
7977 SecondaryNameNode
122 NodeManager
8303 Jps
```


