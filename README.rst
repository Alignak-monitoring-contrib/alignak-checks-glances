Alignak checks package for Glances
==================================

Checks pack for monitoring hosts with Glances (tests repository)


Installation
----------------------------------------

The pack files are to be copied in the monitoring objects configuration directory. The most suitable location is the *arbiter_cfg/objects/packs/* directory in the main alignak configuration directory.

**Note**: The main Alignak configuration directory is usually */usr/local/etc/alignak* but it may depend upon your system and/or your installation.

From PyPI
~~~~~~~~~~~~~~~~~~~~~~~
To install the package from PyPI:

   `pip install alignak_checks_glances`

From source files
~~~~~~~~~~~~~~~~~~~~~~~
To install the package from the source files:

   git clone https://github.com/Alignak-monitoring-contrib/alignak-checks-glances
   cd alignak-checks-glances
   mkdir /usr/local/etc/alignak/arbiter_cfg/objects/packs/alignak_checks_glances
   cp -R alignak_checks_glances/* /usr/local/etc/alignak/arbiter_cfg/objects/packs/alignak_checks_glances

Documentation
----------------------------------------

To be completed

Packaging
----------------------------------------

Design and principles
~~~~~~~~~~~~~~~~~~~~~~~

Each pack aims to provide all necessary elements in the Alignak configuration to monitor hosts and/or services.
Each pack include the check command definitions, services templates, hosts templates, ...
It is even possible to include the monitoring plugins that will be run by Alignak to check an host/service.

Usually, the packs are only made of configuration files using the most common monitoring plugins available from the Nagios community.

The pack files are to be made available in the monitoring objects configuration directory and provide configuration utilities for the end-user:

 - hosts templates: the host "use" the pack features
 - services templates: the service "use" the pack features
 - ...

The proposed structure to build a pack:

 - all the checks packs are named as `alignak_checks_PACK`
 - the `PACK` repository is named as `alignak-checks-PACK`*
 - the `PACK` repository includes the following files:

   * README.rst
   * LICENCE (optional)
   * AUTHORS (optional)
   * MANIFEST.in
   * setup.py

 - the `PACK` repository includes an `alignak_checks_PACK` directory containing the pack files
 - the files in `alignak_checks_PACK` directory will be copied to the Alignak configuration
 - the files in `alignak_checks_PACK/plugins` directory will be copied to the Alignak libexec directory



Building
~~~~~~~~~~~~~~~~~~~~~~~

To build the package:

   - update the `pack/__init.py__` and `setup.py` files with all the package information

      * `setup.py` should not be modified for most of the packs ... if necessary, do it with much care!
      * `pack/__init.py__` contains all the metadata necessary for the pack

   - update the `MANIFEST.in` with the package name

   - run `setup.py register` to register the package near PyPI
   - run `setup.py sdist` to build the package
   - run `setup.py install --dry-run` to test the package installation

   - run `setup.py sdist upload` to upload the package to `PyPI repository <https://pypi.python.org/pypi>`_

Bugs, issues and contributing
----------------------------------------

Contributions to this project are welcome and encouraged ... issues in the project repository are the common way to raise an information.

License
----------------------------------------

Alignak Pack Glances is available under the `GPL version 3 <http://opensource.org/licenses/GPL-3.0>`_.

