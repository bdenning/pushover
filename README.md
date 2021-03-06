# Pushover Golang Package

[![Documentation](https://godoc.org/github.com/bdenning/go-pushover?status.svg)](https://godoc.org/github.com/bdenning/go-pushover) [![Build Status](https://drone.io/github.com/bdenning/go-pushover/status.png)](https://drone.io/github.com/bdenning/go-pushover/latest) [![Coverage Status](https://coveralls.io/repos/bdenning/go-pushover/badge.svg?branch=master&service=github)](https://coveralls.io/github/bdenning/go-pushover?branch=master)

A golang package for sending notifications via https://api.pushover.net.

This library is **not intended for production use** and was written by its author as an exercise to learn more about golang. Please don't import it and use it in any projects that you care about.

# Package Example
You can use the pushover package within your golang applications as follows:
```Go
// Set your pushover API keys
token := "KzGDORePKggMaC0QOYAMyEEuZJnyUi"
user := "e9e1495ec75826de5983cd1abc8031"

// Send your message
m := pushover.NewMessage(token, user)
m.Push("Server exchange01.example.net is in a critical state.")
```

# Command Line Tool
A command line tool is provided under cmd/pushover. Build and install the command using:
```Shell
$ make install
```
Before using the command line tool, you must first set the following environment variables.
```Shell
$ export PUSHOVER_TOKEN="KzGDORePKggMaC0QOYAMyEEuZJnyUi"
$ export PUSHOVER_USER="e9e1495ec75826de5983cd1abc8031"
```
Then messages can be sent by piping output to the pushover command.
```Shell
$ echo "Server exchange01.example.net is in a critical state" | pushover
```
