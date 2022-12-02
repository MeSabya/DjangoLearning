## Dynamic Routing with Path Converters

The following are the path converters available for us to use.

str: Matches any non-empty string, excluding the path separator, '/'.

int: Matches zero or any positive integer.

slug: Matches any slug string consisting of ASCII letters or numbers, plus the hyphen and underscore characters. For example, building-your-1st-django-site.

uuid - Matches a formatted UUID.

path - Matches any non-empty string, including the path separator, '/'. This allows us to match against a complete URL path rather than a segment of a URL path, as with str.
