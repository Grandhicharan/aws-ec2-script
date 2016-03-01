===================================
JSON script to launch ec2 instances
===================================
**requires Python and aws-cli**

--------------------------------
Step 1: Download aws-cli package
--------------------------------

.. image:: https://travis-ci.org/aws/aws-cli.png?branch=develop
   :target: https://travis-ci.org/aws/aws-cli
   :alt: Build Status


.. image:: https://coveralls.io/repos/aws/aws-cli/badge.png
  :target: https://coveralls.io/r/aws/aws-cli


This package provides a unified command line interface to Amazon Web Services.

The aws-cli package works on Python versions:

* 2.6.5 and greater
* 2.7.x and greater
* 3.3.x and greater
* 3.4.x and greater
* 3.5.x and greater


-----------------------
Step 2: Install aws-cli
-----------------------

The easiest way to install aws-cli is to use `pip`_::

    $ pip install awscli

or, if you are not installing in a ``virtualenv``::

    $ sudo pip install awscli

If you have the aws-cli installed and want to upgrade to the latest version
you can run::

    $ pip install --upgrade awscli

This will install the aws-cli package as well as all dependencies.  You can
also just `download the tarball`_.  Once you have the
awscli directory structure on your workstation, you can just run::

    $ cd <path_to_awscli>
    $ python setup.py install

-----------------------
Step 3: Run the script
-----------------------

MUST EDIT aws-ec2-script-template.json with details specific to your AWS account and configuration. Be sure to remove all comments from JSON file before running. 

From the local directory where your aws-ec2-script-template.json file is stored, execute the following::

    $ aws ec2 request-spot-instances --spot-price "0.02" --launch-specification file://ec2-run-script-template.json

**The command above will request a spot instance with price set at $0.02/hr.**

"*To launch a regular instance rather than 'spot instance', execute the following*"::

    $ aws ec2 run-instances --launch-specification file://ec2-run-script-template.json

----------------------------------------------
Additional configuration options and commands
----------------------------------------------
Please see:
**https://docs.aws.amazon.com/cli/latest/reference/ec2/**
