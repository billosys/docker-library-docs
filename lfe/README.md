# Supported tags and respective `Dockerfile` links

- [`latest`, `0.10.0` (*Dockerfile*)](https://github.com/lfe/lfe/blob/0.10.0/Dockerfile)

For more information about this image and its history, please see the [relevant
manifest file
(`library/lfe`)](https://github.com/docker-library/official-images/blob/master/library/lfe)
in the [`docker-library/official-images` GitHub
repo](https://github.com/docker-library/official-images).

# What is LFE?

LFE (Lisp Flavored Erlang) is a functional, concurrent, general-purpose
programming language and Lisp dialect built on top of Core Erlang and the
Erlang Virtual Machine (BEAM). LFE builds on top of Erlang in order to provide
a Lisp syntax for writing distributed, fault-tolerant, soft real-time, non-stop
applications. LFE also extends Erlang to support meta-programming with Lisp
macros and an improved developer experience with a feature-rich REPL.

> [wikipedia.org/wiki/LFE](http://en.wikipedia.org/wiki/LFE_%28programming_language%29)

![logo](https://raw.githubusercontent.com/docker-library/docs/master/lfe/logo.png)

# How to use this image

## Create a `Dockerfile` in your LFE project

    FROM lfe:0.10.0
    COPY . /usr/src/myapp
    WORKDIR /usr/src/myapp
    CMD [ "lfescript", "./your-lfe-daemon-or-script" ]

You can then build and run the Docker image:

    docker build -t my-lfe-app
    docker run -it --rm --name my-running-app my-lfe-app

## Run a single LFE script

For many simple, single file projects, you may find it inconvenient to write a
complete `Dockerfile`. In such cases, you can run an LFE script by using the
LFE Docker image directly:

    docker run -it --rm --name my-running-script -v "$(pwd)":/usr/src/myapp \
      -w /usr/src/myapp lfe:0.10 lfescript your-lfe-daemon-or-script

# License

View [license information](https://github.com/lfe/lfe/blob/master/LICENSE)
for the software contained in this image.

# User Feedback

## Issues

If you have any problems with or questions about this image, please contact us
 through a [GitHub issue](https://github.com/rvirding/lfe/issues).

You can also reach many of the official image maintainers via the
`#docker-library` IRC channel on [Freenode](https://freenode.net).

## Contributing

You are invited to contribute new features, fixes, or updates, large or small;
we are always thrilled to receive pull requests, and do our best to process them
as fast as we can.

Before you start to code, we recommend discussing your plans
through a [GitHub issue](https://github.com/rvirding/lfe/issues), especially
for more ambitious contributions. This gives other contributors a chance to
point you in the right direction, give you feedback on your design, and help
you find out if someone else is working on the same thing.
