# FeedHenry SAML Cloud App
[![Dependency Status](https://img.shields.io/david/feedhenry-templates/saml-cloud-app.svg?style=flat-square)](https://david-dm.org/feedhenry-templates/saml-cloud-app)

This is an example SAML Cloud App, designed to be used in conjunction with our sample SAML Service. The Cloud App here only proxies calls from client to an SAML Service (e.g. fetching a URL to display in the WebView for IdP login).
You must set a SAML_SERVICE environment variable with an appropriate SAML Service ID for this to work.

# Group API

# host [/sso/session/login_host]

Get URL for SSO Sign-in

## host [POST]

'host' endpoint.

+ Request (application/json)
    + Body
            {
              "token": "deviceId"
            }

+ Response 200 (application/json)
    + Body
            {
            }


# session [/sso/session/valid]

Session check endpoint

## session [POST]

'session world' endpoint.

+ Request (application/json)
    + Body
            {
              "token": "deviceId"
            }

+ Response 200 (application/json)
    + Body
            {
            }

## Build
```shell
npm install
```

## Run locally

### Setup MongoDB

In order to run the SAML server locally you'll need to have [MongoDB](https://www.mongodb.com/) installed and running on your local machine.

Start MongoDB server with:

```shell
mongod
```

By default, the SAML server will try to access MongoDB on port `11211`, if you are running MongoDB on a different port you should set the `FH_MONGODB_CONN_URL` environment variable to the MongoDB connection URL.

### Setup Redis

In order to run the SAML server locally you'll need to have [Redis](https://redis.io/) installed and running on your local machine.

Start Redis server with:
```shell
redis-server /usr/local/etc/redis.conf
```

### Start the server

```shell
grunt serve
```

The SAML server will be availble at `localhost:8001`.

If you wish to run the server on a different port you should set the `FH_PORT`
environment variable to the port you want the server to run on.

## Development

See [Cloud Development](http://docs.feedhenry.com/v2/cloud_development.html) page about how to develop cloud app.

## Tests

All the tests are in the "test/" directory. The cloud app is using mocha as the test runner.

### Unit and acceptance tests

* all the tests:

With [MongoDB](#setup-mongodb) and [Redis](#setup-redis) running

```shell
npm test
```

* unit tests:

```shell
npm run unit
```
* acceptance tests:

With [MongoDB](#setup-mongodb) and [Redis](#setup-redis) running

```shell
npm run accept
```

### Code coverage

```shell
npm run coverage
```

* coverage report for unit tests:

```shell
npm run coverage-unit
```
* coverage report for acceptance tests:

```shell
npm run coverage-accept
```

## Source code analysis

To get Plato's JavaScript source code visualization, static analysis, and complexity report:

```shell
npm run analysis
```
