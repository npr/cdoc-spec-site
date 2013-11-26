#### Collection and Item Links

Creating lists content items is one of the most important tasks in content management. Collection.Doc provides both of the two possible ways of defining a list: top-down and bottom-up.

##### Item Link 

Based on: [RFC 6573](http://tools.ietf.org/html/rfc6573)

Item link is a way to define lists top-down. This is when a document points to other documents that it contains. It's a 'contains' relationship, suitable for use-cases such as: "blog contains blog posts" or "news story contains asset documents" scenarios.

##### Collection Link 

Based on: [RFC 6573](http://tools.ietf.org/html/rfc6573)

Collection link supports the bottom-up approach. In this case child documents themselves are pointing to which parent document they're associated with. It's a 'belongs to' relationship, suitable for things like document indicating: "I belong to these certain topics".