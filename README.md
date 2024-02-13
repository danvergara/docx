# docx
![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/danvergara/docx?sort=semver)
[![Go Report Card](https://goreportcard.com/badge/github.com/danvergara/docx)](https://goreportcard.com/report/github.com/danvergara/docx)
[![GoDoc](https://pkg.go.dev/badge/github.com/danvergara/docx?status.svg)](https://pkg.go.dev/github.com/danvergara/docx?tab=doc)

## Introduction
docx is a simple library to creating DOCX file in Go.

## Getting Started
### Install
Go modules supported
```sh
go get github.com/danvergara/docx
```
Import:
```sh
import "github.com/danvergara/docx"
```

### Usage
**Example:**
```go
package main

import (
	"github.com/danvergara/docx"
)

func main() {
	f := docx.NewFile()
	// add new paragraph
	para := f.AddParagraph()
	// add text
	para.AddText("test")

	para.AddText("test font size").Size(22)
	para.AddText("test color").Color("808080")
	para.AddText("test font size and color").Size(22).Color("121212")

	nextPara := f.AddParagraph()
	nextPara.AddLink("google", `http://google.com`)

	f.Save("./test.docx")
}

```
