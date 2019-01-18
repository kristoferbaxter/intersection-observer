# Intersection Observer and Iframes

The AMP codebase relies on operating within iframes and base documents in equivalent manners (AMP viewers from Search engines tend to iframe AMP documents).

As a result, AMP is unable to use Intersection Observer to monitor the intersection of a item with the viewport with a rootMargin. This works as expected with base documents, but not iframes.

The reason is listed here: https://w3c.github.io/IntersectionObserver/#dom-intersectionobserver-rootmargin.

If this restriction was lifted, then AMP and other similar iframed content could use Intersection Observer instead of monitoring scroll position.

## How to use this Repo

1. Clone the Github Repository
2. Use a simple http server to host the root directory (`simplehttp2server` or similar).
3. Visit `content.html`, and notice the intersection boundary starts before the element enters the viewport.
4. Visit `iframer.html`, and notice the same does not occur. (iframes content.html)