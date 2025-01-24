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

- In Alumio, go to "Transformers | 	Spryker - Send - Abstract products"
- Select "Minimal test" in the transformer tester and run it
- Verify that the product has been created or updated in Spryker

### Importing and converting Akeneo data to storages

Alumio uses data from storages to be able to create a complete product from Akeneo data without having to do many
requests to Akeneo.

- In Alumio, go to "Integrations - Incoming"
- Run the following incoming configurations:
  - Akeneo - Fetch - Attribute Groups
  - Akeneo - Fetch - Attributes
  - Akeneo - Fetch - Categories
  - Akeneo - Fetch - Channels
  - Akeneo - Fetch - Families
  - Akeneo - Fetch - Product Models
  - Akeneo - Fetch - Product Models with parent
  - Akeneo - Fetch - Product Models without parent
  - Akeneo - Fetch - Products
  - Akeneo - Fetch - Products with parent
  - Akeneo - Fetch - Products without parent
- Verify that storages have been updated by going to "Storages"
- Verify that products and product models have been converted to be compatible with Alumio

### Transform product models to Spryker Abstract products

- In Alumio, go to "Transformers | Spryker - Convert - Abstract product - From Alumio base product model"
- Select the test named "Sample" and run it.

### Manual syncing attributes from Akeneo to Spryker

- In Alumio, go to "Integrations → Incoming → Akeneo - Fetch - Families";
- Run the incoming
- In Alumio, go to "Integrations → Incoming → Akeneo - Fetch - Attributes";
- Run the incoming
- In Alumio, go to "Integrations → Incoming → Spryker - Fetch - Attributes";
- Run the incoming
- In Alumio, go to "Integrations → Route → Akeneo Synchronize Atrributes to Spryker";
- Run the Route

### Automatic syncing attributes from Akeneo to Spryker

- In Alumio, go to "Integrations → Schedulers → Akeneo - Fetch and check Attributes";
- Set a schedule expression and enable the configuration;
- In Alumio, go to "Integrations → Schedulers → Spryker - Send Attributes";
- Set a schedule expression and enable the configuration.

### Manual syncing categories from Akeneo to Spryker

- In Alumio, go to "Integrations → Incoming → Akeneo - Fetch - Categories";
- Run the incoming
- In Alumio, go to "Integrations → Incoming → Spryker - Fetch - Categories";
- Run the incoming
- In Alumio, go to "Integrations → Route → Akeneo Synchronize Categories to Spryker";
- Run the Route

### Automatic syncing categories from Akeneo to Spryker

- In Alumio, go to "Integrations → Schedulers → Akeneo - Fetch Categories";
- Set a schedule expression and enable the configuration;
- In Alumio, go to "Integrations → Schedulers → Spryker - Send Categories";
- Set a schedule expression and enable the configuration.

### Syncing full products from Akeneo to Spryker

- In Alumio, go to "Integrations → Schedulers → Akeneo - Fetch complete products"
- Set a schedule expression and enable the configuration
- In Alumio, go to "Integrations → Schedulers → Spryker - Send complete products"
- Set a schedule expression and enable the configuration
