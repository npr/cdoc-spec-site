---
layout: typedef
title: Collection.Doc Documentation
---

# Collection.Doc+JSON 

## Media Type Description

Collection Document is a read/write, recursive hypermedia type designed to facilitate flexible exchange of structured, textual content through Hypermedia APIs. 

Rather than a narrowly-defined content exchange format, it aspires to be a generic media type that can host more specific standards through semantic extensions (profiles). The main goal of the `Collection.Doc` is to standardize what is common for most content APIs (but, alas, what currently everybody implements in their own way) and to create standard extension points for the remaining portion of the functionality that could be publisher- and problem-domain-specific.

Collection.Document is based on [Collection+JSON](http://amundsen.com/media-types/collection/format/) hypermedia type and heavily leverages existing standards, such as: [URI Template, RFC6570](http://tools.ietf.org/html/rfc6570), [Home Document Specification](http://tools.ietf.org/html/draft-nottingham-json-home-03) and [IANA-registered Link Relation Types](http://www.iana.org/assignments/link-relations/link-relations.xhtml) wherever possible. 

<dl>
  <dt>Author:</dt>
  <dd>Irakli Nadareishvili, NPR (<a href="mailto:irakli@npr.org">irakli@npr.org</a>)</dd>
  <dt>Dates:</dt>
  <dd>
    2011-06-18(Created)<br>
    2013-10-32 (Updated)
  </dd>
  <dt>Status:</dt>
  <dd><span class="reg-draft">Draft</span></dd>
</dl>

## Contents

<div id="toc"></div>

<blockquote><b>NOTE:</b><br>
  The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL
  NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED",  "MAY", and
  "OPTIONAL" in this document are to be interpreted as described in
  <a href="http://tools.ietf.org/html/rfc2119" title="Key words for use in RFCs to Indicate Requirement Levels">RFC2119</a>.
</blockquote>
      
<div id="content">
  
### Recursiveness

Every instance of a `Collection.Doc` is a document and a collection at the same time. 

As a document, it contains a set of attributes (key/value pairs) and exposes controls (links). As a collection: it contains other documents that, by the virtue of also being Collection.Docs, can contain other documents themselves, which can further contain additional documents etc. The recursion can be of arbitrary depth and its flexibility allows to describe a wide variety of complex use-cases in a streamlined manner.

### Simplicity

Despite its flexible and extensible nature, Collection.Doc is a very simple media type: it has only three top-level elements: 

- attributes: store "state",
- links: expose controls and communicate relationships 
- errors: are intended to facilitate reliable debugging of client/server interactions.

</div><!-- / #content -->




