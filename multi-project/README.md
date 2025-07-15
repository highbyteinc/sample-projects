This project pulls two fragments from the same repository. The first fragment, named `models_and_it_connections.json`, contains a model definition and an MQTT connection. This represents an example of IT-owned definitions that a site can use.

The second fragment, called `site.json`, includes site-level connections, instances, and pipelines that reference the model and MQTT connection. Once deployed, both fragments are merged into a single runtime configuration.

Note: This setup could easily be adapted to pull the fragments from different repositories, but for simplicity, they are included in the same repository.

Use the following `deployment.json` file to load this project.
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
        "deployFile": "multi-project/models_and_it_connections.json",
        "repoName": "highbyte-samples",
        "ref": "master"
      },
      "keyPaths": []
    },
    {
      "details": {
        "type": "git",
        "deployFile": "multi-project/site.json",
        "repoName": "highbyte-samples",
        "ref": "master"
      },
      "keyPaths": []
    }

  ]
}
```
