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

Install docsplit with rubygems:

gem install --version '0.6.4' docsplit 

Deployment buildout
-------------------

::

    python2.6 bootstrap.py
    bin/buildout -vv -c deployment.cfg

Startup ::

    bin/zeo start
    bin/instance start
    bin/varnish


