gaclient is a small library that implements an easy to use API
for consuming Google Analytics APIs.

Assuming you have already obtained a **refresh token** from the
user, retrieving metrics is as simple as::

    >>> import gaclient
    >>> session = gaclient.build_session(CLIENT_ID, CLIENT_SECRET,
        {'refresh_token': REFRESH_TOKEN})
    >>> it = gaclient.Cursor(session, PROFILE_ID,
        '2012-01-01', '2012-01-01', ['visits'], ['date'])
    >>> list(it)
    [{'visits': 12345, 'date': datetime.date(2012, 1, 1)}]

For complete step-by-step guide on how to obtain a user's
consent please refer to the
`User Guide <http://www.python-gaclient.org/0.3/guide.html>`_.


Features
--------

    * Transparently queries Google Analytics for additional results
      if any are available;
    * Selecting any valid combination of dimensions and metrics;
    * Server-side filtering;
    * Server-side sorting;
    * Data is returned in native Python types, parsed and
      ready for you consumption;
    * Support for Python 3.


For more information check out the `gaclient documentation <http://www.python-gaclient.org/latest>`_.
