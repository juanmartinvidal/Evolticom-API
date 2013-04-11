Evolticom API
============

The Evolticom API is implemented as vanilla XML over HTTP using all four verbs (GET/POST/PUT/DELETE). Every resource, like Contact, Deal, or Company, has their own URL and are manipulated in isolation. In other words, we've tried to make the API follow the REST principles as much as we can.

You can explore the view part of the API (everything that's fetched with GET) through a regular browser. Using Firefox for this is particularly nice as it has a good, simple XML renderer (unlike Safari which just strips the tags and dumps the content). Pretty much any URL in Evolticom can be viewed in its XML form by adding the .xml extension. So `/contact/4` becomes `/contact/4.xml` if you want to see the XML version.

SSL Usage
---------

If SSL is enabled for your account, ensure that you're using https.

Conventions in the API documentation
------------------------------------

In the documentation that follows, the following notation is used:

    #{text}: Indicates text that should be replaced by your own data

    ...: Indicates content from the response has been elided for brevity in documentation. See the list of data responses at the end of the page for a full description of the format of that response type.


Help us make it better
----------------------

Please tell us how we can make this API better. If you have a specific feature request or if you found a bug, please [let us know](mailto:support@evolticom.com). Also, feel free to fork these docs and send a pull request with improvements!
