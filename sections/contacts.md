Contacts
======

Get contacts
----------

* `GET /api/contacts.xml` returns a collection of contacts that are visible to the authenticated user.
* `GET /api/contacts.xml?n=500` returns a collection of contacts that are visible to the authenticated user offset by the given amount. (page limit of 500)
* `GET /api/contacts.xml?title=CEO` returns a collection of contacts that have a specific title.
* `GET /api/contacts.xml?tag_id=#{label_id}` returns a collection of contacts that have been labeled with the label responding to `#{label_id}`.
* `GET /api/contacts.xml?since=20070425154546` returns a collection of contacts that have been created or updated since the time passed in through the URL.

If no contacts are returned for the given parameters, an empty `<contact>` container will be in the response.

When filtering with the `since` parameter, the collection is ordered by ascending `updated_at` (oldest to newest). The `since` parameter should be in the `yyyymmddhhmmss` format and in UTC.

**Response:**

``` xml
<contacts>
  <contact>
    ...
  </contact>
  <contact>
    ...
  </contact>
</contacts>
```


Get contact
----------

* `GET /api/contacts/$id?/contact/` returns a single person.

**Response:**

``` xml
<contact>
  <id type="integer">1</id>
  <first-name>John</first-name>
  <last-name>Doe</last-name>
  <title>CEO</title>
  <twitter-username>johnDoe</twitter-username>
  <linkedin-url>http://us.linkedin.com/in/john-doe</linkedin-url>
  <company-id type="integer">5</company-id>
  <company-name>Doe Inc.</company-name>
  <created-at type="datetime">2007-02-27T03:11:52Z</created-at>
  <updated-at type="datetime">2007-03-10T15:11:52Z</updated-at>
  <visible-to>Everyone</visible-to>
  <owner-id type="integer"></owner-id>
  <author-id type="integer">2</author-id>
  <email-address>john.doe@example.com</email-address>
  <phone-number>555-555-5555</phone-number>
  <labels type="array">
    <label>
      <id type="integer">1</id>
      <name>Partner</name>
    </label>
  </labels>
</contacts>
```
