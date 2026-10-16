Breaking changes
----------------

*   Slices and the ``[*]`` wildcard no longer coerce scalars and objects into arrays. (#96)

    Previously, ``$[*]`` applied to ``"abc"`` or ``5`` would find the value itself,
    and ``$[*]`` applied to ``{"a": 1}`` would find the whole object.
    This also caused ``$..[*]`` to return phantom nodes,
    such as the root object and a second copy of each string.

    Now, slices like ``[0:2]`` find nothing unless they are applied to an array,
    and ``[*]`` finds the member values of an object or the elements of an array
    and nothing from a scalar value.

    This change improves RFC 9535 compliance.

Fixed
-----

*   Fix ``..[*]`` omitting the member values of objects. (#96)
