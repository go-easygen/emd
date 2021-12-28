# emd
<!-- ALL-CONTRIBUTORS-BADGE:START - Do not remove or modify this section -->
[![All Contributors](https://img.shields.io/badge/all_contributors-2-orange.svg?style=flat-square)](#contributors-)
<!-- ALL-CONTRIBUTORS-BADGE:END -->

[![MIT License](http://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![GoDoc](https://godoc.org/github.com/go-easygen/emd?status.svg)](http://godoc.org/github.com/go-easygen/emd)
[![Go Report Card](https://goreportcard.com/badge/github.com/go-easygen/emd)](https://goreportcard.com/report/github.com/go-easygen/emd)
[![Build Status](https://github.com/go-easygen/emd/actions/workflows/go-release-build.yml/badge.svg?branch=master)](https://github.com/go-easygen/emd/actions/workflows/go-release-build.yml)
[![PoweredBy WireFrame](https://github.com/go-easygen/wireframe/blob/master/PoweredBy-WireFrame-B.svg)](http://godoc.org/github.com/go-easygen/wireframe)

Enhanced Markdown template processor.


## TOC
- [emd - Enhanced Markdown template processor](#emd---enhanced-markdown-template-processor)
- [Usage](#usage)
  - [$ emd](#-emd)
  - [Examples](#examples)
- [Install Debian/Ubuntu package](#install-debianubuntu-package)
- [Download/install binaries](#downloadinstall-binaries)
  - [The binary executables](#the-binary-executables)
  - [Distro package](#distro-package)
  - [Debian package](#debian-package)
- [Install Source](#install-source)
- [Contributors](#contributors-)

## emd - Enhanced Markdown template processor

## Usage

### $ emd
```sh
emd - 1.0.2

Usage
  -h	Show help
  -help
    	Show help
  -v	Show version
  -version
    	Show version

Commands
	gen	Process an emd file.
	init	Init a basic emd file.
```

### Examples

For examples and further details, check out the [original README](https://github.com/mh-cbon/emd).

## Install Debian/Ubuntu package

    apt install emd

## Download/install binaries

- The latest binary executables are available 
as the result of the Continuous-Integration (CI) process.
- I.e., they are built automatically right from the source code at every git release by [GitHub Actions](https://docs.github.com/en/actions).
- There are two ways to get/install such binary executables
  * Using the **binary executables** directly, or
  * Using **packages** for your distro

### The binary executables

- The latest binary executables are directly available under  
https://github.com/go-easygen/emd/releases/latest 
- Pick & choose the one that suits your OS and its architecture. E.g., for Linux, it would be the `emd_verxx_linux_amd64.tar.gz` file. 
- Available OS for binary executables are
  * Linux
  * Mac OS (darwin)
  * Windows
- If your OS and its architecture is not available in the download list, please let me know and I'll add it.
- The manual installation is just to unpack it and move/copy the binary executable to somewhere in `PATH`. For example,

``` sh
tar -xvf emd_*_linux_amd64.tar.gz
sudo mv -v emd_*_linux_amd64/emd /usr/local/bin/
rmdir -v emd_*_linux_amd64
```


### Distro package

- Packages available for Linux distros are
  * [Alpine Linux](https://cloudsmith.io/~suntong/repos/repo/setup/#formats-alpine)
  * [Debian](https://cloudsmith.io/~suntong/repos/repo/setup/#formats-deb)
  * [RedHat](https://cloudsmith.io/~suntong/repos/repo/setup/#formats-rpm)

The repo setup instruction url has been given above.
For example, for [Debian](https://cloudsmith.io/~suntong/repos/repo/setup/#formats-deb) --

### Debian package


```sh
curl -1sLf \
  'https://dl.cloudsmith.io/public/suntong/repo/setup.deb.sh' \
  | sudo -E bash

# That's it. You then can do your normal operations, like

sudo apt-get update
apt-cache policy emd

sudo apt-get install -y emd
```

## Install Source

To install the source code instead:

```
go get -v -u github.com/go-easygen/emd
```


## Contributors ✨

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->
<!-- prettier-ignore-start -->
<!-- markdownlint-disable -->
<table>
  <tr>
    <td align="center"><a href="https://github.com/suntong"><img src="https://avatars.githubusercontent.com/u/422244?v=4?s=100" width="100px;" alt=""/><br /><sub><b>suntong</b></sub></a><br /><a href="https://github.com/go-easygen/emd/commits?author=suntong" title="Code">💻</a> <a href="#ideas-suntong" title="Ideas, Planning, & Feedback">🤔</a> <a href="#design-suntong" title="Design">🎨</a> <a href="#data-suntong" title="Data">🔣</a> <a href="https://github.com/go-easygen/emd/commits?author=suntong" title="Tests">⚠️</a> <a href="https://github.com/go-easygen/emd/issues?q=author%3Asuntong" title="Bug reports">🐛</a> <a href="https://github.com/go-easygen/emd/commits?author=suntong" title="Documentation">📖</a> <a href="#blog-suntong" title="Blogposts">📝</a> <a href="#example-suntong" title="Examples">💡</a> <a href="#tutorial-suntong" title="Tutorials">✅</a> <a href="#tool-suntong" title="Tools">🔧</a> <a href="#platform-suntong" title="Packaging/porting to new platform">📦</a> <a href="https://github.com/go-easygen/emd/pulls?q=is%3Apr+reviewed-by%3Asuntong" title="Reviewed Pull Requests">👀</a> <a href="#question-suntong" title="Answering Questions">💬</a> <a href="#maintenance-suntong" title="Maintenance">🚧</a> <a href="#infra-suntong" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></td>
    <td align="center"><a href="https://github.com/mh-cbon"><img src="https://avatars.githubusercontent.com/u/17096799?v=4?s=100" width="100px;" alt=""/><br /><sub><b>mh-cbon</b></sub></a><br /><a href="https://github.com/go-easygen/emd/commits?author=mh-cbon" title="Code">💻</a> <a href="#ideas-mh-cbon" title="Ideas, Planning, & Feedback">🤔</a> <a href="#design-mh-cbon" title="Design">🎨</a> <a href="#data-mh-cbon" title="Data">🔣</a> <a href="https://github.com/go-easygen/emd/commits?author=mh-cbon" title="Tests">⚠️</a> <a href="https://github.com/go-easygen/emd/issues?q=author%3Amh-cbon" title="Bug reports">🐛</a> <a href="https://github.com/go-easygen/emd/commits?author=mh-cbon" title="Documentation">📖</a> <a href="#blog-mh-cbon" title="Blogposts">📝</a> <a href="#example-mh-cbon" title="Examples">💡</a> <a href="#tutorial-mh-cbon" title="Tutorials">✅</a> <a href="#tool-mh-cbon" title="Tools">🔧</a> <a href="#platform-mh-cbon" title="Packaging/porting to new platform">📦</a> <a href="https://github.com/go-easygen/emd/pulls?q=is%3Apr+reviewed-by%3Amh-cbon" title="Reviewed Pull Requests">👀</a> <a href="#question-mh-cbon" title="Answering Questions">💬</a> <a href="#maintenance-mh-cbon" title="Maintenance">🚧</a> <a href="#infra-mh-cbon" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a></td>
  </tr>
</table>

<!-- markdownlint-restore -->
<!-- prettier-ignore-end -->

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
