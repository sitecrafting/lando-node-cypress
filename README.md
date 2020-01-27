# lando-node-cypress

Run Cypress inside a Lando-compatible Node container.

This image satisfies two simple requirements:

* To be usable as a `node:custom` image for a [Lando Node service](https://docs.lando.dev/config/node.html)
* To be compatible with [Cypress](https://cypress.io), the end-to-end test runner

To that end, lando-node-cypress is extremely minimal, replicating the Lando-
native Node service image but also including `xvfb`, which is required for
Cypress's headless browser testing.

## Usage

```
docker run -it sitecrafting/lando-node-cypress:8.11
```

## Example Landofile

NOTE: this syntax is for Lando **3.0.0-rc.2** and above. See [Updating to 3.0.0-rc.2+](https://docs.lando.dev/guides/updating-to-rc2.html#new-images) for details.

```yaml
name: lando-node-cypress-example
recipe: lamp
config:
  php: '7.0'

services:
  cypress:
    type: node:8

    run:
      # This assumes you have declared `cypress` as a dependency in package.json
      - yarn cypress install

    overrides:
      image: 'sitecrafting/lando-node-cypress:8.11'
```
