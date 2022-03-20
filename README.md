# Local Clusters for Fun and Profit

This repo is meant to provide a local lab space and dev environment for working on spark workflows. For groups who utilize test-in-production workflows, this fills the gap left by a lack of dev or stage environment.

What this provides you is:

* A single master node with web UI to track your spark applications
* Three worker nodes to process data
* A Jupyter-lab node for experimenting with pySpark code

## Status

Clearly I just wrote this while on an airplane. This needs a lot of work. Namely:

* Testing
* Documentation
* A lot of robustness to support the variety of workflows that can be used with Spark

## Requirements

* Docker
* docker-compose
* make

## How to setup

Provided is a makefile which makes setup a single-step process:

~~~ bash
make build
~~~

## How to deploy

Now all you should have to do is 

~~~ bash
make start
~~~

And to stop the cluster:

~~~ bash
make stop
~~~


## Roadmap


As I continue to work on this, I'll be providing some additional code to simplify pandas UDFs and client-specific code. As you can imagine, the first blush isn't meant to be the final product, but we'll iterate towards the end.

## Contributions

Feel free to contribute to this repo directly or contact [Kevin at kwierman@gmail.com](kwierman@gmail.com).