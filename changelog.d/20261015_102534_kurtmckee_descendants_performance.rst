Fixed
-----

*   Fix ``RecursionError`` when paths using ``..`` are applied to deeply nested data.

    It is still possible to encounter ``RecursionError``.
    For example, very long JSONPath expressions can still raise ``RecursionError``.

    Note that cyclic data structures can trigger indefinite execution,
    as can updating data with a value that the path can match again.
    Cyclic data structures are impossible to encounter in JSON
    and can only be constructed programmatically in Python.

*   Make ``Descendants.find()`` runtimes scale linearly with the depth of the data.
