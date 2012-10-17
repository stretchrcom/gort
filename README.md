Professor - go test -r
===================================

Professor is a go program that installs test dependencies and/or runs tests, recursively, starting from the working directory.

Professor allows you to run all the tests in a multi-package directory structure with one command. As it works, it will display a '.' for each successful test and print out any failures. At the end of the run, professor will give you a summary of tests run, tests succeeded and tests failed.

Professor pairs wonderfully with our testing framework, [Testify](http://github.com/stretchrcom/testify).

For an introduction to writing test code in Go, see the [Go Testing Documentation](http://golang.org/doc/code.html#Testing).

Installation
============

Before installation, please ensure that your GOPATH is [set properly](http://golang.org/doc/code.html#tmp_2).

To install Professor, use `go get`:

    go get github.com/stretchrcom/professor

This will place Professor in $GOPATH/src/professor. Navigate to this directory, and run:

	go install
	
`go install` should install Professor to $GOPATH/bin. It may attempt to install to $GOBIN instead, however. If this happens, you can manually copy the `professor` file to $GOPATH/bin.

Complete! You are now ready to use Professor!


Usage
=====

When using Professor, it is important that the code your are testing resides within a directory that is in your GOPATH.

Using Professor is easy. Just execute the command:

	professor test

Professor will recurse the directory structure and run `go test -i` & `go test` for each directory that contains tests.

If there is a directory that contains tests you don't wish to run, simply exclude it:

	professor exclude testify
	
Now, when you run tests, the directory "testify" will not be recursed, and no tests inside it or its subdirectories will be run.

Professor has some more commands that are not listed here. To see them all, simply run `professor` with no arguments


------

Contributing
============

Please feel free to submit issues, fork the repository and send pull requests!

When submitting an issue, we ask that you please include steps to reproduce the issue so we can see it on our end also!


Licence
=======
Copyright (c) 2012 Mat Ryer and Tyler Bunnell

Please consider promoting this project if you find it useful.

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.