# Security

Connections are secured with Transport Layer Security (TLS) by default,
and passwords are only stored in memory.

## CAVEATS

Credentials are stored in memory so that they need not be entered again
in case of a referral. However, because page-locking is unfeasible in
Python, they may be swapped out to the disk.

## VERSIONS

Only the most recent version of SieveManager receives security updates.

Subscribe to <https://codeberg.org/odkr/sievemgr/releases.rss>
to be notified about new releases.

## REPORTING

If you have discovered a security issue, please write an encrypted email
to the `@zoho.com` address listed in my [PGP
key](https://keys.openpgp.org/vks/v1/by-fingerprint/8975B184615BC48CFA4549056B06A2E03BE31BE9).
