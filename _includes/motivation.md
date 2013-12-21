### Pedigree and Motivation

Collection.Doc+JSON (`application/vnd.collection.doc+json`), documented in the following specification, is a JSON representation of the media type. Other representations (+XML, +XHTML, +HTML) can be created, but are out of scope for this document.

Collection.Doc+JSON is heavily based on [Collection+JSON](http://amundsen.com/media-types/collection/format/) hypermedia type and  leverages existing standards, such as: [URI Template [RFC6570]](http://tools.ietf.org/html/rfc6570), [Home Document Specification](http://tools.ietf.org/html/draft-nottingham-json-home-03) and [IANA-registered Link Relation Types](http://www.iana.org/assignments/link-relations/link-relations.xhtml), wherever possible.

In contrast to some interchange formats before it, `Collection.Doc` is not a domain-specific content exchange format. Rather, `Collection.Doc` was designed to be a generic hypermedia type that can host more specific standards through semantic extensions: [profiles](http://tools.ietf.org/html/rfc6906). The primary motivation behind `Collection.Doc` is to standardize traits common to the vast majority of content APIs: aggregating content items into collections, supporting internationalization, paginating large sets, providing rights management, templated querying, facilities for content update etc.—features that, alas, currently every API unnecessarily implements in their own way. 

In addition to the standardization of common traits, we deemed it equally important to also define *standard* extension mechanisms for application-specific parts of what an API may require to implement.

