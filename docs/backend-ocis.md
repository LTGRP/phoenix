---
title: "Setup with OCIS"
date: 2020-04-15T00:00:00+00:00
weight: 50
geekdocRepo: https://github.com/owncloud/phoenix
geekdocEditPath: edit/master/docs
geekdocFilePath: backend-ocis.md
---

{{< toc >}}

## Setting up OCIS services

- Setup OCIS by cloning the [ocis repository](https://github.com/owncloud/ocis) and following the setup instructions there.
- Do not start the whole server but run `./bin/ocis --log-level debug $EXTENSION` for all the existing extensions **except the phoenix service**. A list of extensions can be found by running `./bin/ocis` without arguments and looking at the "Extensions" section.

## Setting up Phoenix

- Please note that config.json is generated by ocis-phoenix so there is no need to create one.
- If you want to provide a config.json file, you can do so by starting ocis with `PHOENIX_WEB_CONFIG=/path/to/config.json`

## Setting up ocis-phoenix service

- Clone the [ocis-phoenix repository](https://github.com/owncloud/ocis-phoenix) and follow the setup instructions there.
- Set `export PHOENIX_ASSET_PATH=$PHOENIX_CHECKOUT/dist` and replace with the path to the local git checkout of the [Phoenix repository](https://github.com/owncloud/phoenix)
- Run "ocis-phoenix": `./bin/ocis-phoenix --log-level debug server`

## Running Phoenix

- in the Phoenix checkout folder, run `yarn watch-all-ocis`
- open [https://localhost:9200](https://localhost:9200) and accept the certificate.
- when signing in, use one of the [available test users](https://github.com/owncloud/ocis#quickstart)
- whenever code changes are made, you need to manually reload the browser page (no hot reload)

## Running acceptance tests

For testing, please refer to the [OCIS testing section]({{< ref "testing.md#running-acceptance-tests-using-ocis-backend" >}})

