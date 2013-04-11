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
<people>
  <person>
    ...
  </person>
  <person>
    ...
  </person>
</people>
```


Get contact
----------

* `GET /api/contacts/$id?/contact/` returns a single person.

**Response:**

``` xml
<person>
  <id type="integer">1</id>
  <first-name>John</first-name>
  <last-name>Doe</last-name>
  <title>Stand-in</title>
  <background>A popular guy for random data</background>
  <linkedin-url>http://us.linkedin.com/in/john-doe</linkedin-url>
  <avatar-url></avatar-url>
  <company-id type="integer">5</company-id>
  <company-name>Doe Inc.</company-name>
  <created-at type="datetime">2007-02-27T03:11:52Z</created-at>
  <updated-at type="datetime">2007-03-10T15:11:52Z</updated-at>
  <visible-to>Everyone</visible-to>
  <owner-id type="integer"></owner-id>
  <group-id type="integer"></group-id>
  <author-id type="integer">2</author-id>
  <contact-data>
    <email-addresses>
      <email-address>
        <id type="integer">1</id>
        <address>john.doe@example.com</address>
        <location>Work</location>
      </email-address>
    </email-addresses>
    <phone-numbers>
      <phone-number>
        <id type="integer">2</id>
        <number>555-555-5555</number>
        <location>Work</location>
      </phone-number>
      <phone-number>
        <id type="integer">3</id>
        <number>555-666-6666</number>
        <location>Home</location>
      </phone-number>
    </phone-numbers>
  </contact-data>
  <!-- custom fields -->
  <subject_datas type="array">
    <subject_data>
      <id type="integer">3</id>
      <value>Chicago</value>
      <subject_field_id type="integer">1</subject_field_id>
      <subject_field_label>Sales Region</subject_field_label>
    </subject_data>
    <subject_data>
      <id type="integer">5</id>
      <value>John</value>
      <subject_field_id type="integer">2</subject_field_id>
      <subject_field_label>Account Manager</subject_field_label>
    </subject_data>
  </subject_datas>
  <tags type="array">
    <tag>
      <id type="integer">1</id>
      <name>Partner</name>
    </tag>
  </tags>
</person>
```
