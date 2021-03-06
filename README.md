Metrics Client Documentation
============================

Query Log Format
----------------

Provides a platform for recording, aggregating, publishing and accessing metrics produced by your host system, shared resource, or application. 


###Versions

#### 2H *(Proposed)*

* *Example Not Available*
* *Schema Not Available*

Changes:
* Include time offset relative to initTimestamp on each timer sample.
* Network sink for writing directly to Tsd Aggregator using TCP or UDP.
* Add shutdown procedure to factory and propgate to sinks and encoders.

#### 2G

** [Example](examples/query-log-example-2g.json)
** [Schema](schema/query-log-schema-2g.json)

Changes:
* Add Support for dimensions
* Remove restriction against additional root fields
* Simplify annotations by extracting id and date
* [Binary file format](https://github.com/InscopeMetrics/client-protocol) in addition to standard and steno wrapped JSON.

#### 2F

* Standard:
** [Example](examples/query-log-example-2f.json)
** [Schema](schema/query-log-schema-2f.json)
* Steno:
** [Example](examples/query-log-steno-example-2f.json)
** [Schema](schema/query-log-steno-schema-2f.json)

Changes:
* Support for compound units (e.g. Megabytes per second).
* Fully self-describing:
    * Includes service name
    * Includes cluster name
    * Includes host name

#### 2E

* [Example](query-log-example-2e.json)
* [Schema](query-log-schema-2e.json)

Changes:
* Wrap the metrics payload in a formatted container to better support general log routing and storage.
    * The time, name and level fields must be serialized first and in that order.
    * The time must be in ISO8601 with date, time and timezone.

#### 2D

* [Example](query-log-example-2d.json)
* [Schema](query-log-schema-2d.json)

Changes:
* Expand counter, timer and gauge samples to include optional units.
* Switch finalTimestamp and initTimestamp annotations from epoch to ISO8601.

#### 2C

* [Example](query-log-example-2c.json)
* [Schema](query-log-schema-2c.json)

Changes:
* First standardized JSON format.

#### Pre-2C

All versions prior to 2C of the file format are considered *deprecated*.

License
-------

Published under Apache Software License 2.0, see LICENSE

&copy; Groupon Inc., 2015

