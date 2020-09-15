# Getting started
```
curl lama.sh | sh
```

# Introduction
![lama.sh](docs/lama.svg)

lama is a simple HTTP server that serves files, directories and verbosely logs requests.
This project has two main qualities:
1. **Easy to use:** lama allows one to start a web server on any Linux/MacOSX using 25 characters, with no requirements (not even libc).
2. **Trustworthy:** lama's code and download script are as simple as they can be, thus can be inspected and verified. We have a very shallow
   dependency tree (just two dependencies other than the Go standard library).

## Configuration
`server` sports a few command-line flags which configure its behaviour. To pass those flags use

```shell
$ curl lama.sh | sh -s -- <flags>
```

For example to print the list of available flags

```shell
$ curl lama.sh | sh -s -- --help
Usage of lama:
  -d, --directory string   the directory to serve (default ".")
  -N, --dont-dump          be less verbose and don't dump requests
  -D, --dont-serve         don't serve any directy (ignores --directory)
  -l, --localhost          serve on localhost only
  -p, --port string        port to serve on, respects LAMA_PORT envvar (default "8080")
  -v, --version            prints the version
```

Some flags can be set as environment variables, like so:

```shell
curl lama.sh | LAMA_PORT=8888 sh
```

# Run the Server

```shell
git clone https://github.com/csweichel/lama && cd lama
```

## with go

```shell
go run main.go
```

## with binary 

```shell
curl https://github.com/csweichel/lama/releases/download/v0.3.0/lama_0.3.0_Linux_x86_64 -o server
chmod +x server
./server
```

## with Docker

```shell
docker build -t lama:latest .
docker run --rm -p 8080:8080 lama:latest
```

lama.sh is now located under http://localhost:8080/docs/

to start lama.sh with you selfhosted server, just replace the url

```shell
curl  http://localhost:8080/docs/ | sh
```

# How to contribute
All contributions/PR/issue/beer are welcome ❤️.

It's easiest to develop _lama_ using Gitpod, a free one-click online IDE (who I happen to be working on):

[![Open in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io#github.com/32leaves/lama)

# Credits

Logo based on work from [Vectors by Vecteezy](https://www.vecteezy.com).