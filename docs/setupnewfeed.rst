Setup Automatic Daily Feed
========

Setting up an article generation news feed is done by using the profile page of your monok account.

1. Go to your profile page and add a new feed.
2. Insert the keywords for your query and any relevant location, if any
3. Choose additional settings such as interlinking or social media embeds 

Example of a UK Entertainment News Feed
---------------------------------

.. image:: images/setupgaming.png

In this example we've set up an article generation feed for news about gaming consoles. We've chosen 2 articles every Weekday (Mon-Fri). We've also chosen a 600 word human editing service, so articles are automatically passed through a human editor that expands and edits the articles.

Our Query is the following ::

    nintendo, xbox, playstation


We've also gone ahead and chosen interlinking so articles have links for previously published articles, as well as social media embeds for embeded tweets and youtube videos as well as the photos options that provides us with multiple photos for each article.

**Some Example Outputs for "UK Entertainment"**

`Katharine McPhee says hubby David Foster and Prince Harry are 'like father and son'`_ - This is an article with youtube and instagram content

`The nominated British rapper dies from coronavirus at the age of 47`_ - This is an article with youtube, twitter and embeded video content as well as multiple social media comments

`Kevin Spacey complains about treatment over claims of sexual assault`_ - This article has an automatically attached relevant photo


.. _`Katharine McPhee says hubby David Foster and Prince Harry are 'like father and son'`: https://www.monok.com/puff/katharine-mcphee-says-hubby-david-foster-and-prince-harry-are-like-father-and-son

.. _`The nominated British rapper dies from coronavirus at the age of 47`: https://www.monok.com/puff/the-nominated-british-rapper-dies-from-coronavirus-at-the-age-of-47

.. _`Kevin Spacey complains about treatment over claims of sexual assault`: https://www.monok.com/puff/kevin-spacey-compares-sexual-abuse-allegations-to-the-coronavirus-and-says-i-understand-what-it-s-like-being-told-you-can-t-work


Example of a French Health Feed
--------------------------------------------

.. image:: images/frenchhealthfeed.png

In this example, we're generating news videos with corresponding news articles, about health topics regarding france and french citizens. We make use of the "Video Generation" plugin that attempts to generate a video using the generated article text and corresponding fair use images and videos. We don't provide any publication sources, thus ensuring all possible sources are used to generate articles in this feed. Included in the plugin list is the "Geo Location" plugin, that attempts to detect the longitude and latitude of each article generated, so we may know where in France each article is mainly about.

Our Query is the following ::

    health, cause_of_death:illness, organization:who
    AND
    country:france, nationality:french, city:paris, state_or_province:champagne

We make use of the **organization** prefix to select articles that contain the abbreviation for the World Health Organization (WHO). You can read more about the different types of prefixes you can use at the Article `Query Selector`_

.. _`Query Selector`: https://docs.monok.com/en/latest/articlequeryselector.html
