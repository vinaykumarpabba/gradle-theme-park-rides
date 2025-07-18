
- We can also do token substitution while copying files.
- We can add the wrapper by executing the `gradle wrapper` command.
- `./gradlew --version` will show the version of Gradle being used.
- `./gradlew wrapper --gradle-version=8.0` will update the wrapper to a specific version.
- `git rm -r --cached .gradle` to remove the `.gradle` directory from Git cache.
- `gradle projects` will list all the projects in the build.
- `gradle tasks` will list all the tasks available in the build. There are different groups of tasks. `Build Setup tasks`, `Help tasks`, etc.
- `generateDescriptions` and `zipDescriptions` are not part of any group. `gradle tasks --all` will show all tasks including those not in any group.
- We can run multiple tasks by separating them with a space, e.g., `gradle generateDescriptions zipDescriptions`.
- When we run `./gradlew`, it runs the `help` default task. We can customize this by specifying a different default task in the `build.gradle` file. `defaultTasks 'generateDescriptions'` will set `generateDescriptions` as the default task.
- We can also specify a part of the task name to run. For example, `gradle h` will run the `help` task. `gradle gD for generateDescriptions` will run the `generateDescriptions` task.
- command line arguments. 
- `gradle --help` which is different from `gradle help` will show the command line options available for Gradle.
- `gradle gD --info` will run the `generateDescriptions` task with additional logging information. `gradle --info gD` will also work.
- `--console` has different options like `plain`, `rich`, and `auto`. `--console=plain` will show the output in plain text without any formatting. `--console=rich` will show the output with colors and formatting. `--console=auto` will automatically choose the best option based on the terminal capabilities. `./gradlew gD --console=verbose`


- Build life cycle: 
  - Initialization: Gradle determines which projects are going to take part in the build. Executes the `settings.gradle` file.
  - Configuration: Gradle configures the projects and tasks that will be executed. Gradle learns about the tasks and their dependencies. This is where the `build.gradle` files are executed. Builds in-memory model of the project is created.
  - Execution: Gradle executes the tasks that were configured in the previous step. The tasks themselves are executed in the order they were configured. This is where the actual work is done.
- `./gradlew gD --info` log output is in three different phases.
- The `up-to-date` message during the execution phase indicates that the task has already been executed and its outputs are still valid, so it will not be executed again.

- There is also some stuff about the `Gradle Daemon` which is a long-running process that can speed up the build process by keeping the Gradle runtime in memory. It is started automatically when you run a Gradle command and will be reused for subsequent commands. You can stop the daemon with `./gradlew --stop`. Helps with faster builds by avoiding the overhead of starting a new JVM for each build.
- 
- We can also debug tasks from the command line using `--debug` option. This will provide detailed information about the task execution and can help in troubleshooting issues. Or using Intellij IDEA, we can run the Gradle task in debug mode by clicking on the debug icon next to the task in the Gradle tool window. This will allow us to set breakpoints and step through the code.
- 

