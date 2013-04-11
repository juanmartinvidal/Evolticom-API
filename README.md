Evolticom API
============

The Evolticom API is implemented as vanilla XML over HTTP using all four verbs (GET/POST/PUT/DELETE). Every resource, like Contact, Deal, or Company, has their own URL and are manipulated in isolation. In other words, we've tried to make the API follow the REST principles as much as we can.

You can explore the view part of the API (everything that's fetched with GET) through a regular browser. Using Firefox for this is particularly nice as it has a good, simple XML renderer (unlike Safari which just strips the tags and dumps the content). Pretty much any URL in Evolticom can be viewed in its XML form by adding the .xml extension. So `/contact/4` becomes `/contact/4.xml` if you want to see the XML version.
