johanek-redmine
---------------

[![Build Status](https://travis-ci.org/johanek/johanek-redmine.png)](http://travis-ci.org/johanek/johanek-redmine)

This module installs redmine, running behind apache and passenger, and backed by mysql

Tested on CentOS 6.3 and debian wheezy

Requirements
------------

Packages installed during process:
All OS: wget, tar, make, gcc
CentOS: mysql-devel, postgresql-devel, sqlite-devel, ImageMagick-devel
Debian: libmysql++-dev, libmysqlclient-dev, libmagickcore-dev, libmagickwand-dev

Gems installed during process: bundler

Modules required: johanek-apache, johanek-passenger, puppetlabs-mysql

Example Usage
-------------

To install the default version of redmine 

    class { 'apache': }
    class { 'passenger': }
    class { 'mysql': }
    class { 'mysql::server': }
    class { 'redmine': }

Parameters
----------

**version**

  Set to desired version. Default: 2.2.3

**download_url**

  Download URL for redmine tar.gz. If you want to install an unsupported version, this is required.
  Versions Supported: 2.2.1, 2.2.2, 2.2.3

**database_server**

  Database server to use. Default: 'localhost'
  If server is not on localhost, the database and user must be setup in advance.

**database_user**

  Database user. Default: 'redmine'

**database_password**

  Database user password. Default: 'redmine'

**production_database**

  Name of database to use for production environment. Default: 'redmine'

**development_database**

  Name of database to use for development environment. Default: 'redmind_development'

**smtp_server**

  SMTP server to use. Default: 'localhost'

**smtp_domain**

  Domain to send emails from. Default: $::domain
