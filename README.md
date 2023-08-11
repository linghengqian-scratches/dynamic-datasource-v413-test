## dynamic-datasource-v413-test

- For https://github.com/linghengqian/spring-plugin-graalvm-agent-test
- Steps to reproduce on Ubuntu 22.04.3.
```shell
sudo apt install unzip zip curl sed -y
curl -s "https://get.sdkman.io" | bash
source "$HOME/.sdkman/bin/sdkman-init.sh"
sdk install java 17.0.8-graalce
sdk use java 17.0.8-graalce

git clone git@github.com:linghengqian/dynamic-datasource-v413-test.git
cd ./dynamic-datasource-v413-test/
./gradlew clean test
```

- Error Log at `./gradlew clean test` step.
```shell
$ ./gradlew clean test

> Task :test
OpenJDK 64-Bit Server VM warning: Sharing is only supported for boot loader classes because bootstrap classpath has been appended

AddRemoveDatasourceTest > testAddAndRemoveDataSource() FAILED
    com.baomidou.dynamic.datasource.exception.ErrorCreateDataSourceException at AddRemoveDatasourceTest.java:37
2023-08-11T18:46:07.504+08:00  INFO 6833 --- [ionShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource start closing ....
2023-08-11T18:46:07.504+08:00  INFO 6833 --- [ionShutdownHook] c.b.d.d.DynamicRoutingDataSource         : dynamic-datasource all closed success,bye

1 test completed, 1 failed

> Task :test FAILED

FAILURE: Build failed with an exception.

* What went wrong:
Execution failed for task ':test'.
> There were failing tests. See the report at: file:///home/linghengqian/TwinklingLiftWorks/git/public/dynamic-datasource-v413-test/build/reports/tests/test/index.html

* Try:
> Run with --scan to get full insights.

Deprecated Gradle features were used in this build, making it incompatible with Gradle 9.0.

You can use '--warning-mode all' to show the individual deprecation warnings and determine if they come from your own scripts or plugins.

For more on this, please refer to https://docs.gradle.org/8.2.1/userguide/command_line_interface.html#sec:command_line_warnings in the Gradle documentation.

BUILD FAILED in 4s
4 actionable tasks: 4 executed
```