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

News Article API
------------
Search for original news articles from publishers much like the Google News API or similar services. The articles are returned as a JSON.
This API Endpoint requires the News Article API Product.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/articles/?q=politics&f=20&sort=date&entities=true

===================   	================================================================================================
 Param                       Description                        
===================   	================================================================================================
q	          	An Article Search Query (example:‘entertainment’ or ‘organization:samsung‘), 
			learn more about the `Query Selector`_    
s (optional)      	The number of articles returned (s=1 return 1 article, s=20 
	          	returns 20 articles after the first 35 articles), default is 10.
f (optional)      	The offset (f=0 return the first 10 articles, f=35 
	          	returns 10 articles or your chosen s-parameter number of articles, 
			after the first 35 articles), default is 0 
c (optional)      	A filter of comma-separated category
                  	names. (example: ‘business,politics’),
                  	default is all categories.
sort (optional)   	The type of sort you wish the list of generated content 
                  	to have, either ‘popularity’ for most popular first or ‘date’ for
		  	latest articles first, default is popularity.
entities (optional)     A boolean (true/false) for returning named entities in the article. (example: ‘entities=true’),
                  	A list of all available named entities is available here. default is false.
===================   	================================================================================================

.. csv-table:: articles API
   :header: "Parameter", "Default", "Description"
   :widths: 15, 10, 30   
   
   "q", "", "An Article Search Query (example:‘entertainment’ or ‘organization:samsung‘), learn more about the `Query Selector`_"
   "s (optional)", 10, "The number of articles returned (s=1 return 1 article, s=20 returns 20 articles after the first 35 articles)"
   "f (optional)", 0, "The offset (f=0 return the first 10 articles, f=35 returns 10 articles or your chosen s-parameter number of articles, after the first 35 articles)"

Clustered News Stories API
------------
Search for clusters of original news articles, the returned stories will have multiple news article sources, 
all of which report on the same news event. The clustered articles are returned as a JSON.
This API Endpoint requires the Clustered News Stories API Product.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/clusters/?q=politics&f=20&sort=date&entities=true

===================   	================================================================================================
 Param                       Description                        
===================   	================================================================================================
q	          	An Article Search Query (example:‘entertainment’ or ‘organization:samsung‘),
			learn more about the `Query Selector`_  
s (optional)      	The number of articles returned (s=1 return 1 article, s=20 
	          	returns 20 articles after the first 35 articles), default is 10.
f (optional)      	The offset (f=0 return the first 10 articles, f=35 
	          	returns 10 articles or your chosen s-parameter number of articles, 
			after the first 35 articles), default is 0 
c (optional)      	A filter of comma-separated category
                  	names. (example: ‘business,politics’),
                  	default is all categories.
sort (optional)   	The type of sort you wish the list of generated content 
                  	to have, either ‘popularity’ for most popular first or ‘date’ for
		  	latest articles first, default is popularity.
entities (optional)     A boolean (true/false) for returning named entities in the article. (example: ‘entities=true’),
                  	A list of all available named entities if found in the `Query Selector`_ page. default is false.
===================   	================================================================================================


Feed API
------------
You may access the content of a feed as a JSON with this request,
Depending on what kind of plugin you've chosen for the feed, you'll get a clustered articles, scraped articles or generated articles.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/feed/?q=en&f=20&sort=date&c=business

If you're running an article generation feed but wish to see the scraped articles, you can force the endpoint to return the scraped articles instead by using the "product" param.

===================   	==================================================================
 Param                       Description                        
===================   	==================================================================
q	          	The Id of the feed (example:‘myPoliticsNews’)            
f (optional)      	The offset (f=0 return the first 10 articles, f=35 
	          	returns 10 articles after the first 35 articles), default is 0         
c (optional)      	A filter of comma-separated category
                  	names. (example: ‘business,politics’),
                  	default is all categories.
sort (optional)   	The type of sort you wish the list of generated content 
                  	to have, either ‘popularity’ for most popular first or ‘date’ for
		  	latest articles first, default is popularity.
product (optional)  	Chose what kind of content to return (generated articles, 
			clustered articles or scraped articles), 
			the default is the dominant plugin you've chosen.
===================   	==================================================================


Article API
------------
This endpoint will return the entire article and all its meta-data as a JSON.

**Type:** GET-Request
**Example:** https://www.monok.com/api/v1/puff/band-lady-a-files-legal-action-against-blues-singer-anita-lady-a-white

===============   ===================================================
 URL Endpoint       https://www.monok.com/api/v1/puff/​[article Id]                        
===============   ===================================================

.. _`Query Selector`: https://docs.monok.com/en/latest/articlequeryselector.html
