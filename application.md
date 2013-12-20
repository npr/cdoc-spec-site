---
layout: typedef
title: IANA Application
---

<style>
*, body, p, li {
  color: gray;
}

h6 {
  font-size: 1.3em;
  margin-top: 10px;
  color: black;
}

h6:after { content: ":" }
</style>

## Application for Media Type Registration

- Registration Procedures: [http://tools.ietf.org/html/rfc6838](http://tools.ietf.org/html/rfc6838)
- Registration form: [http://www.iana.org/form/media-types](http://www.iana.org/form/media-types)

<!-- - Example registration: [http://www.rfc-editor.org/rfc/rfc4735.txt](http://www.rfc-editor.org/rfc/rfc4735.txt) -->

###### Name

Irakli Nadareishvili on behalf of NPR

###### Email

irakli@npr.org

###### MIME media type name

Application


###### MIME subtype name

Vendor Tree - vnd.collection.doc+json


###### Required parameters

n/a

###### Optional parameters

n/a

###### Encoding considerations

binary

###### Security Considerations

Collection.Doc+JSON shares security issues common to all JSON content types. See RFC4627 Section #6 (http://tools.ietf.org/html/rfc4627#section-6) for additional information. Collection.Doc+JSON does not provide executable content. Information contained in Collection.Doc+JSON documents do not require
privacy or integrity services.

###### Interoperability considerations

None

###### Published specification

http://cdoc.io/spec.html

###### Applications which use this media

Various

######Additional information

1. Magic number(s) : n/a
2. File extension(s) : .json
3. Macingtosh file type code : TEXT
4. Object Identifiers: n/a

###### Person to contact for further information

1. Name : Irakli Nadareishvili
2. Email : irakli@npr.org

###### Intended Usage

Common

###### Author/Change controller

Irakli Nadareishvili