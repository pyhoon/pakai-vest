# Pakai Vest

Version: 0.20

Tables and CRUD web forms extension for [Pakai Server v6](https://github.com/pyhoon/pakai-server-b4j) — a B4J web framework built with EndsMeet, MiniORM, MiniHtml, HTMX, and AlpineJS.

> NOTE: This repo is created by AntiGravity Desktop and still under development. Use it at your own risk.

## Overview

Pakai Vest adds responsive HTML tables, web CRUD forms, and REST API endpoints to any Pakai Server v6 project. It provides reusable B4X classes that can be dropped in as a library and customized for any database table or business entity.

## Features

- **CrudModel** — Generic B4J database client powered by `MiniORM` for table CRUD operations.
- **CrudView** — Programmatic HTML views (Search panel, Table listing, Add/Edit/Delete modals) built using `MiniHtml` and Bootstrap 5.
- **CrudWebHandler** — HTMX web routing handler linking views and models to handle GET/POST/PUT/DELETE partial page updates.
- **CrudApiHandler** — JSON/XML REST API endpoint handler supporting standard operations.

## Usage

1. Drop `release/Vest.b4xlib` into your B4J additional libraries folder.
2. Add the four class templates to your project: `CrudModel`, `CrudView`, `CrudWebHandler`, `CrudApiHandler`.
3. Rename the classes as appropriate (e.g. `ItemsModel`, `ItemsView`, etc.) and adjust target table/fields.
4. Register web and API routes in `AppStart`:

```b4j
' Web endpoints (HTMX)
App.Get("/items", "ItemsWebHandler")
App.Rest("/hx/items/*", "ItemsWebHandler")

' REST API endpoints
App.Rest("/api/items/*", "ItemsApiHandler")
```

## Build Configurations

| Database  | Driver                        |
|-----------|-------------------------------|
| SQLite    | sqlite-jdbc-3.7.2 (default)   |
| MariaDB   | mariadb-java-client-3.5.6     |
| MySQL     | mysql-connector-j-9.3.0       |

## Dependencies

- EndsMeet v6.80+, MiniORM, MiniHtml, MiniCSS, MiniJS, WebApiUtils
- Bootstrap 5.3, HTMX 2.x, AlpineJS 3.x (loaded via CDN)
- B4J IDE 10.5+ / Java JDK

## License

MIT — see [LICENSE.txt](LICENSE.txt)
