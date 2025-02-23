# Github Action: DISTRO Core Repo Init/Sync

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| env | Required | Desctiption |
| --- | --- | --- |
| REPO_MANIFEST_URL | X | repo manifest url |
| REPO_MANIFEST_NAME | X | repo manifest name |
| REPO_MANIFEST_REF | X | repo manifest ref |
| REPO_MANIFEST_LOCAL | X | repo manifest local-manifest.xml |

| outputs | Required | Desctiption |
| --- | --- | --- |
| manifest_url | - | repo manifest url |
| manifest_name | - | repo manifest name |
| manifest_ref | - | repo manifest branch/tag/commit-id |
| manifest_sha | - | repo manifest commit-id |
| manifest_xml_ref | - | repo manifest as XML refs |
| manifest_xml_sha | - | repo manifest as XML commit-id |
| manifest_json_ref | - | repo manifest as JSON refs |
| manifest_json_sha | - | repo manifest as JSON commit-id |

Action yaml

~~~ yaml
env:
  REPO_MANIFEST_URL: https://github.com/distro-core/distro-manifest.git
  REPO_MANIFEST_NAME: distro-head-scarthgap.xml
  REPO_MANIFEST_REF: main
  REPO_MANIFEST_LOCAL: >-
    <!-- <extend-project name="meta-distro" revision="main" /> -->
    <!-- <extend-project name="workflows-com-cexpress-bt" groups="default"/> -->

jobs:
  test:
    steps:
    - id: repo-manifest
      uses: distro-core/actions/repo@main
~~~
