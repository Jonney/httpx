<p align="center">
  <a href="https://www.python-httpx.org/"><img width="350" height="208" src="https://raw.githubusercontent.com/encode/httpx/master/docs/img/logo.jpg" alt='HTTPX'></a>
</p>

<p align="center"><strong>HTTPX</strong> <em>- A next-generation HTTP client for Python.</em></p>

<p align="center">
<a href="https://travis-ci.org/encode/httpx">
    <img src="https://travis-ci.org/encode/httpx.svg?branch=master" alt="Build Status">
</a>
<a href="https://codecov.io/gh/encode/httpx">
    <img src="https://codecov.io/gh/encode/httpx/branch/master/graph/badge.svg" alt="Coverage">
</a>
<a href="https://pypi.org/project/httpx/">
    <img src="https://badge.fury.io/py/httpx.svg" alt="Package version">
</a>
</p>

HTTPX is a fully featured HTTP client for Python 3, which provides sync and async APIs, and support for both HTTP/1.1 and HTTP/2.

**Note**: _HTTPX should be considered in beta. We believe we've got the public API to
a stable point now, but would strongly recommend pinning your dependencies to the `0.11.*`
release, so that you're able to properly review [API changes between package updates](https://github.com/encode/httpx/blob/master/CHANGELOG.md). A 1.0 release is expected to be issued sometime on or before April 2020._

---

Let's get started...

```python
>>> import httpx
>>> r = httpx.get('https://www.example.org/')
>>> r
<Response [200 OK]>
>>> r.status_code
200
>>> r.headers['content-type']
'text/html; charset=UTF-8'
>>> r.text
'<!doctype html>\n<html>\n<head>\n<title>Example Domain</title>...'
```

Or, using the async API...

_Use [IPython](https://ipython.readthedocs.io/en/stable/) or Python 3.8+ with `python -m asyncio` to try this code interactively._

```python
>>> import httpx
>>> async with httpx.AsyncClient() as client:
>>>     r = await client.get('https://www.example.org/')
>>> r
<Response [200 OK]>
```

## Features

HTTPX builds on the well-established usability of `requests`, and gives you:

* A broadly [requests-compatible API](https://www.python-httpx.org/compatibility/).
* Standard synchronous interface, but with [async support if you need it](https://www.python-httpx.org/async/).
* HTTP/1.1 [and HTTP/2 support](https://www.python-httpx.org/http2/).
* Ability to make requests directly to [WSGI applications](https://www.python-httpx.org/advanced/#calling-into-python-web-apps) or [ASGI applications](https://www.python-httpx.org/async/#calling-into-python-web-apps).
* Strict timeouts everywhere.
* Fully type annotated.
* 99% test coverage.

Plus all the standard features of `requests`...

* International Domains and URLs
* Keep-Alive & Connection Pooling
* Sessions with Cookie Persistence
* Browser-style SSL Verification
* Basic/Digest Authentication
* Elegant Key/Value Cookies
* Automatic Decompression
* Automatic Content Decoding
* Unicode Response Bodies
* Multipart File Uploads
* HTTP(S) Proxy Support
* Connection Timeouts
* Streaming Downloads
* .netrc Support
* Chunked Requests

## Installation

Install with pip:

```shell
$ pip install httpx
```

httpx requires Python 3.6+

## Documentation

Project documentation is available at [https://www.python-httpx.org/](https://www.python-httpx.org/).

For a run-through of all the basics, head over to the [QuickStart](https://www.python-httpx.org/quickstart/).

For more advanced topics, see the [Advanced Usage](https://www.python-httpx.org/advanced/) section, the [async support](https://www.python-httpx.org/async/) section, or the [HTTP/2](https://www.python-httpx.org/http2/) section.

The [Developer Interface](https://www.python-httpx.org/api/) provides a comprehensive API reference.

## Contribute

If you want to contribute with HTTPX check out the [Contributing Guide](https://www.python-httpx.org/contributing/) to learn how to start.

## Dependencies

The httpx project relies on these excellent libraries:

* `urllib3` - Sync client support.
* `h11` - HTTP/1.1 support.
* `h2` - HTTP/2 support.
* `certifi` - SSL certificates.
* `chardet` - Fallback auto-detection for response encoding.
* `hstspreload` - determines whether IDNA-encoded host should be only accessed via HTTPS.
* `idna` - Internationalized domain name support.
* `rfc3986` - URL parsing & normalization.
* `sniffio` - Async library autodetection.
* `brotlipy` - Decoding for "brotli" compressed responses. *(Optional)*

A huge amount of credit is due to `requests` for the API layout that
much of this work follows, as well as to `urllib3` for plenty of design
inspiration around the lower-level networking details.

<p align="center">&mdash; ⭐️ &mdash;</p>
<p align="center"><i>HTTPX is <a href="https://github.com/encode/httpx/blob/master/LICENSE.md">BSD licensed</a> code. Designed & built in Brighton, England.</i></p>
