# Gradle Cheat Sheet
## Basic Commands
- gradle tasks: Lists all available tasks.
- gradle build: Builds the project.
- gradle clean: Cleans the build directory.
- gradle run: Runs the project.
- gradle test: Runs the tests.
## Dependencies
- compile: Adds a dependency to the compile classpath.
- testCompile: Adds a dependency to the test compile classpath.
- runtime: Adds a dependency to the runtime classpath.
- testRuntime: Adds a dependency to the test runtime classpath.
## Plugins
- apply plugin: 'java': Applies the Java plugin.
- apply plugin: 'application': Applies the Application plugin.
- apply plugin: 'idea': Applies the IntelliJ IDEA plugin.
- apply plugin: 'eclipse': Applies the Eclipse plugin.
## Tasks
- task myTask: Defines a new task.
- dependsOn: Specifies the dependencies of a task.
- doFirst: Specifies the actions to be executed before the task.
- doLast: Specifies the actions to be executed after the task.
- inputs: Specifies the inputs of a task.
- outputs: Specifies the outputs of a task.
## Build Script
- repositories: Specifies the repositories to use for dependencies.
- dependencies: Specifies the dependencies of the project.
- sourceSets: Specifies the source sets of the project.
- jar: Configures the JAR task.
- test: Configures the test task.
- Gradle Wrapper
- gradle wrapper: Generates the Gradle wrapper files.
- ./gradlew: Runs the Gradle wrapper on Unix-based systems.
- gradlew.bat: Runs the Gradle wrapper on Windows-based systems.
## Miscellaneous
- gradle properties: Displays the project properties.
- gradle help: Displays the Gradle help.
- gradle -q: Runs Gradle in quiet mode.
- gradle -s: Runs Gradle in stacktrace mode.
