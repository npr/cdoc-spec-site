#### Profile Link Relation

A profile link defines additional semantics for a message body of a Collection Document and uniquely identifies the sub-type of a document.

Collection.Doc is a generic media type intended to standardize solutions for common requiements in content web APIs. Most applications will however require to use various document sub-types that define additional document-type-specific semantics.

The href attribute of a profile link MUST be a valid URI that uniquely identifies the sub-type of a document. The URI SHOULD be dereferenceable and SHOULD point to a document explaining additional semantics.

Depending on the applicatuon needs, the dereferenceable URI of the profile link may point to any web document that can serve as a human-centric or machine-centric documentation. Examples include: another Collection Document document, an [ALPS](http://alps.io/spec/index.html) document or even a PDF. 

Profiles MAY be made inheritable using the "extends" link relation allowing re-use of profile definitions and collaboration around profile definitions. Profiles are used solely via linking. There is no requirement for a central registry of profiles. An index of profiles can be created for discoverability, but innovation around profiles is intentionally decentralized.