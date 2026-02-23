# Logstash buildpack

This buildpack manage the installation of
[Logstash](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html).

It has been designed to work on [Scalingo](https://scalingo.com/), but it should
work on any other platform that support buildpacks.

Please follow our [documentation
page](https://doc.scalingo.com/platform/getting-started/getting-started-with-elk#logstash)
about the ELK stack to use this buildpack.


## Configuration

To configure the buildpack you can use the following environment variables:

* `LOGSTASH_VERSION`\
  Allows to specify the version of Logstash to install
* `LOGSTASH_PLUGINS`\
  A comma separated list of plugin names to install.
  [List of plugins](https://github.com/logstash-plugins)

## Installation path

The elasticsearch binary is available at
`logstash/logstash-$LOGSTASH_VERSION/bin/logstash`.

You can also use the wrapper present in this buildpack which will do two
things:
* Use the `LOGSTASH_VERSION` environment variable to generate the path
* Split the `ELASTICSEARCH_URL` variable into three:
  * `ELASTICSEARCH_HOST`
  * `ELASTICSEARCH_USER`
  * `ELASTICSEARCH_PASSWORD`
