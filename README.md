# Spryker templates for Alumio

## Description

This repository contains a template to create a route from Akeneo to Spryker in Alumio.
This is a work in progress. A new version will be released every two weeks. 

## Importing the template

- In Alumio go to "System | Import / Export"
- Choose file spryker-from-akeneo-template.ndjson
- Click "Import configurations"

## Testing the template

### Update environment variables if needed

In Alumio go to "System | Environment variables". Create or update the following environment variables if needed:

- AKENEO_BASE_URL
- AKENEO_CLIENT_ID
- AKENEO_CLIENT_SECRET
- AKENEO_PASSWORD
- AKENEO_USERNAME}
- SPRYKER_BACKOFFICE_GLUE_BASE_URI
- SPRYKER_BACKOFFICE_GLUE_PASSWORD
- SPRYKER_BACKOFFICE_GLUE_USERNAME

### Importing Spryker identifiers to storages

To be able to store a product in Spryker, Alumio needs a mapping of codes (such as SKU, tax set names, store codes) to
identifiers.

- In Alumio, go to "Transformers | Spryker - Update Storages"
- Run the transformer tester with an empty object as input
- Verify that storages have been updated by going to "Storages"

### Inserting or updating an abstract product in Spryker

- In Alumio, go to "Transformers | Spryker - Persist - Abstract Products"
- Select "Minimal test" in the transformer tester and run it
- Verify that the product has been created or updated in Spryker

### Importing Akeneo data to storages

Alumio uses data from storages to be able to create a complete product from Akeneo data without having to do many
requests to Akeneo.

- In Alumio, go to "Transformers"
- Run the transformer tester with an empty object as input for the following transformers:
  - Akeneo - Attribute Groups to Alumio Storage
  - Akeneo - Attribute Options to Alumio Storage
  - Akeneo - Attributes to Alumio Storage
  - Akeneo - Categories to Alumio Storage
  - Akeneo - Channels to Alumio Storage
  - Akeneo - Families to Alumio Storage
  - Akeneo - Family Variants to Alumio Storage
- Verify that storages have been updated by going to "Storages"

### Fetching and transforming Akeneo products

- In Alumio, go to "Transformers | Akeneo - Product - Fetch and restructure to Alumio Base"
- Run the transformer tester with an empty object as input

### Fetching and transforming Akeneo product models

- In Alumio, go to "Transformers | Akeneo - ProductModel - Fetch and restructure to Alumio Base"
- Run the transformer tester with an empty object as input

### Transform product models to Spryker Abstract products

- In Alumio, go to "Transformers | Spryker - Alumio Base Product to Spryker Product (Abstract)"
- Select the test named "Sample" and run it.

### Transform products to Spryker Concrete products

- In Alumio, go to "Transformers | Spryker - Alumio Base Product to Spryker Product (Concrete)"
- Select the test named "Sample" and run it.