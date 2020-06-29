# tb-registry-example

This is a example registry to demonstrate usage of [`tb`](https://github.com/TouchBistro/tb) and provide a reference for how to setup a registry.

## Quick Start

This guide assumes you already have [homebrew](https://brew.sh/) installed.

Add TouchBistro's homebrew tap:
```
brew tap touchbistro/tap
```

Install `tb`:
```
brew install tb
```

Add this registry:
```
tb registry add TouchBistro/tb-registry-example
```

Run `postgres` and `redis`:
```
tb up -p db
```

## What's in this registry?

### Services

* `postgres`: Uses the `12.3-alpine` tag (https://hub.docker.com/_/postgres)
* `redis`: Uses the `6.0-alpine` tag (https://hub.docker.com/_/redis)

### Playlists

* `db`: Contains the `posgres` and `redis` services

    ```
    tb up -p db
    ```

### Validating Registry

`tb` provides the `tb registry validate` command to check that the files in a registry are valid. This will check for syntactical/schema correctness and make sure `tb` is able to read the registry files.

This is especially useful if the registry is used by multiple people to ensure that changes one person makes doesn't break `tb` for everyone else. In situations like this it can be useful to run this command in CI to ensure that no one merges a change that breaks the config.

This repository has CI configured using CircleCI. The config is stored in `.circleci/config.yml`. You can use this as a reference for how validating the registry in CI works and adapt it to your CI tool as desired.
