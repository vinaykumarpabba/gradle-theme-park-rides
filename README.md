
- We can also do token substitution while copying files.
- We can add the wrapper by executing the `gradle wrapper` command.
- `./gradlew --version` will show the version of Gradle being used.
- `./gradlew wrapper --gradle-version=8.0` will update the wrapper to a specific version.
- `git rm -r --cached .gradle` to remove the `.gradle` directory from Git cache.
- `gradle projects` will list all the projects in the build.
- `gradle tasks` will list all the tasks available in the build. There are different groups of tasks. `Build Setup tasks`, `Help tasks`, etc.
- `generateDescriptions` and `zipDescriptions` are not part of any group. `gradle tasks --all` will show all tasks including those not in any group.
- 