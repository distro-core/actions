# Github Action: DISTRO Core Keep Alive

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

For all original content supplied with this layer, unless otherwise
specified, is licensed as [LICENSE](../LICENSE).

## Usage

Action yaml

~~~ yaml
jobs:
  test:
    steps:
    - id: keepalive
      uses: distro-core/actions/keepalive@main
~~~
