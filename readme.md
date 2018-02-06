# Structor Sample

Sample of multiple Mkdocs versionned documentation build With Structor (https://mmatur.github.io/structor-sample/).

[Mesor Structor](https://github.com/containous/structor) is a tool to manage multiple documentation versions with Mkdocs.

## Prerequisites

* GitHub release used
* `requirements.txt` need to be present in repository root level on each branches
* `mkdocs.yml` need to be present in repository root level on each branches

## How it works

```shell
sudo ./structor --owner mmatur --repo-name="structor-sample" \
--dockerfile-url="https://raw.githubusercontent.com/mmatur/structor-sample/master/docs.Dockerfile" \
--menu.js-url="https://raw.githubusercontent.com/mmatur/structor-sample/master/traefik-menu.js.gotmpl" \
--exp-branch=master --debug
```

With this command Structor will :
* Download Dockerfile used to build documentation
* Fetch latest release on GitHub to generate documentation tag mark as `latest`
* List remote branches matching the pattern `origin/v*`. All of those branches will have their documentation generated
* `--exp-branch=master` will generate experimental documentation mark as experimental
* For each branches
  * Build the version selector
  * Build documentation

Versionned documentation will be available in `site` directory
