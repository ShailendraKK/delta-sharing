
To compile, run

```
build/sbt compile
```

To generate JAR file, run

```
build/sbt publishLocal
```

The jar file will be generated in the target folder of server directory.

To install the generated jar file in local Maven repo, run 

```
cd <path_to_jar_file>  # jar file should be in server/target/scala-2.12
mvn install:install-file -Dfile=<jar_file_name> -DgroupId=io.delta -DartifactId=delta-sharing-server_2.12 -Dversion=1.0.0-SNAPSHOT -Dpackaging=jar -DgeneratePom=true.
```

To access data from AWS S3, AWS access key id and key needs to be exported using below commands:

```
export AWS_ACCESS_KEY_ID=<aws_key_id>
export AWS_SECRET_ACCESS_KEY=<aws_acess_key>
```

After installing jar, the JUnit test can be run by following below steps:

``` 
cd jarTest
mvn test
```

To sync the fork with upstream repo, follow the steps given below:

1. Set up upstream

```
git remote add upstream https://github.com/delta-io/delta-sharing.git
```

2. Fetch the branches and their respective commits from the upstream repository

```
git fetch upstream
``

3. Check out your fork's local default branch - in this case, we use main

```
git checkout main
```

4. Merge the changes from the upstream default branch - in this case, upstream/main - into your local default branch

```
git merge upstream/main
```

5. If there are any merge conflicts, resolve them.

For more details on how to sync the fork, follow https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/working-with-forks/syncing-a-fork
