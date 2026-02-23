# Logstash buildpack

This buildpack manage the installation of
[Logstash](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html).

It has been designed to work on [Scalingo](https://scalingo.com/), but it should
work on any other platform that support buildpacks.

Default version: 6.8.21

Please follow our [documentation
page](https://doc.scalingo.com/platform/getting-started/getting-started-with-elk#logstash)
about the ELK stack to use this buildpack.

## Prerequisites

This buildpack assume that java is already installed with the correct version.

## Configuration

To configure the buildpack you can use the following environment variables:

* `LOGSTASH_VERSION`: Define which version of Logstash will be installed
* `LOGSTASH_PLUGINS`: Comma separated list of plugins which needs to be
  installed. [List of plugins](https://github.com/logstash-plugins)

## Installation path

The elasticsearch binary will be available at
`logstash/logstash-$LOGSTASH_VERSION/bin/logstash`.

You can also use the wrapper present in this buildpack which will do two
things:
* Use the `LOGSTASH_VERSION` environment variable to generate the path
* Split the `ELASTICSEARCH_URL` variable into three:
  * `ELASTICSEARCH_HOST`
  * `ELASTICSEARCH_USER`
  * `ELASTICSEARCH_PASSWORD`

