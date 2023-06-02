# dataset-utils
A collection of JavaScript functions to read and parse OpenActive Data Catalogs and Dataset Sites

## Install

Install using NPM:
```
$ npm install @openactive/dataset-utils --save
```

## Dependencies
- [Axios](https://github.com/axios/axios)

## Usage

```js
const { getAllDatasetSiteUrls } = require('@openactive/dataset-utils');
const EXAMPLE_DATA_CATALOG_COLLECTION = 'https://openactive.io/data-catalogs/data-catalog-collection.jsonld';

var datasetUrls = await getAllDatasets(EXAMPLE_DATA_CATALOG_COLLECTION);
```

## API Reference
### getAllDatasetSiteUrls(dataCatalogUrl)
 This is a recursive function that returns an array of dataset site URLs.
 If the URL supplied is a data catalog collection, it takes all the part collections in hasPart and crawls them.
 If the URL supplied is a data catalog, it takes the dataset array and flattens them. 
 If `dataCatalogUrl` is not supplied, the default OpenActive Data Catalog (`https://openactive.io/data-catalogs/data-catalog-collection.jsonld`) is used.

### extractJSONLDfromHTML(html)
This function extracts JSONLD metadata from dataset HTML
### getAllDatasets(dataCatalogUrl)
This function recursively crawls through a data catalog, fetches datasets, and extracts JSONLD from dataset HTML.
This combines getAllDatasetSiteUrls() and extractJSONLDfromHTML()
If `dataCatalogUrl` is not supplied, the default OpenActive Data Catalog (`https://openactive.io/data-catalogs/data-catalog-collection.jsonld`) is used.
