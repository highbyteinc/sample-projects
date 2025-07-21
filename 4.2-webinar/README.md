
This is the project used in the 4.2 webinar. To run this project, follow the steps below.

1. Create a deployment.json file and paste in the content below
```
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
        "deployFile": "4.2-webinar/config.json",
        "repoName": "highbyte-samples",
        "ref": "master"
      },
      "keyPaths": []
    }
  ]
}
```
2. Launch the hub using Step #3 described here https://guide.highbyte.com/setup/git/example/. Below is an example using docker.
   ```
   docker run -v "path/to/deployment.json:/usr/highbyte/appData/deployment.json" -e HIGHBYTE_DEPLOYMENT_FILE=/usr/highbyte/appData/deployment.json -p 45245:45245 -p 1885:1885 -p 8885:8885 -p 45345:45345 --name highbyteGitExample highbyte:4.2.0
   ```
3. Verify you see the following message in the startup logs
   ```
   2025-07-21 17:51:12 | INFO    | Runtime | Successfully applied deployment using settings file located at /usr/highbyte/appData/deployment.json. Deployment built using 1 fragments from 1 repos.
   ```
4. Login and verify the configuration
