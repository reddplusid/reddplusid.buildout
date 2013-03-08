======
README
======

Ubuntu/Debian Dependencies

 * python-devel
 * git
 * libreoffice
 * docsplit
 * tesseract-ocr
 * libxml2-dev
 * libxslt-dev
 * ruby
 * rubygems
 * poppler-utils
 * graphicsmagick
 * pkg-config
 * libpcre3-dev

Install docsplit with rubygems:

gem install --version '0.6.4' docsplit 

Development buildout
--------------------

This buildout is the default buildout.cfg

It provides a basic setup, checkouts out development versions
of packages in dev. It only requires one service to startup.

::
    python2.6 bootstrap.py
    bin/buildout -vv 

    bin/instance fg (to start service foreground and see all debug output)

Deployment buildout
-------------------

Deployment buildout pulls in all dependencies and configures, the
setup for a production machine with caching proxy, zeo database, 
and worker service for background document preview conversions
and effective user set as usually root user is deploying the setup.

First time install.

::

    python2.6 bootstrap.py
    bin/buildout -vv -c deployment.cfg

Startup ::

    bin/zeo start
    bin/instance start
    bin/worker start
    bin/varnish

In future to update the deployment setup::

    git pull
    bin/buildout -vv -c deployment.cfg
    bin/zeo stop; bin/zeo start;
    bin/instance stop; bin/instance start;
    bin/worker stop; bin/worker start;
    bin/varnish

