# Logstash buildpack

This buildpack manage the installation of
[logstash](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html).

It has been designed to work on [Scalingo](http://scalingo.com/), but it should
work on any other platform that support buildpacks.

## Prerequisites

This buildpack assume that java is already installed with the correct version.

## Configuration

To configure the buildpack you can use the following environment variables:

* `LOGSTASH_VERSION`: Define which version of logstash will be installed
  (defaults to: 5.5.0)
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

