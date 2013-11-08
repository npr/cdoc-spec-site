#### Profile Link Relation

Profile link allows publishers to define additional, domain-specific semantics on top of the media type. This is how you would define the semantic meaning of the attributes of the specific content types--which is an important task in content publishing. 

In Collection.doc profiles MUST also be inheritable, through the "extends" link relation, allowing re-use and collaboration. Profile definitions are themselves instances of the collection document type and are saved just like any other document is. Which means: to define a new profile, you don't have to go through a standards body. Innovation around profiles is decentralized. Decentralization is good for any innovation process.

A sample of a profile document that a profile link may point to would look something like the following:

```json
{
  "version" : "1.0",
  "attributes": {
    "created": "2013-10-17T17:24:46+00:00",
    "guid": "b9ce545e-01a2-44d0-9a15-a73da4ed304b",
    "modified": "2013-11-08T13:42:58+00:00",
    "published": "2013-02-11T13:21:31+00:00",
    "title": "Story Profile",
    "valid": {
      "from": "2013-02-11T13:21:31+00:00",
      "to": "3013-05-11T13:21:31+00:00"
    }
  },
  "links": {
    "alternate": [
      {
        "href": "https://api-sandbox.pmp.io/profiles/story"
      }
    ],
    "creator": [
      {
        "href": "https://api-sandbox.pmp.io/docs/af676335-21df-4486-ab43-e88c1b48f026"
      }
    ],
    "documentation": [
      {
        "href": "https://github.com/publicmediaplatform/pmpdocs/wiki/News-Story-Profile",
        "type": "text/html"
      }
    ],
    "edit": [
      {
        "hints": {
          "allow": [
            "PUT",
            "DELETE"
          ],
          "docs": "https://github.com/publicmediaplatform/pmpdocs/wiki/Collection.doc-JSON-Media-Type",
          "formats": [
            "application/vnd.pmp.collection.doc+json"
          ]
        },
        "href-template": "https://publish-sandbox.pmp.io/docs{/guid}",
        "href-vars": {
          "guid": "https://github.com/publicmediaplatform/pmpdocs/wiki/Globaly-Unique-Identifiers-for-PMP-Documents"
        },
        "rels": [
          "urn:pmp:form:documentsave"
        ],
        "title": "Document Save"
      }
    ],
    "extends": [
      {
        "href": "https://api-sandbox.pmp.io/profiles/base"
      }
    ],
    "navigation": [
      {
        "href": "https://api-sandbox.pmp.io/docs?guid=b9ce545e-01a2-44d0-9a15-a73da4ed304b",
        "rels": [
          "urn:pmp:navigation:self"
        ]
      }
    ],
    "profile": [
      {
        "href": "https://api-sandbox.pmp.io/profiles/profile"
      }
    ],
    "schema": [
      {
        "href": "https://api-sandbox.pmp.io/schemas/story",
        "scope": "update",
        "type": "application/schema+json"
      }
    ]
  }
}
```