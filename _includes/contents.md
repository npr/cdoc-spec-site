## Contents

{% include toc.html %}

<blockquote><b>NOTE:</b><br>
  The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
  NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
  "OPTIONAL" in this document are to be interpreted as described in
  <a href="http://tools.ietf.org/html/rfc2119" title="Key words for use in RFCs to Indicate Requirement Levels">RFC2119</a>.
</blockquote>

### Recursiveness

Collection.Doc is a recursive hypermedia type. Every instance of a `Collection.Doc` is a document and a collection at the same time. 

As a document, it contains a set of attributes (key/value pairs) and exposes controls (links). As a collection: it contains other documents that, by the virtue of also being Collection.Docs, can contain other documents themselves, which can further contain additional documents etc. The recursion can be of arbitrary depth and its flexibility allows to describe a wide variety of complex use-cases in a streamlined manner.

### General Structure

Despite its flexible and extensible nature, Collection.Doc is a very simple media type: it has only three top-level elements: 

- attributes: store "state",
- links: expose controls and communicate relationships 
- errors: are intended to facilitate reliable debugging of client/server interactions.


![Collection.Doc diagram](https://raw.github.com/publicmediaplatform/pmpdocs/master/charts/collection+doc+json.png)