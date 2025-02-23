# Github Action: DISTRO Core Sync S3

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

| secrets | Required | Desctiption |
| --- | --- | --- |
| AWS_ENDPOINT_URL | X | S3 DNS Endpoint |
| AWS_ACCESS_KEY_ID | X | S3 Access Key ID |
| AWS_SECRET_ACCESS_KEY | X | S3 Secret Access Key |

| inputs | Required | Desctiption |
| --- | --- | --- |
| src_dir | X | source directory path |
| dst_dir | X | destination bucket |
| expiry_days | - | expiry days |

| outputs | Required | Desctiption |
| --- | --- | --- |
| src_dir | - | source directory path |
| dst_dir | - | destination bucket |

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: s3cmd-dl-dir
      uses: distro-core/actions/s3cmd@main
      with:
        src_dir: ${{ steps.bitbake-targets.outputs.dl_dir }}
        dst_dir: s3://distro-core-downloads
        AWS_ENDPOINT_URL: ${{ secrets.AWS_ENDPOINT_URL }}
        AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
        AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
~~~
