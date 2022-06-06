# avroStreamExample
Consumer and Producer static/void/mains for Apache Pulsar, using the Avro schema.

The Producer code is there, but the pom.xml is set up to recognize `AvroSchemaConsumerExample.java` as the `main`.
Ensure that Apache Pulsar is running locally.  Topics will be created at runtime, if they do not exist.
Run the `AvroSchemaProducerExample.java` code from within an IDE, or manually produce messages which match the Payment schema.

Running the AvroSchemaConsumerExample from _outside_ an IDE requires the following steps:

```
mvn clean install
```

This should compile the Java classes _and_ build the `avrostreamexample-0.0.1-SNAPSHOT-jar-with-dependencies.jar` file.
Note that Maven will put the compiled jar into the `target/` directory.  Running the jar should produce output similar to this:

```
% java -jar target/avrostreamexample-0.0.1-SNAPSHOT-jar-with-dependencies.jar

SLF4J: Failed to load class "org.slf4j.impl.StaticLoggerBinder".
SLF4J: Defaulting to no-operation (NOP) logger implementation
SLF4J: See http://www.slf4j.org/codes.html#StaticLoggerBinder for further details.
Jun 06, 2022 8:17:50 AM org.apache.pulsar.shade.io.netty.resolver.dns.DnsServerAddressStreamProviders <clinit>
WARNING: Can not find org.apache.pulsar.shade.io.netty.resolver.dns.macos.MacOSDnsServerAddressStreamProvider in the classpath, fallback to system defaults. This may result in incorrect DNS resolutions on MacOS.
Checking for messages on avro-payments
key = id-0, value = avrostreamexample.Payment@150ab4ed
key = id-1, value = avrostreamexample.Payment@3c435123
key = id-2, value = avrostreamexample.Payment@50fe837a
key = id-3, value = avrostreamexample.Payment@3a62c01e
key = id-4, value = avrostreamexample.Payment@7a8fa663
key = id-5, value = avrostreamexample.Payment@5ce33a58
key = id-6, value = avrostreamexample.Payment@78a287ed
key = id-7, value = avrostreamexample.Payment@546ccad7
key = id-8, value = avrostreamexample.Payment@5357c287
key = id-9, value = avrostreamexample.Payment@1623134f
```
