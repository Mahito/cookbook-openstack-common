# CHANGELOG for cookbook-openstack-common

This file is used to list changes made in each version of cookbook-openstack-common.

## 10.2.0
* Separate endpoints for vncserver_listen and vncserver_proxyclient_address
* Bump Chef gem to 11.16
* Fix openstack_command with correct arguments order
* Fix openstack_command with single argument type
* Make default using cinder v2 api
* Add OS_VOLUME_API_VERSION for openrc
* Removed the hardcoded PPA reference to "Precise"
* Added an optional automatic apt-get update for Debian based repos
* Add a new custom matcher render_config_file to test ini file content
* Add global rabbit ha flag

## 10.1.0
* Adding identity admin bind host endpoint to allow flexibility and consistency
* Fix logging.conf No section error
* Raise error for nil address returned from address_for

## 10.0.3
* Adding identity internal endpoint variables to support new endpoint usage in identity cookbook
* Add sensitive flag to openrc template resource

## 10.0.2
* Add database charset during create

## 10.0.1
* Add an option to allow configuring rabbitmq use_ssl

## 10.0.0
* Upgrading to Juno
* Upgrading berkshelf from 2.0.18 to 3.1.5

## 9.7.0
* Add new network_uuid cli library method for obtaining ID from various neutron resources
* fix fauxhai version for suse
* Allow custom logging attributes for loggers, formatters and handlers

## 9.6.1
* Add python_packages attribute for sqlite

## 9.6.0
* Add an option to store passwords in attributes instead of data bags. Deprecates the get_secret method and the development_mode.

## 9.5.2
* Adds new python_packages attributes for database client packages

## 9.5.1
* Add Trove endpoints, database and mq attributes

## 9.5.0
* Add new image_id cli library method for obtaining glance ID from image name

## 9.4.1
* Fix to allow database connection options for telemetry nosql

## 9.4.0
* Add durable_queues, auto_delete, and qpid topology version attributes

## 9.3.0
* Provide an option to specify the password when dev mode equals true

## 9.2.2
* Fixed openrc failure on role search

## 9.2.1
* Fix package action to allow updates

## 9.2.0
* Add recipe for openrc file (moved from compute cookbook)

## 9.1.2
* Make PKI tokens the new default

## 9.1.1
* Add new library method for making cli calls and one for getting uuids

## 9.1.0
* Added python-openstackclient support

## 9.0.2
* Allow address_for family default to be overridden

## 9.0.1
### Bug
* Fix the depends cookbook version issue in metadata.rb

## 9.0.0
* Upgrading to Icehouse

## 8.5.0
* Add get_secret library method which allows one to specify a secrets_data_bag in attributes.

## 8.4.2
* Adjust image service endpoint path from /v2 to /

## 8.4.1
* Fix a renaming openstack-metering issue, change `metering` to `telemetry` in db_uri function.

## 8.4.0
* Rename openstack-metering to openstack-telemetry

## 8.3.0
### Blueprint
* use-data-bag-for-qpid-password: have qpid use get_password method rather than
  using a password attribute

## 8.2.1
### Bug
* Add notification_topics attribute to network attributes

## 8.2.0
* Update and add new attributes for openstack-network cookbook

## 8.1.1
### Bug
* Adjust metering service endpoint path from /v1 to /

## 8.1.0
### Blueprint:
* yum-cookbook-v3-support: Update this cookbook to be compatible with version 3 of the yum cookbook.

## 8.0.1:
### Bug
* Add sleep to search_for function, so that node can be searched
* Add CentOS/RHEL support

## 8.0.0:
* Upgrading to Havana
* Upgrading gems
  * ChefSpec -> 3.0.2
  * Foodcritic -> 3.0.3
  * Berkshelf -> 2.0.10

## 0.4.7:
### Bug
* Change `#db_uri` to hand out UTF8 MySQL URIs; i.e. append '?charset=utf8' to mysql URIs

## 0.4.6:
### Bug
* Ensuring `#db_uri` returns a valid sqlite connection string
  * relative path example: 'path' = 'path/to/foo.db' -- will return sqlite:///foo.db
  * absolute path example: 'path' = '/path/to/foo.db' -- will return sqlite:////foo.db

## 0.4.5:
* Added `openstack-common::set_endpoints_by_interface` to enable using
  `bind_interface` with endpoints rather than hard-code the IP addresses in an
  Environment.

## 0.4.4:
* Add support for openstack-common::sysctl and managing sysctl settings via the
  node['openstack']['sysctl'] hash, written out to /etc/sysctl.d/60-openstack.conf

## 0.4.3:
* Corrected `#search_for` role and recipe queries.

## 0.4.2:
* Remove hardcoded localhost for mysql host specification.

## 0.4.1:
* Changed endpoint attributes to use http for default scheme.  this is inline with
  default settings in keystone.  fine for dev,  but should be ssl for prod.

## 0.4.0:
* Remove `#config_by_role` as it is no longer used and no longer suits our needs.

## 0.3.5:
* Reverted change made in 8311869e5b99fecefd567ce3f1ad1cbdf8d5c5c6.

## 0.3.4:
* Allow `#search_for` to always returns an array.

## 0.3.3:
* Incorrectly mocked search results, as a result `#search_for` was performing unnecessary
  actions to an array.

## 0.3.2:
* Fix network-api endpoint path

## 0.3.1:
* Corrected a faulty Chef search query with `#config_by_role`.  The search returns a
  Hash, not an array.

## 0.3.0:
* Added `#rabbit_servers` method, which returns a comma-delimited string of rabbit
  servers in the format of host:port.
* The `#memcached_servers` method no longer accepts an environment.
* Re-factored methods which search to a generic `#search_for`.
* Added `#address_for` method, which returns the IPv4 (default) address of the given
  interface.
* Added global mysql setting of port and db type, for use with wrapper cookbooks.
* Add default messaging attributes, for use with wrapper cookbooks.

## 0.2.6:
* Update Chef dependency to Chef 11.

## 0.2.5:
* Moved the default library to database, to better represent its duties.

## 0.2.4:
* Break out #memcached_servers into separate library.

## 0.2.3:
* Sort the results returned by #memcached_servers.

## 0.2.2:
* Provides a mechanism to override memcache_servers search logic through node attributes.

## 0.2.1:
* Adds a prettytable_to_array function for parsing OpenStack CLI output.

## 0.2.0:
* First release of cookbook-openstack-common that aligns with the Grizzly packaging.
* Adds OpenStack Network endpoints.

## 0.1.x:
* Folsom-based packaging.

## 0.0.1:
* Initial release of cookbook-openstack-common.

- - -
Check the [Markdown Syntax Guide](http://daringfireball.net/projects/markdown/syntax) for help with Markdown.

The [Github Flavored Markdown page](http://github.github.com/github-flavored-markdown/) describes the differences between markdown on github and standard markdown.
