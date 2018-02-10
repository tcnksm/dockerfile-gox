Dockerfile-gox 
====

[![MIT License](http://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)][LICENSE]
[![Docker Pulls](https://img.shields.io/docker/pulls/tcnksm/gox.svg?style=flat-square)][dockerhub]

[LICENSE]: https://github.com/tcnksm/dockerfile-gox/blob/master/LICENCE
[dockerhub]: https://registry.hub.docker.com/u/tcnksm/gox/

Dockerfile for Cross-compiling golang project with [mitchellh/gox](https://github.com/mitchellh/gox).

## Description

[docker-library/golang](https://github.com/docker-library/golang) (Docker official golang stack) also support image for cross-compile. With `Dockerfile-gox`, You can cross-compile your golang project parallelly. It's more fast when compiling for multiple platform.

## Supported tags

`tcnksm/gox` image support below tags. Link is its `Dockerfile`. 

- [`1.2.2` (1.2.2/Dockerfile)](1.2.2/Dockerfile)
- [`1.3` (1.3/Docekerfile)](1.3/Dockerfile)
- [`1.3.1` (1.3.1/Dockerfile)](1.3.1/Dockerfile)
- [`1.3.2` (1.3.2/Dockerfile)](1.3.2/Dockerfile)
- [`1.4` (1.4/Dockerfile)](1.4/Dockerfile)
- [`1.4.1` (1.4.1/Dockerfile)](1.4.1/Dockerfile)
- [`1.4.2` (1.4.2/Dockerfile)](1.4.2/Dockerfile)
- [`1.5` (1.5/Dockerfile)](1.5/Dockerfile)
- [`1.5.1` (1.5.1/Dockerfile)](1.5.1/Dockerfile)
- [`1.5.2` (1.5.2/Dockerfile)](1.5.2/Dockerfile)
- [`1.5.3` (1.5.3/Dockerfile)](1.5.3/Dockerfile)
- [`1.6` (1.6/Dockerfile)](1.6/Dockerfile)
- [`1.6.1` (1.6.1/Dockerfile)](1.6.1/Dockerfile)
- [`1.6.2` (1.6.2/Dockerfile)](1.6.2/Dockerfile)
- [`1.6.3` (1.6.3/Dockerfile)](1.6.2/Dockerfile)
- [`1.7` (1.7/Dockerfile)](1.7/Dockerfile)
- [`1.9` (1.9/Dockerfile)](1.9/Dockerfile)
- [`latest` (1.9/Dockerfile)](1.9/Dockerfile)

Tag is correspond to its golang version. 

## Usage

If you want to cross-compile with go v1.5:

```bash
$ docker run --rm -v "$(pwd)":/usr/src/myapp -w /usr/src/myapp tcnksm/gox:1.5 
```

Or if you want to cross-compile with go v1.4:

```bash
$ docker run --rm -v "$(pwd)":/usr/src/myapp -w /usr/src/myapp tcnksm/gox:1.4 
```

You can overwrite command. If you have Makefile with `gox`:

```bash
$ docker run --rm -v "$(pwd)":/usr/src/myapp -w /usr/src/myapp tcnksm/gox:1.5 make 
```

Or if you want to build for 64-bit linux and change output to `pkg` directory with your favor name:

```bash
$ docker run --rm -v "$(pwd)":/usr/src/myapp -w /usr/src/myapp tcnksm/gox:1.3.1 gox -osarch="linux/amd64" -output "pkg/{{.OS}}_{{.Arch}}/{{.Dir}}"
```

If you want to know `gox` arguments more, See documents in [mitchellh/gox](https://github.com/mitchellh/gox).

## Build 

To build image,

```bash
$ docker build -t tcnksm/gox:${VERSION} .
$ docker push tcnksm/gox:${VERSION}
```

## Contribution

1. Fork ([https://github.com/tcnksm/dockerfile-gox/fork](https://github.com/tcnksm/dockerfile-gox/fork))
1. Create a feature branch
1. Commit your changes
1. Rebase your local changes against the master branch
1. Push it to your remote repository
1. Create new Pull Request

## Author

[tcnksm](https://github.com/tcnksm)
