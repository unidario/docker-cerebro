## Description

Docker image to run cerebro [Elasticsearch 6.0.0](https://www.elastic.co/products/elasticsearch) web admin tool that replaces [Kopf](https://github.com/lmenezes/elasticsearch-kopf).

Cerebro project: [https://github.com/lmenezes/cerebro](https://github.com/lmenezes/cerebro)

This Docker image is built and available in Docker hub [unidario/cerebro:latest](https://hub.docker.com/r/unidario/cerebro/)

## Docker Tags

`unidario/cerebro` provides only one cerebro version at the moment:

- `latest` (default): Latest version of Cerebro.
- `0.7.2`: Cerebro 0.7.2 (Elasticsearch 6.0.0 supported)

## Usage

To run the image:
`docker run -d -p 9000:9000 --name cerebro unidario/cerebro:latest`

Then you can access the web console in this URL: [http://$DOCKERHOST:9000](http://[localhost:9000)

You can mount volumes for the configuration folder and / the logs, for example:

`docker run -d -p 9000:9000 --name cerebro -v /mount_folder/logs:/opt/cerebro/logs -v /mount_folder/conf:/opt/cerebro/conf unidario/cerebro:latest`

Where `/mount_folder` is a folder in the Docker host to contain the data. If mounted, the volume `/opt/cerebro/conf` must contain a valid configuration.

## Docker-compose example

A docker-compose project is available in the [GitHub] project to run cerebro and a cluster 2 nodes with Elasticsearch 6.0.0.
To run it:
`docker-compose up -d`

If you were running a previous version of the project and want to force a build, run first:
`docker-compose build`

Then you can access the web console in this URL: [http://$DOCKERHOST:9000](http://[localhost:9000) and connect to the Elasticsearch cluster using the URL `http://elasticsearch:9200` or `http://elasticsearch2:9200` in the hosts input field, the user and password not needed.

## Disclaimer

This repository is build using the code of [yannert/docker-cerebro](https://github.com/yannart/docker-cerebro).
It was created because [yannert/docker-cerebro](https://github.com/yannart/docker-cerebro) does not seem to be maintained anymore and there was a need to have Elasticsearch 6.0.0 support.
