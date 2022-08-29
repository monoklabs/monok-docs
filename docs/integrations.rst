Integration
========

There are multiple ways of integrating with established publishing tools.
Monok allows the user to automatically generate a draft from
the chosen article, by pushing the content to their system of
choice. You can also automatically publish from Monok directly to your wordpress website, custom backend system or to your teams slack channel.

.. image:: images/dropdown.png

Wordpress
--------

A wordpress plugin is available that allows you to push out any article of your choice to your wordpress admin as a new draft. The Plugin once installed also offer a settings page where you can choose default category, resolution of featured image and other important settings.

You do not need to insert your API key or even have an API key to use this integration. It is however necessary to insert the API key in your monok settings page in wordpress if you'd like to enable automatic publish to your wordpress site from monok when you press "publish" from the dropdown or when an order is complete and submitted by our writers.

Features
**********************

- Automatic category matching
- Automatic Featured Image setup
- Choose post type
- Choose default author
- Quotes are styled according to your theme
- All embeded content is pushed (Youtube Video, Instagram Post, Twitter Post etc)
- Choose resolution of photos



Installation
**********************

1. Download this `wordpress plugin`__ and install it in your wordpress admin for the website you wish to integrate with

.. _`wordpress plugin`: https://www.monok.com/static/plugins/wp/monoksync.zip

__ `wordpress plugin`_

2. Go to your `monok profile`__ and add the url of your Wordpress admin to your list of wordpress websites.

3. To enable the ability to directly publish from Monok to your wordpress website, you will need to go to the monok settings page in your wordpress site, and insert your API-key. 

.. image:: images/integrations.png

.. _`monok profile`: https://www.monok.com/profile

__ `monok profile`_

That's it, you can then start pushing out articles by opening up an article, pressing push to wordpress and chosing your wordpress url.

Troubleshooting
**********************

Many servers limit the amount of data you can send to them. When a thumbImageData field is sent, it can exceed that limit, thus yielding a `413 Payload Too Large`_ error. To resolve this issue, make sure your Nginx value for client_max_body_size is larger than 10mb.

In some cases, the website has limited POST and GET calls by restriction of endpoints through Nginx. To resolve this, open up the following endpoint:

website.com/wp-json/monok/*

The wildcard is there because there are two paths, Nginx configurations understand wildcards

If your Nginx setup resitricts IP's, open it up for this address: 51.15.93.77

Embedding content such as tweets is easy with Wordpress. By default Monok inserts the url for a youtube or a tweet as new line in the text. If you've disabled this feature on Wordpress, you can instead embed as HTML or as a shortcode.

Our shortcode for twitter is [twitter ="..."]

Clipboard
--------
By clicking "Copy to Clipboard" from the **More** dropdown menu, the article text and it's headline are automatically saved in your clipboard, enabling you to easily paste them into your editor of choice. 

Slack
--------
If you choose the slack integration you will be asked to sign in to your slack account unless you already are. You will be presented with a list of your channels and asked to select one. Once you've selected a channel it will be added in your integration and avialable from the dropdown menu of any article. You can the push an article out to this channel with the click of a button.

Email
--------
You are also given the option of pushing out an article by email to an email address of your choice.
In the same way one inserts a url for a wordpress website, you can also type in an email address. Press the "push to draft" button on an article once you've added the email address, to be presented with the list of emails and websites you've inputed. Click anyone to have an email automatically sent with the article.

.. _`413 Payload Too Large`: https://developer.mozilla.org/en-US/docs/Web/HTTP/Status/413
