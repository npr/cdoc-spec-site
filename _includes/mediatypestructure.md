### General Structure

Despite its flexible and extensible nature, Collection.Doc is a very simple media type: it has only five top-level elements: 

- version: indicates the version of the Collection.Doc specification that the message conforms to.
- href: is a URI that serves as the unique identifier of the resource representation.
- attributes: represent the “state” of the resource,
- links: expose controls and communicate relationships with other documents 
- errors: are intended to facilitate reliable debugging of client/server interactions.


![Collection.Doc diagram](/img/collection+doc+json.png)