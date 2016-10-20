# jsontableschema-sql-py

[![Travis](https://img.shields.io/travis/frictionlessdata/jsontableschema-sql-py/master.svg)](https://travis-ci.org/frictionlessdata/jsontableschema-sql-py)
[![Coveralls](http://img.shields.io/coveralls/frictionlessdata/jsontableschema-sql-py/master.svg)](https://coveralls.io/r/frictionlessdata/jsontableschema-sql-py?branch=master)
[![PyPi](https://img.shields.io/pypi/v/jsontableschema-sql.svg)](https://pypi.python.org/pypi/jsontableschema-sql)
[![SemVer](https://img.shields.io/badge/versions-SemVer-brightgreen.svg)](http://semver.org/)
[![Gitter](https://img.shields.io/gitter/room/frictionlessdata/chat.svg)](https://gitter.im/frictionlessdata/chat)

Generate and load SQL tables based on JSON Table Schema descriptors.

## Getting Started

### Installation

```bash
pip install jsontableschema-sql
```

### Tabular Storage

Package implements [Tabular Storage](https://github.com/frictionlessdata/jsontableschema-py#storage) interface.

SQLAlchemy is used as sql wrapper. We can get storage this way:

```python
from sqlalchemy import create_engine
from jsontableschema_sql import Storage

engine = create_engine('sqlite:///:memory:', prefix='prefix')
storage = Storage(engine)
```

Then we could interact with storage:

```python
storage.buckets
storage.create('bucket', descriptor)
storage.delete('bucket')
storage.describe('bucket') # return descriptor
storage.iter('bucket') # yield rows
storage.read('bucket') # return rows
storage.write('bucket', rows)
```

### Mappings

```
schema.json -> SQL table schema
data.csv -> SQL talbe data
```

### Drivers

SQLAlchemy is used - [docs](http://www.sqlalchemy.org/).

## Contributing

Please read the contribution guideline:

[How to Contribute](CONTRIBUTING.md)

Thanks!
