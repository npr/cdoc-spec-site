---
layout: typedef
title: Collection.Doc Documentation
---

## Collection.Doc+JSON 

### Media Type Description

Collection Document is a read/write, recursive media type intended for flexible exchange of structured textual content.

#### Recursiveness

Every instance of a `Collection.Doc` is a document and a collection at the same time. As a document, it contains a set of attributes (key/value pairs) and exposes controls (links). As a collection: it contains other documents that, by the virtue of also being Collection.Docs, can contain other documents themselves, which can further contain additional documents etc. The recursion can be of arbitrary depth and its flexibility allows to describe very complex domains in a streamlined manner.

#### Simplicity

Despite its flexible and extensible nature, Collection.Doc is a very simple media type: it has only three top-level elements: attributes, links and errors. Attributes store "state", links communicate controls and relationships, errors are intended for comfortable debugging of client/server interactions.






