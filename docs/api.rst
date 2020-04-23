============
API
============

The API endpoints are for our business customers to migrate and store generated content,
they are not for serving the content for a website nor are they suitable for on-demand
access. Thus the access limits are strict, we recommend our clients to maintain their own
backend and database, access the monok api periodically to refresh their database with
newly generated content.

API-Key
------------

The API is only accessible by our paying customers through a unique API key provided to
each user. The API key is a token that a client provides when making API calls, the key is
added in the request header as such:

Install the package with pip::

    $ pip install read-the-docs-template

Get a Feed
------------
Acces the generated articles of a feed as a JSON

Get an Article
------------
This endpoint will return the entire article and all its meta-data as a JSON.