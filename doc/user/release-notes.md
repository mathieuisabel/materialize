---
title: "Release Notes"
description: "What's new in this version of Materialize"
menu: "main"
weight: 500
---

This page details changes between versions of Materialize, including:

- New features
- Major bug fixes
- Substantial API changes

For information about available versions, see our [Versions page](../versions).

## 0.1.1 &rarr; 0.1.2 (unreleased)
<span id="v0.1.2"></span>

- Change [`SHOW CREATE SOURCE`] to render the full SQL statement used to create
  the source, in the style of [`SHOW CREATE VIEW`], rather than displaying a URL
  that partially describes the source. The URL was a vestigial format used in
  [`CREATE SOURCE`] statements before v0.1.0.

- Raise the maximum SQL statement length from approximately 8KiB to
  approximately 64MiB.

- Support casts from [`text`] to [`date`], [`timestamp`], [`timestamptz`], and
  [`interval`].

- Support the `IF NOT EXISTS` clause in [`CREATE VIEW`] and
  [`CREATE MATERIALIZED VIEW`].

- Attempt to automatically increase the nofile rlimit to acceptable levels, as
  creating multiple Kafka sources can quickly exhaust the default nofile rlimit
  on some platforms.

- Improve CSV parsing speed by 5-6x.

[`CREATE SOURCE`]: ../sql/create-source
[`SHOW CREATE SOURCE`]: ../sql/show-create-source
[`SHOW CREATE VIEW`]: ../sql/show-create-view
[`CREATE MATERIALIZED VIEW`]: ../sql/create-materialized-view
[`CREATE VIEW`]: ../sql/create-view
[`text`]: ../sql/types/text
[`date`]: ../sql/types/date
[`timestamp`]: ../sql/types/timestamp
[`timestamptz`]: ../sql/types/timestamptz
[`interval`]: ../sql/types/interval

## 0.1.0 &rarr; 0.1.1
<span id="v0.1.1"></span>

* Specifying the message name in a Protobuf-formatted source no longer requires
  a leading period.

- **Indexes on sources**: You can now create and drop indexes on sources, which
  lets you automatically store all of a source's data in an index. Previously,
  you would have to create a source, and then create a materialized view that
  selected all of the source's content.

## _NULL_ &rarr; 0.1.0
<span id="v0.1.1"></span>

- [What is Materialize?](../overview/what-is-materialize/)
- [Architecture overview](../overview/architecture/)
