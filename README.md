This is an [Ansible](http://www.ansible.com/home) role for installing
[InfluxDB](http://influxdb.com/).

# What it Does

## Software

Installs InfluxDB from the .deb which provides influxdb command.

## Configuration & Logging

Creates the files:

* `/opt/influxdb/current/config.toml` -- configuration file for InfluxDB
* `/etc/logstash/conf.d/influxdb.conf` -- input file for logstash
* `/var/log/influxdb` -- log directory (FIXME: though it doesn't seem to want to log there?)

## Services

Leaves a service `influxdb` which camps out several ports.

# Usage

Use the role in a playbook like this:

```yaml
- hosts: all
  roles:
    - influxdb
```

Set the `influxdb_use_logstash` to `false` to skip the logstash
configuration.

## Variables

The following variables are exposed for configuration...

