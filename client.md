---
layout: typedef
title: Collection.Doc Documentation
---

# Client SDK Implementation Recommendations

Following are some suggestions for implementing a capable SDK for a Collection.Doc-driven API.

## UML Diagram of Suggested Implementation

![UML Diagram of Suggested Implementation](/img/cdoc-client.png) 

## Commentary

Any Hypermedia client must be a proper HTTP client and implement fundamental functionality such as: security, encryption and caching properly. Specifically, the SDK must provide means to properly authenticate with the server, must implement TLS/SSL and verify certificates properly, must respect caching headers sent by the server and cache information accordingly.

Proper Hypermedia SDK should never hardcode any URIs, but be able to resolve functionality provided by the API by exploring relationships and links provided by the server, following links, populating URI templates with data and submitting them to the API server.

## Flow

Much like in the HTML-driven web most interactions involve hitting some URI to grab an HTML at that URI, a typical interaction with a Collection.Document API means hitting some URI and expecting a Collection.Document in the response. If you're just starting your interaction with the API, you'd just hit the root URI of the API (e.g.: https://api.pmp.io) and expect to get enough information in return to start interacting with the API.

Given this flow, CollectionDocument class is the central class of the Client SDK design. An instance of CollectionDocument is initialized by passing a URI to the constructor. Once the document is initialized (by loading the resource at the URI), the name of the game becomes: "Let's figure out what we can do further". 

###### rels()

method returns a list of standard link relationship types, or URNs for custom link relationship types that the links in the current context support.

###### queryRels()

method returns similar list of standard link relationship types or URNs for custom link relationship types, but for queries: URI templates in the context that can be populated with data and submitted to the server.

###### links() and queries()

methods return a list/array of CollecytionDocLink and CollectionDocQuery objects respectively, that are available in the current context. Both functions also optionally take optional parameter: `relTypes` array. The optional parameter makes the links() and queries() methods filter-out all links or queries by a set of relationship types. The second argument `mode` can be either 'all' or 'any' and respectively indicates if a link should have all reltypes indicated or at least one, to make it through the filter.


###### itemsPageIterator and collectionsPageIterator()

are respectively iterators for items and collections documents, allowing easy paging through those, in case there are many of them.


###### grant() and revoke()

methods allow granting permissions to or revoking from specific user groups, which typically would be represented as CollectionDoc documents.

###### save()

allows saving of a document if its state (attributes) were updated. The save() method MUST get all the information required for updating a document, including the URI of save endpoint, from the `edit` link relationship that MUST be present in any document context.