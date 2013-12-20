### General Structure

Despite its flexible and extensible nature, Collection.Doc is a very simple media type: its primary identifier is a fully-qualified URL (`href` attribute) and it has only three other top-level elements: 

- attributes: store “state”,
- links: expose controls and communicate relationships 
- errors: are intended to facilitate reliable debugging of client/server interactions.


![Collection.Doc diagram](/img/collection+doc+json.png)