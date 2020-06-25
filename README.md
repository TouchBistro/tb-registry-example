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
