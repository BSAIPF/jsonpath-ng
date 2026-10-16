Fixed
-----

*   Allow ``true`` and ``false`` to be used as field names in the extended parser.

    For example: ``$.true`` and ``$[?@.false == false]``.

    These previously raised a ``JsonPathParserError``.

    Unquoted ``true`` and ``false`` on the right-hand side of a filter comparison
    continue to be boolean literals.

*   Stop treating booleans as numbers in filter comparisons.

    Previously ``[?@.v == true]`` also matched ``1`` and ``[?@.v == 1]`` also matched ``true``.
    A boolean is now never equal to a number, which follows RFC 9535.
