============
Installation
============

REQUIREMENTS
============

* A Unix-like operating system (e.g., \*BSD, illumos, Linux, or macOS).

* Python_ ≥ v3.9.

* Optionally, dnspython_ (see EXTRAS_ below).


.. _dnspython: https://www.dnspython.org/

.. _Python: https://www.python.org/


DOWNLOAD
========

Clone the repository:

.. code:: bash

    git clone https://codeberg.org/odkr/sievemgr.git


Go to the top-level directory of the repository:

.. code:: bash

    cd sievemgr

.. caution::
    The following instructions assume that the repository
    is your working directory.


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
    Copy the manual pages to `$directory`:

    .. code:: bash

        make mandir="$directory" user-install


Virtual environment
-------------------

Store the path to the virtual environment in `$venv`:

.. code:: bash

    venv=/opt/odkr/sievemgr

.. caution::
    The following instructions assume that `venv` is set
    to the top-level directory of the virtual environment.


Create the virtual environment:

.. code:: bash

    python3 -mvenv "$venv"


Activate the virtual environment:


.. code:: bash

    . "$venv/bin/activate"


Install SieveManager:

.. code:: bash

    make prefix="$venv" venv-install


Symlink :command:`sievemgr` and the manual pages into directories that
are in the system's :envvar:`PATH` and :envvar:`MANPATH` respectively:

.. code:: bash

    ln -s "$venv/bin/sievemgr" /usr/local/bin
    ln -s "$venv/share/man/man1/sievemgr.1" /usr/local/share/man/man1
    ln -s "$venv/share/man/man5/sieverc.5" /usr/local/share/man/man5


System-wide
-----------

Configure the installer:

.. code:: bash

    ./configure


Install SieveManager:

.. code:: bash

    make install

.. warning::

    Only try this if you know what you are doing.


Manual
------

SieveManager is but a Python script.

It can also be installed by being copied into
a directory that is in your :envvar:`PATH`.

For example:

.. code:: bash

    install sievemgr.py ~/.local/bin/sievemgr

.. note::

    The Python module is only by :command:`make` or :command:`pip`.


DE-INSTALLATION
===============

.. code:: bash

    make uninstall

.. note::
    SieveManager can only be uninstalled with :command:`make uninstall`
    if it was installed with :command:`make` or :command:`pip`.


EXTRAS
======

Resolving DNS SRV records requires dnspython_,
which can be installed with::

    pip install dnspython

.. note::
   ManageSieve servers typically do *not* have DNS SRV records.
   SieveManager works well without dnspython.

.. note::
    :command:`pip` may be called :command:`pip3` on your system.
