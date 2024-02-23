========
Security
========

Connections are secured with Transport Layer Security (TLS) by default,
and passwords are only stored in memory.


REPORTING
=========

If you have discovered a security issue, please write an encrypted email
to the :file:`@zoho.com` address listed in my `PGP key`_.


CAVEATS
=======

Checking whether a server's TLS certificate has been revoked requires
the non-standard Python module cryptography_.

Credentials are stored in memory so that they need not be entered again
in case of a referral. However, because page-locking is unfeasible in
Python, they may be swapped out to the disk.

.. _`PGP key`: https://keys.openpgp.org/vks/v1/by-fingerprint/8975B184615BC48CFA4549056B06A2E03BE31BE9

.. _cryptography: https://cryptography.io
