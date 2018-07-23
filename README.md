# lando-node-cypress

Run Cypress inside a Lando-compatible Node container.

This image satisfies two simple requirements:

* To be usable as a `node:custom` image for a [Lando Node service](https://docs.devwithlando.io/services/node.html)
* To be compatible with [Cypress](https://cypress.io), the end-to-end test runner

To that end, lando-node-cypress is extremely minimal, replicating the Lando-
native Node service image but also including `xvfb`, which is required for
Cypress's headless browser testing.

## Usage

```
docker run -it sitecrafting/lando-node-cypress:8.11
```
