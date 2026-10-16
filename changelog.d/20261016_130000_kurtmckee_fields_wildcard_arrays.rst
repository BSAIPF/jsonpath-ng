Fixed
-----

*   Fix ``*`` (used as a field) omitting the elements of arrays. (#11, #164)

    ``$.*`` and ``$..*`` now find array elements as well as object member values.

    ``update()`` and ``filter()`` now also act on array elements for these wildcards.
