# What is LFE?

LFE (Lisp Flavored Erlang) is a functional, concurrent, general-purpose
programming language and Lisp dialect built on top of Core Erlang and the
Erlang Virtual Machine (BEAM). LFE builds on top of Erlang in order to provide
a Lisp syntax for writing distributed, fault-tolerant, soft real-time, non-stop
applications. LFE also extends Erlang to support meta-programming with Lisp
macros and an improved developer experience with a feature-rich REPL

> [wikipedia.org/wiki/LFE](https://en.wikipedia.org/wiki/LFE_(programming_language))

%%LOGO%%

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
