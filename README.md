# gorm-zerolog

[![Build Status](https://travis-ci.org/gorpher/gorm-zerolog.svg?branch=master)](https://travis-ci.org/gorpher/gorm-zerolog)
[![codecov](https://codecov.io/gh/gorpher/gorm-zerolog/branch/master/graph/badge.svg)](https://codecov.io/gh/gorpher/gorm-zerolog)
[![GoDoc](https://godoc.org/github.com/gorpher/gorm-zerolog?status.svg)](https://godoc.org/github.com/wantedly/gorm-zerolog)
[![license](https://img.shields.io/github/license/gorpher/gorm-zerolog.svg)](./LICENSE)

Alternative logging with [zerolog](https://github.com/rs/zerolog) for [GORM](http://jinzhu.me/gorm) ⚡️

In comparison to gorm's default logger, `gorm-zerolog` is faster, reflection free, low allocations and no regex
compilations.

## Example

```go
package main

import (
	"github.com/jinzhu/gorm"
	"github.com/gorpher/gorm-zerolog"
)

const (
	databaseURL = "postgres://postgres:@localhost/gormzr?sslmode=disable"
)

func main() {
	logger, err = zerolog.NewProduction()
	if err != nil {
		panic(err)
	}

	db, err := gorm.Open("postgres", databaseURL)
	if err != nil {
		panic(err)
	}
	db.LogMode(true)
	db.SetLogger(gorm - zerolog.New(logger))

	// ...
}
```
