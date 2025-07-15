This is a simple that models OPC data according to the motor model and sends it to MQTT.

To run this project, use the following `deployment.json`

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
        "deployFile": "single-project/motors.json",
        "repoName": "highbyte-samples",
        "ref": "master"
      },
      "keyPaths": []
    }
  ]
}
```
