# emd

[![travis Status](https://travis-ci.org/mh-cbon/emd.svg?branch=master)](https://travis-ci.org/mh-cbon/emd)[![appveyor Status](https://ci.appveyor.com/api/projects/status/github/mh-cbon/emd?branch=master&svg=true)](https://ci.appveyor.com/project/mh-cbon/emd)
[![GoDoc](https://godoc.org/github.com/mh-cbon/emd?status.svg)](http://godoc.org/github.com/mh-cbon/emd)


Enhanced Markdown template processor.


# Install

Check the [release page](https://github.com/mh-cbon/emd/releases)!

#### Go

```sh
go get github.com/mh-cbon/emd
```


#### Chocolatey

```sh
choco install emd
```

#### linux rpm/deb repository

```sh
wget -O - https://raw.githubusercontent.com/mh-cbon/latest/master/source.sh \
| GH=mh-cbon/emd sh -xe
# or
curl -L https://raw.githubusercontent.com/mh-cbon/latest/master/source.sh \
| GH=mh-cbon/emd sh -xe
```

#### linux rpm/deb standalone package

```sh
curl -L https://raw.githubusercontent.com/mh-cbon/latest/master/install.sh \
| GH=mh-cbon/emd sh -xe
# or
wget -q -O - --no-check-certificate \
https://raw.githubusercontent.com/mh-cbon/latest/master/install.sh \
| GH=mh-cbon/emd sh -xe
```

# Usage


###### $ emd -help
```sh
emd - 1.1.1

Usage
  -h	Show help
  -help
    	Show help
  -version
    	Show version

Commands
	gen	Process an emd file.
```


###### $ emd gen -help
```sh
emd - 1.1.1

Command "gen": Process an emd file.
  -data string
    	JSON map of data
  -h	Show help
  -help
    	Show help
  -in string
    	Input src file (default "README.e.md")
  -out string
    	Output destination, defaults to stdout (default "-")
```

# Cli examples

```sh

# Reads content of README.e.md, outputs to README.md
emd gen -out README.md

# same with data injections,
emd gen -out README.md --data='{"CsUUID":"xxxx"}'

```

# Templates helper

#### Data

| Key | Description |
| --- | --- |
| Name | Project directory name (filepath.Base(cwd)). |
| User | Project directory name (filepath.Base(cwd)). |
| ProviderURL | The vcs provider url (example: github.com). |
| ProviderName | The vcs provider name (example: github). |
| URL | Project url as determined by the cwd (example: github.com/mh-cbon/emd). |
| Branch | Current vcs branch name (defaults to master). |

#### Function

| Name | Description |
| --- | --- |
| file(f string) | read and display a file enclosed with triples backquotes. The highlight defaults to `go`. |
| cli(bin string, args ...string) | execute and display a command line enclosed with triples backquotes. The highlight defaults to `sh`. |
| pkgdoc(files ...string) | reads the first of files, lookup for its package comment and shows it as plain text. |

#### Templates

| Name | Description | Params |
| --- | --- | --- |
| gh/releases | Show a text to link the release page. | |
| badge/travis | Show a travis badge. | |
| badge/appveyor | Show an appveyor badge. | |
| badge/codeship | Show acodeship badge. | __CsUUID__: the codeship project UUID. Add it with `--data '{"CsUUID": "xxxxxx"}'` |
| choco/install | Show an sh snippet to install the package with chocolatey. | |
| linux/gh_src_repo | Show an sh snippet to install the package via linux repositories (deb/rpm). | |
| linux/gh_pkg | Show an sh snippet to install the package via linux packages (deb/rpm). | |
| glide/install | Show an sh snippet to install the package via `glide`. | |
| go/install | Show an sh snippet to install the package via `go get`. | |

# API example


###### > main_example.go
```go
// Demonstrates the generation
// of the given README.e.md source file
// to os.Stdout.

package main

import (
	"os"

	"github.com/mh-cbon/emd/emd"
	"github.com/mh-cbon/emd/std"
)

func genExample() {

	// make a new instance of emd.Generator.
	gen := emd.NewGenerator()

	// set the main template.
	if err := gen.AddFileTemplate("README.e.md"); err != nil {
		panic(err)
	}

	// set the data available in templates.
	gen.SetDataMap(map[string]interface{}{"Name": "projectname"})

	// register a plugin
	if err := std.Register(gen); err != nil {
		panic(err)
	}

	// process the template.
	if err := gen.Execute(os.Stdout); err != nil {
		panic(err)
	}
}
```

# Recipes

#### Generate HTML content

To directly generate HTML content out of `emd` output, for example, with `gh-markdown-cli`,

```sh
npm install gh-markdown-cli -g
emd gen | mdown
```

#### Release the project

```sh
gump patch -d # check
gump patch # bump
```
