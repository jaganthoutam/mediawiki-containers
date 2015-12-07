# mediawiki-docker-compose

Experimental docker-compose setup for a fully-featured MediaWiki install
including VisualEditor, Parsoid, RESTBase, Mathoid & other services.

## Description

We are starting three containers:

- An Apache/MediaWiki container.
- A MySQL container, used as the database backend for MediaWiki.
- A [mediawiki-node-services](https://github.com/gwicke/mediawiki-node-services)
    container, currently running RESTBase and Parsoid in a single node process
    for memory efficiency.

All data is stored outside the containers in a host directory:

```bash
ls /var/lib/mediawiki-docker-compose/
mediawiki-core  mediawiki-mysql  node-services
```
## Usage

```bash
docker-compose up
```

## TODO

This is a fairly early prototype, and not fully functional yet. Next steps:

- Update / parametrize the mediawiki-node-services config to reference the
    "mediawiki" container by name.
- Forward `/api/rest_v1/` to RESTBase.
- Include / configure VisualEditor by default.

