
This is the project used in the 4.2 webinar. To run this project, use the following `deployment.json` and follow the instructions here https://guide.highbyte.com/setup/git/example/

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
