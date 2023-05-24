# Snowflake Ingest SDK Java Examples
This example code was extracted from [snowflake-ingst-java
](https://github.com/snowflakedb/snowflake-ingest-java) repo, to help customers test out the Snowflake Ingest SDK more easily. Please refer to that repo for the latest "official" example code.   

**PLEASE NOTE:** This example project is not an official Snowflake offering. It comes with no support or warranty.



## Prerequisites

### Java 8+

The Snowflake Ingest Service SDK can only be used with Java 8 or higher.

### A 2048-bit RSA key pair

Snowflake Authentication for the Ingest Service requires creating a 2048
bit RSA key pair and, registering the public key with Snowflake. For
detailed instructions, please visit the relevant [Snowflake
Documentation Page](https://docs.snowflake.com/en/user-guide/key-pair-auth.html).

### Maven (Developers only)

These ingest examples are packaged in a Maven project, so you will need Maven to load dependencies, and then compile and
run the code.

## Setup process

 

### Create required Snowflake objects
Please make sure that the following objects exist in your account.
#### Required Snowflake objects for Snowpipe example
```
create or replace database TESTDB;
```

#### Required Snowflake objects for Snowpipe Streaming example

```
create or replace database MY_DATABASE;
create or replace schema MY_SCHEMA;
create or replace table MY_TABLE(c1 number);
```

### Populate connection profile
In the top-level of this project, you will need to create a connection profile with the filename`profile.json`.  Please refer to the example `profile.json.example` for a sample of this file.


### Configure logging (optional)
This example repo is configured to use logback-classic for logging, but any slf4j-compatible Java logging framework (e.g. log4j) could be used instead.

By default, the root logger is set to `INFO` level logging,  but you can easily change the logging configuration in the file `src/main/java/resources/logback.xml`.

**PLEASE NOTE:** If you make changes to the logging config file, you will need to recompile the Java code (see below) for the changes to take effect.

More info on configuring logback: https://logback.qos.ch/manual/configuration.html#syntax 

### Compile example code

```
mvn compile
```

## Run examples
The following commands assume that your working directory is the root of this project. 

### Snowpipe example

```
export SNOWFLAKE_ACCOUNT=myaccount
export SNOWFLAKE_USER=someuser
export SNOWFLAKE_PASSWORD=somepassword
mvn exec:java -Dexec.mainClass="net.snowflake.ingest.example.SnowflakeIngestBasicExample" 
``` 

### Snowpipe Streaming example

```
mvn exec:java -Dexec.mainClass="net.snowflake.ingest.streaming.example.SnowflakeStreamingIngestExample"
```