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

Request articles by Feed ID (businessfeed1) ::

    $ curl -XGET -i 'https://www.monok.com/api/v1/feed?q=businessfeed1'
    -H "Content-Type: application/json"
    -H "x-api-token: [ API KEY ]"

Get a Feed
------------
Acces the generated articles of a feed as a JSON

**Type:** GET-Request
**Example:** http://www.monok.com/api/v1/feed/?q=en&f=20&sort=date&c=business

	
+------------+------------+
| Param      |Description |
+============+============+
| q | column 2   |
+------------+------------+
| f | column 2   |
+------------+------------+
| c (optional) | column 2   |
+------------+------------+
| body row 1 | column 2   |
+------------+------------+

Get an Article
------------
This endpoint will return the entire article and all its meta-data as a JSON.
