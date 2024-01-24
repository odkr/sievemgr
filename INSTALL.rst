============
Installation
============

REQUIREMENTS
============

* A Unix-like operating system (e.g., \*BSD, illumos, Linux, or macOS).

* Python_ ≥ v3.9.

* The `Package Installer for Python`_ (pip)

* Optionally, dnspython_ (see EXTRAS_ below).


.. _dnspython: https://www.dnspython.org/

.. _`Package Installer for Python`: https://pypi.org/project/pip/

.. _Python: https://www.python.org/


DOWNLOAD
========

Download the most recent release:

.. code:: bash

    curl -O https://codeberg.org/odkr/sievemgr/releases/download/v0.5.1/sievemgr-0.5.1.tgz

Optionally, verify that the tarball has not been tampered with:

.. code:: bash

    curl -O https://codeberg.org/odkr/sievemgr/releases/download/v0.5.1/sievemgr-0.5.1.tgz.asc
    gpg --recv-key 8975B184615BC48CFA4549056B06A2E03BE31BE9
    gpg --verify sievemgr-0.5.1.tgz.asc

Unpack the tarball:

.. code:: bash

    tar -xzf sievemgr-0.5.1.tgz

Go to the top-level directory of the repository:

.. code:: bash

    cd sievemgr-0.5.1

.. caution::
    The following commands require that the repository is your working directory.


INSTALLATION
============

Home directory
--------------

.. code:: bash

    make user-install

The manual pages are copied to :file:`~/.local/share/man` by default.

Consult the manual of your system's :command:`man` or your shell
on how to add that directory to your :envvar:`MANPATH`.

.. tip::
    Copy the manual pages to `$mandir`:

    .. code:: bash

        make mandir="$mandir" user-install


System-wide
-----------

Create a virtual environment in :file:`/opt/odkr/sievemgr`
and install SieveManager to that directory:

.. code:: bash

    make venv-install

Symlink :command:`sievemgr` into a directory in the system's :envvar:`PATH`:

.. code:: bash

    ln -s /opt/odkr/sievemgr/bin/sievemgr /usr/local/bin

.. tip::
    Install SieveManager to `$installdir` and
    copy the manual pages to `$mandir`:

    .. code:: bash

        make installdir="$installdir" mandir="$mandir" venv-install


Virtual environment
-------------------

Install SieveManager to an existing virtual environment at `$venvdir`:

.. code:: bash

    make installdir="$venvdir" venv-install


Manual
------

SieveManager is a simple Python script.

It can also be installed by being copied into
a directory that is in your :envvar:`PATH`.

For example:

.. code:: bash

    install sievemgr.py ~/.local/bin/sievemgr


DE-INSTALLATION
===============

.. code:: bash

    make uninstall


EXTRAS
======

Resolving DNS SRV records requires dnspython_,
which can be installed with::

    python3 -mpip install dnspython

.. note::
   ManageSieve servers typically do *not* have DNS SRV records.
   SieveManager works well without dnspython.


PACKAGING
=========

See :doc:`packaging` for an example how to
package SieveManager for Debian_.

.. _Debian: https://www.debian.org
