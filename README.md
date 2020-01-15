# DIT032 – Data Management Setup

This documentation helps you to setup the software used during the Data Management course.

> Please let us know in the Canvas discussion forum if something doesn't work, something misses, and if you found a better solution!

## Software List

We typically recommend to install the latest version.

* PostgreSQL server and psql client `>=11.1`
* Java Development Kit (JDK) `>=11.0.1` (tested with JDK8, JDK9, JDK11)
* Maven `>=3.6.0`
* MongoDB `>=4.0.5` (Notice that older versions before 3.6.x do NOT support [new features](https://docs.mongodb.com/master/release-notes/3.6/) such as [$expr](https://docs.mongodb.com/master/reference/operator/query/expr/#op._S_expr))
* yED graph editor (for ER diagrams): https://www.yworks.com/products/yed
* RelaX (online relational algebra calculator): https://dbis-uibk.github.io/relax/calc.htm?data=gist:7ec0be1be462f65818454ca3411c7b02#
  * Help: https://dbis-uibk.github.io/relax/help.htm

## Installation

* [macOS](macOS.md)
* [Windows](Windows.md)
* [Linux](Linux.md)

## Getting Started

* [PostgreSQL](PostgreSQL.md)
* [Import Maven Project](Maven.md)
* [MongoDB](MongoDB.md)
