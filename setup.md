Reference: https://gist.github.com/ankithooda/b0d624aec9b3ed2882713d59feba4b11
# Get SimpleDB_3.4.zip from here - http://www.cs.bc.edu/~sciore/simpledb/


# Tested using OpenJDK 17.0.2

# Unzip SimpleDB_3.4
> unzip SimpleDB_3.4.zip
> cd SimpleDB_3.4

# Create bin folder to store the compiled .class files
> mkdir -p bin/server
> mkdir -p bin/client

# Compile Server
> javac -d bin/server simpledb/server/*

# Compile the various Client programs

> javac -d bin/client simpleclient/SimpleIJ.java
> javac -d bin/client simpleclient/network/*
> javac -d bin/client simpleclient/embedded/*

# Now the bin/server contains all the class files for server
# and bin/client contains all the class files for running various sample clients


################ Run Server ##################

> cd bin/server/
> java simpledb.server.StartServer


################ Run Clients #################

> cd bin/client

# Create some sample data by running the CreateStudentDB and StudentMajor clients
> java network.CreateStudentDB
> java network.StudentMajor


# Run interactive client
> java SimpleIJ

# it will ask for connection string

Connect> 
jdbc:simpledb://localhost

# after providing the connection string, SQL> prompt appears, where one can type in the query.

SQL> select sname, majorid from student
      sname majorid
-------------------
        joe      10
        amy      20
        max      10
        sue      20
        bob      30
        kim      20
        art      30
        pat      20
        lee      10