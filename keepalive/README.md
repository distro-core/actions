# Github Action: DISTRO Core Keep Alive

This repository supplies a GitHub Action used as part of the build
process for DISTRO Core.

## LICENSE Information

## Usage:

Example:

~~~ yaml
jobs:
  test:
    steps:
    - id: keepalive
      uses: distro-core/actions/keepalive@main
~~~
