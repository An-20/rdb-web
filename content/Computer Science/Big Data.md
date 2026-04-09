'**Big Data**' is a catch-all term for data that won't fit usual containers, and can't be processed using traditional means. Big Data can be described in terms of:
- **Volume** - too much data to fit into a single server.
- **Velocity** - data can be streamed, with milliseconds to seconds to respond.
- **Variety** - data can be in many forms, including structured, unstructured, text, or multimedia.

#### Volume
For the volume of data, 'big' is a relative term, but size impacts when the data doesn’t fit onto a single server, because relational databases don’t scale well across multiple machines.

#### Velocity
Data from networked sensors, smartphones, video surveillance, mouse clicks, etc. are continuously streamed.

#### Variety
The most difficult aspect of Big Data involves the lack of structure (not size (*IS*)). This lack of structure is a challenge because:
- **Analysing** the data is significantly more difficult.
- **Relational databases** are not appropriate because they require the data to fit into a row-and-column format, while the data may be unstructured.
**Machine learning techniques** can be used to discern patterns in the data and to extract useful information.

#### Processing
When the volume of data is too large to fit on a single server, the processing must be **distributed** across multiple machines. **Functional programming** can be used, because it makes it easier to write **correct and efficient distributed code**. 

This is because functional programming languages support:
- **Immutable data structures**: data structures that cannot have their value changed after being created.
- **Statelessness**: functions that are pure, always returning the same value for a given input, not depending on any external state.
- **Higher-order functions**: functions that take other functions as arguments or return other functions, or both.

#### Fact-based models
**Fact-based models** represent a dataset using facts stored in a graph.
- **Facts** capture a single piece of information. They are atomic and timestamped, which makes them immutable as they are always true.
- **Nodes** represent core entities in the dataset, e.g. users or organisations.
- **Edges** represent relationships between nodes.
- **Properties** represent facts about nodes.

A **graph schema** defines the structure of the dataset. It defines the types of nodes, edges, and properties (facts) defined in the dataset. New types of information can be added by defining new nodes, edges, and properties in the graph schema.
