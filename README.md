# kiln-php

Static PHP builds for [Kiln](https://github.com/sameedkun/kiln) on Linux. Kiln is a free,
open-source local PHP development environment.

Each release has:

- PHP 8.2, 8.3, 8.4 and 8.5, CLI and FPM, for x86-64 Linux.
- A `.sha256` file for each archive.
- The licences of PHP and every library linked into each build.

The builds are made by [static-php-cli](https://github.com/crazywhalecc/static-php-cli),
pinned to a commit in [the workflow](.github/workflows/build.yml).

## Extensions

static-php-cli's `common` set, plus `mysqli` (WordPress), `intl`, `sodium` and `opcache`:

bcmath, bz2, calendar, ctype, curl, dom, exif, fileinfo, filter, ftp, gd, gmp, iconv, intl,
xml, mbstring, mbregex, mysqli, mysqlnd, opcache, openssl, pcntl, pdo, pdo_mysql, pdo_sqlite,
pdo_pgsql, pgsql, phar, posix, redis, session, simplexml, soap, sockets, sodium, sqlite3,
tokenizer, xmlwriter, xmlreader, zlib, zip.

## How Kiln uses them

Kiln downloads an archive only from a release here and installs it only if its SHA-256
matches the one pinned in Kiln's source. Why Kiln builds its own PHP is in Kiln's ADR 0025.

## Building

Run the **Build PHP** workflow. To publish the result, give it a release tag such as
`2026-10-27`.

## Licence

The workflow and this repository: Apache-2.0. The PHP binaries are covered by the PHP
License and by the licences of the libraries linked into them. Each release's
`php-<version>-licenses.tar.gz` contains those licences.
