Fixed
-----

*   Fix a parse error when a filter follows ``..``, as in ``$..[?@.key]``. (#46)

    The path now parses and selects every matching array element or object member value
    at any depth, as required by RFC 9535.
