ℹ️ _This repository is part of my "Patterns of Enterprise Application Architecture" (PoEAA) catalog, based on Martin Fowler's book with the same title. For my full work with this implementation, see [kaiosilveira/poeaa](https://github.com/kaiosilveira/patterns-of-enterprise-application-architecture)_

---

# Patterns of Enterprise Application Architecture: Base patterns

Base patterns are commonly used approaches to well-known problems, such as creating objects that are only meant to carry certain values ([value objects](/value-object/)), setting up a [Registry](https://github.com/kaiosilveira/poeaa-registry/tree/main) to keep track of in-memory instances or even simply configuring a `Money` class.

## Base Patterns Catalog

[Value Object](https://github.com/kaiosilveira/poeaa-value-object/tree/main): A small simple object, like money or a date range, whose equality isn’t based on identity

[Registry](https://github.com/kaiosilveira/poeaa-registry/tree/main): A well-known object that other objects can use to find common objects and services.
