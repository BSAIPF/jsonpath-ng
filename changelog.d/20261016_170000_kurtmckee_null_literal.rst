Fixed
-----

*   Allow filters to compare against JSON ``null`` values (``[?(@.v == null)]``). (#49)

    An unquoted ``null`` no longer matches the string ``"null"``.
    To compare a value to the word ``"null"``, quote it (``[?(@.v == 'null')]``).
    ``null`` also continues to work as a field name, as in ``$.null``.

    ``!= null`` now also matches members that are missing,
    and ``<``, ``<=``, ``>``, and ``>=`` no longer raise a ``TypeError``
    when compared with ``null``.
