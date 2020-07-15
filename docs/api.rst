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
If the feed plugin you're runnig is "article generation", you can access the generated articles of a feed as a JSON with this request,
the same applies for scraped articles with the funnel plugin or clusters of articles with the cluster plugin.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/feed/?q=en&f=20&sort=date&c=business


===============   ===================================================
 Param                       Description                        
===============   ===================================================
q	          The Id of the feed (example:‘myPoliticsNews’)            
f (optional)      The offset (f=0 return the first 10 articles, f=35 
	          returns 10 articles after the first 35 articles), default is 0         
c (optional)      A filter of comma-separated category
                  names. (example: ‘business,politics’),
                  default is all categories.
sort (optional)   The type of sort you wish the list of generated content 
                  to have, either ‘popularity’ for most popular first or ‘date’ for
		  latest articles first, default is popularity.
===============   ===================================================


Get an Article
------------
This endpoint will return the entire article and all its meta-data as a JSON.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/puff/band-lady-a-files-legal-action-against-blues-singer-anita-lady-a-white

===============   ===================================================
 URL Endpoint       https://www.monok.com/api/v1/puff/​[article Id]                        
===============   ===================================================
