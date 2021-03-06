# The CoLoMoTo Docker

[![](https://images.microbadger.com/badges/image/colomoto/colomoto-docker.svg)](http://microbadger.com/images/colomoto/colomoto-docker "Get your own image badge on microbadger.com")
[![](https://images.microbadger.com/badges/version/colomoto/colomoto-docker.svg)](https://microbadger.com/images/colomoto/colomoto-docker "Get your own version badge on microbadger.com")
[![PyPI version](https://badge.fury.io/py/colomoto-docker.svg)](https://badge.fury.io/py/colomoto-docker)
[![Binder](https://mybinder.org/badge.svg)](https://mybinder.org/v2/gh/colomoto/colomoto-docker/mybinder)

## Quick usage guide

You need [Docker](http://docker.com).
We support GNU/Linux, macOS, and Windows.

### Using the colomoto-docker script

You need [Python](http://python.org).

The script can be installed and upgraded by executing the following command
(you may have to use `pip3` instead of `pip` depending on your configuration):

    pip install -U colomoto-docker


The CoLoMoTo notebook can then be started by executing in a terminal (if using Docker Toolbox, in a Docker Terminal):

    colomoto-docker

The container can be stopped by pressing <kbd>Ctrl</kbd>+<kbd>C</kbd> keys.

By default, the script will fetch the most recent [colomoto/colomoto-docker tag](https://hub.docker.com/r/colomoto/colomoto-docker/tags/). A specific tag can be specified using the `-V` option. For example:

    colomoto-docker -V 2018-05-29

**Warning**: by default, the files within the Docker container are isolated from the running host computer, therefore *files are deleted after stopping the container*.
To have access to the files of your current directory you should use the `--bind` option:

    colomoto-docker --bind .
      
See

    colomoto-docker --help

for other options.


### Manual invocation

First fetch the image with

    docker pull colomoto/colomoto-docker:TAG

where `TAG` is the version of the image, among [colomoto/colomoto-docker tags](https://hub.docker.com/r/colomoto/colomoto-docker/tags/).

The image can be ran using

    docker run -it --rm -p 8888:8888 colomoto/colomoto-docker:TAG

then, open your browser and go to http://localhost:8888 for the Jupyter notebook web interface
(note: when using Docker Toolbox, replace localhost with the result of
`docker-machine ip default` command).


## Embedded software

Besides the [Jupyter notebook](http://jupyter.org), the docker image provides
access to the following softwares:

| Software tool | Homepage | Description | Jupyter interface |
| --- | --- | --- | --- |
| CellCollective | https://cellcollective.org | Model repository and knowledge base | Python module [`cellcollective`](https://github.com/colomoto/colomoto_jupyter) |
| GINsim | http://ginsim.org | Boolean and multi-valued network modelling | Python module [`ginsim`](https://github.com/GINsim/GINsim-python) |
| bioLQM | http://colomoto.org/biolqm/ | Logical Qualitative Modelling toolkit | Python module [`biolqm`](https://github.com/GINsim/GINsim-python) |
| NuSMV | http://nusmv.fbk.eu | Symbolic model-checker | Python module [`nusmv`](https://github.com/colomoto/colomoto_jupyter)
| Pint | https://loicpauleve.name/pint | Static analyzer for dynamics of Automata Networks | Python module [`pypint`](https://github.com/pauleve/pint)  |
| MaBoSS | http://maboss.curie.fr | Markovian Boolean Stochastic Simulator | Python module [`maboss`](https://github.com/colomoto/pyMaBoSS) |


## Tagging policy and re-executability considerations

Docker images are timestamped with tags of the form YYYY-MM-DD after each tool addition or upgrade.

In order to guarantee the re-executability of your notebook, we recommend to use these tagged images instead of the non-persistent `next` tag.

## Contribute

See [CONTRIBUTING.md](CONTRIBUTING.md).

