=====
sssss
=====

Static (version of) Shamir's Secret Sharing Scheme

|pypi| |travis| |coveralls|

.. |pypi| image:: https://badge.fury.io/py/sssss.svg
   :target: https://badge.fury.io/py/sssss
   :alt: PyPI version and link.

Package Installation and Usage
------------------------------
The package is available on PyPI::

    python -m pip install sssss

The library can be imported in the usual ways::

    import sssss
    from sssss import sssss

.. code-block:: python

    from sss import make_shares, reconstruct_secret

    secret = b'Correct. Horse. Battery. Staple.'
    shares = make_shares(secret, minimum=3, shares=6)

    print('Secret:', secret)
    print('Shares:')
    if shares:
        for share in shares:
            print('', '', share)

    print('Secret recovered from minimum subset of shares:',
          reconstruct_secret(shares[:3]))
    print('Secret recovered from a different subset of shares:',
          reconstruct_secret([shares[1], shares[3], shares[5]]))


Versioning
----------
Beginning with version 0.2.0, the version number format for this library and the changes to the library associated with version number increments conform with `Semantic Versioning 2.0.0 <https://semver.org/#semantic-versioning-200>`_.
