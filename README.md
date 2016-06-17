# Waterline Query Docs

> NOTE: The documentation in this repo is the next-generation of Waterline query syntax, and is not valid in the current version of Waterline.

This repo documents the query language, expected results, and error notation used by queryable [Waterline drivers](https://github.com/node-machine/driver-interface).  While the query syntax defined here (WLQL) will look familiar to anyone who has worked with Waterline or MongoDB, bear in mind that it represents a _lower-level abstraction_, and has important differences from the criteria dictionaries you might be used to working with when calling methods like `.find()`.


### Waterline Drivers
See [Waterline driver interface](https://github.com/node-machine/driver-interface).


### Waterline Query Language (WLQL)

WLQL is the query language for queryable Waterline drivers.  It allows for the composition of complex queries that can run on either a SQL datastore or a NoSQL datastore. There are a few exceptions, but for the most part, the language is completely database-independent.  It acts as an interchange format between higher level code (e.g. business logic) and native database queries (e.g. SQL strings or Mongo dictionaries).

Waterline query language is composed of _statements_.  Each statement compiles directly into a native query for a particular database, depending on the driver that is being used to do the compilation.  WLQL statements can be built and compiled in userland, but the format is also suitable for internal use within Waterline adapters.  In the latter case, the adapter uses a driver to convert a Waterline criteria dictionary into one or more WLQL statements; then compiles those statements into native queries and finally transmits that native query to the underlying database.

> Note that, while it is highly influenced by a relational/SQL databases, most of WLQL's syntax is also compatible with NoSQL databases such as MongoDB.


### Table of Contents

* [Overview](docs/overview.md)
* Syntax
  * [Finding Records](docs/read-operations.md)
  * [Writing Records](docs/write-operations.md)
  * [Aggregations](docs/aggregations.md)
* Parsing
  * [Results](docs/results.md)
  * [Errors](docs/errors.md)
* Extensions
  * [PostgreSQL Schema](docs/pg-schema.md)
  * [Sub Queries](docs/sub-queries.md)
  * [Joins](docs/joins.md)
* [Glossary](docs/glossary.md)




