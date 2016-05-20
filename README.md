# gosu-archetype-simple
Our first attempt at a Maven Archetype.  This can be executed via the command-line, or using IntelliJ IDEA.

The Archetype defines a simple Gosu project template and creates the project using the user-supplied values for groupId, artifactId and version.

## Command-line execution
Command-line options will vary slightly depending on if the archetype itself is a release version or not (SNAPSHOT builds are not available in the default repository).

### Release versions

```
$ mvn archetype:generate \
-DgroupId=<your project's groupId> \
-DartifactId=<your project's artifactId> \
-Dversion=1.0-SNAPSHOT \
-DarchetypeGroupId=org.gosu-lang.archetypes \
-DarchetypeArtifactId=gosu-archetype-simple \
-DarchetypeVersion=1.13.4 \
```

### Snapshot versions
```
$ mvn archetype:generate \
-DgroupId=<your project's groupId> \
-DartifactId=<your project's artifactId> \
-Dversion=1.0-SNAPSHOT \
-DarchetypeGroupId=org.gosu-lang.archetypes \
-DarchetypeArtifactId=gosu-archetype-simple \
-DarchetypeVersion=1.13.4-SNAPSHOT \
-DarchetypeRepository=https://oss.sonatype.org/content/repositories/snapshots
```

Change to the newly-created project's directory:
```
$ cd <your project's artifactId>
```

Execute and verify test(s) pass:
```
$ mvn test
...
-------------------------------------------------------
 T E S T S
-------------------------------------------------------
Running <your project's groupId>.FooTest
newing a Foo
Hello, got the argument 'eureka'
Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 1.768 sec

Results :

Tests run: 1, Failures: 0, Errors: 0, Skipped: 0

[INFO] ------------------------------------------------------------------------
[INFO] BUILD SUCCESS
[INFO] ------------------------------------------------------------------------
...
```
