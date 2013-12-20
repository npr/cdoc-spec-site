### Attributes

The `attributes` field is a JSON object that represents static state of the document. If you view a `Collection.doc+JSON` as encapsulating controls (links) and state, then `attributes` is where the state resides. The meaning of each attribute depends on the [profile](http://www.ietf.org/rfc/rfc6906.txt) of the document.

The attributes and their semantic meaning defined for the base media type are as follows:

#### guid 

Read-only, optional.May be present on output only. Unique internal identifier of a document. A UUIDv4 schema SHOULD be used for generating guids. The only time an API client needs GUID directly is when creating a new document. Documents that are merely collections of search results will not have a GUID, as a search result collection is a dynamic resource identified by the URL of the search query itself.

The difference between the top-level "href" field of a doucment and the "guid" attribute is that "hreF" identifies document representation as served by a specific API endpoint, whereas "guid" can identify the content item itself. If two documents are published by two API servers, they SHOULD have the same guid, but they MAY have different hrefs.

#### title

Read/write, optional. Title of the document.

#### hreflang 

Read/write, optional. ISO639-1 code of the language of the document. Defaults to 'en'.

#### valid 

Read/write, optional. The date-times that content is valid from and to. In ISO 8601 format. Allows scheduling of document publishing and expiration of content. API Clients MUST respect valid from/to fields. This field has following rules:
  - `valid.from` is optional and if omitted, `valid.from` = `created` date.
  - `valid.to` is optional and if omitted, `valid.to` = `valid.from` date + 1,000 years.

#### created 

Read-only, auto-generated. Date the content item was first saved, in ISO 8601 format. This field is system-generated and read-only to the API clients.

#### modified 

Read-only, date the content item was last modified, in ISO 8601 format. This field is system-generated and read-only to the API clients.
