### Links

Links attribute is possibly the most important attribute of the `Collection.doc+JSON` media type. It contains hyperlinks representing various relationships that current document has to other documents and actions that can be performed in the context of the current document.

Links is also where the biggest opportunity for standardization lies: most APIs implement the same controls in different ways. Standardizing those takes as huge way towards interoperable APIs and API clients.

In the JSON representation of the media type, the `links` field is a JSON object. Each top-level key of the JSON object is a [Link Relation Type (RFC5988)](http://tools.ietf.org/html/rfc5988#section-4) and the value is an array of `JSON links`. We call the link relationship types used for the top-level keys `Primary Relationship Type` of the corresponding links, to distinguish them from the `Secondary Relationship Type` that is explained below.

In Collection.doc+JSON terminology `JSON link` is a JSON object that has following fields:

- Either a required `href`: a proper [Uniform Resource Identifier (URI)](http://tools.ietf.org/html/rfc3986)
- or a required `href-template`: a proper [URI Template](http://tools.ietf.org/html/rfc6570).
- optional but typical `rels`: an array of secondary relationship types. Secondary relationship types further determine the semantic purpose of a link. Secondary relationship type is either a standards-registered relationship type (e.g. in case of [Navigation links](#navigation)) or a custom relationship type. Custom relationship types SHOULD be a proper, unique Uniform Resource Name (URN: [RFC2141](http://www.ietf.org/rfc/rfc2141.txt)). Typically there are multiple links associated with the primary link relation type, in a document, e.g.: you have multiple `query` type links. Secondary relationships allow us to tell the difference between various queries such as: a `query for users' and 'query for groups':
        
    ```json
    {"links" : 
       {"query" :  
            {
                "href-template": "...",
                "title": "Query for users",
                "rels": [ "urn:pmp:query:users"]
            },
            {
                "href-template": "...",
                "title": "Query for groups",
                "rels": [ "urn:pmp:query:groups"]
            }
        }
    } 
    ```

`Collection.doc+JSON` media type inherits semantic meaning of many [standard Link Relations](http://tools.ietf.org/html/rfc5988#section-6.2.2) for the Primary Link Relation Types, including the ones defined by [IANA](http://www.iana.org/assignments/link-relations/link-relations.xml) and [Microformats](http://microformats.org/wiki/existing-rel-values#non_HTML_rel_values). 


### Primary Link Relation Types

For link relation types, used in Collection.doc, rather then inventing new ones, we really tried to use popular, standard IETF link relation types wherever possible. There are a handful of important link relation types that the media type defines and a client MUST implement.

{% include links_profile.md %}

{% include links_buckets.md %}

{% include links_permissions.md %}

{% include links_nav.md %}

{% include links_alternate.md %}

#### Query

Read-only. optional. List of templated URIs <sup>[RFC](http://tools.ietf.org/html/rfc6570)</sup> that describe range of Uniform Resource Identifiers that can be constructed through variable expansion to run searches for additional documents related to the context document.


#### Edit

Read-only. optional. A URI pointing to a document that provides information required for updating the document in the current context.

#### Creator

Read-only. optional. A URI pointing to a document that describes user or an organization whose API Key originally created current document.