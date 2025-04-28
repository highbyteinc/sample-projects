> [!IMPORTANT]
> This requires version 4.2 or newer.

This repo includes sample projects to get started with the Intelligence Hub. To leverage these sample projects do the following.

1. Create a deployment.json file in the runtime directory
2. Add the following information to the file. You will need to change this configuration depending on what project you want to load. Examples are provided in each project directory.

```json
{
  "version": 0,
  "repos": [
    {
      "type": "git",
      "uri": "https://github.com/highbyteinc/sample-projects.git",
      "name": "highbyte-samples",
      "author": "",
      "email": ""
    }
  ],
  "fragments": [
    {
      "details": {
        "type": "git",
        "deployFile": "deployment.json",
        "repoName": "highbyte-samples",
        "ref": "test"
      },
      "keyPaths": []
    }
  ]
}
```

- repos.name is the name of the repo relative to this file
- fragments.repoName must match the repos.name
- fragments.details.deployFile is the path to the sample you want to load in the repo (ex. /motors/motors.json)
- fragments.details.ref is the branch name in the repo
- fragments.keyPaths are paths inside the .json file to load. For example project.models would only load models

3. Open the start-windows.bat (or start-linux.bat), find the java command, and add in the **highbyte.deployment.file** java option to point to the deployment.json file like so 
```
java !JAVA_OPTS! -Dhighbyte.deployment.file="deployments.json" -jar intelligencehub-runtime.jar start
```
4. Launch the start bat file. The runtime will load and start with the project
