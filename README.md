## Compile example code

```
mvn compile
```

## Run examples

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