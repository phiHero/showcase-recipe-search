# 🎶 Recipe Search, powered by Typesense

This is a demo that showcases some of [Typesense's](https://github.com/typesense/typesense) features using a 2 Million database of recipes.

View it live here: [recipe-search.typesense.org](https://recipe-search.typesense.org/)

## Tech Stack

This search experience is powered by <a href="https://typesense.org" target="_blank">Typesense</a> which is
a blazing-fast, <a href="https://github.com/typesense/typesense" target="_blank">open source</a> typo-tolerant
search-engine. It is an open source alternative to Algolia and an easier-to-use alternative to ElasticSearch.

The recipe dataset is from <a href="https://github.com/Glorf/recipenlg" target="_blank">Glorf/recipenlg</a> 🙏!

The app was built using the <a href="https://github.com/typesense/typesense-instantsearch-adapter" target="_blank">
Typesense Adapter for InstantSearch.js</a> and is hosted on <a href="https://www.digitalocean.com/products/app-platform/" target="_blank">DigitalOcean's App Platform</a>.

The search backend is powered by a geo-distributed 3-node Typesense cluster running on <a href="https://cloud.typesense.org" target="_blank">Typesense Cloud</a>,
with nodes in Oregon, Frankfurt and Mumbai.

## Repo structure

- `src/` and `index.html` - contain the frontend UI components, built with <a href="https://github.com/typesense/typesense-instantsearch-adapter" target="_blank">Typesense Adapter for InstantSearch.js</a>
- `scripts/indexer` - contains the script to index the recipe data into Typesense.
- `scripts/data` - contains a 1K sample subset of the recipes database. But you can download the full dataset from the link above.

## Development

To run this project locally, install the dependencies and run the local server:

```sh
yarn
yarn run typesenseServer
ln -s .env.development .env
BATCH_SIZE=1000 yarn run indexer
yarn start
```

Open http://localhost:3000 to see the app.

## Deployment

The app is hosted on [DigitalOcean App Platform](https://www.digitalocean.com/products/app-platform/).

Pushing to master will deploy the app to production.