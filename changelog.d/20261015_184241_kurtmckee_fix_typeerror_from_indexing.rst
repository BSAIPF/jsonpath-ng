Breaking changes
----------------

*   When applying an index to a string, nothing will be returned.

    Previously, an index applied to a string would "find" individual characters.
    For example, ``$[0]`` applied to ``"abc"`` would find ``"a"``.

    This change improves RFC 9535 compliance.

Fixed
-----

*   Fix ``TypeError`` when an index like ``[0]`` is applied to a scalar value.

    These values now match nothing, as RFC 9535 requires.
