# Logstash buildpack

This buildpack manage the installation of
[Logstash](https://www.elastic.co/guide/en/logstash/current/getting-started-with-logstash.html).

It has been designed to work on [Scalingo](https://scalingo.com/), but it should
work on any other platform that support buildpacks.

Default version: 9.2.4

Please follow our [documentation
page](https://doc.scalingo.com/platform/getting-started/getting-started-with-elk#logstash)
about the ELK stack to use this buildpack.

## Configuration

To configure the buildpack you can use the following environment variables:

* `LOGSTASH_VERSION`: Define which version of Logstash will be installed
* `LOGSTASH_PLUGINS`: Comma separated list of plugins which needs to be
  installed. [List of plugins](https://github.com/logstash-plugins)
