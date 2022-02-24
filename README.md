# Amplience Reference Storefront Architecture – Core Automation Files

amp-rsa-automation

This package is used by the [amprsa cli](https://github.com/amp-nova/amp-rsa-cli) to set up data for use with [Amplience Reference Storefront Architecture](https://github.com/amp-nova/amp-rsa-core).

## File Structure

```
.
├── content/
│   ├── content-items/
│   │   ├── Content/
│   │   │   └── 00 Experience Content/
│   │   │       ├── 01 Banners
│   │   │       ├── 02 Cards and Card Lists
│   │   │       ├── 04 Other Content Types
│   │   │       ├── 05 Externally Referenced Products
│   │   │       ├── 06 Blogs and Dynamic Blog Lists
│   │   │       ├── 07 Homepage
│   │   │       ├── 08 Landing Pages
│   │   │       ├── 10 Products
│   │   │       ├── 11 Layouts
│   │   │       └── 12 Stores
│   │   ├── Email Marketing
│   │   ├── Site Components
│   │   └── Slots/
│   │       └── 01 Web/
│   │           ├── Accessories
│   │           ├── Men
│   │           ├── New
│   │           ├── Sale
│   │           └── Women
│   ├── content-type-schemas/
│   │   └── schemas
│   ├── content-types
│   ├── extensions
│   ├── indexes
│   └── settings
├── media/
│   └── Templates
├── package-lock.json
├── package.json
└── README.md
```

### content

The root folder for automation content is `content`.  Let's dig in to what's inside there.

- `content-items`

    At the root level of `content-items` there are folders that represent specific repositories.  These folders can hold both content items (`*.json.hbs`) and folders.

- `content-types`

    [Content types](https://amplience.com/docs/glossary.html#content-type)

- `content-type-schemas`

    [Content type schemas](https://amplience.com/docs/integration/contenttypes.html)

- `extensions`

    Web apps that extend the functionality of Dynamic Content.  [Extensions](https://amplience.com/docs/development/extensions.html)

- `indexes`

    Indexes used with Amplience Search.  [Search Indexes](https://amplience.com/docs/development/search-indexes/readme.html)

- `settings`

    Hub settings including [workflow states](https://amplience.com/docs/production/workflow.html#workflow) and [visualization settings](https://amplience.com/docs/production/visualizations.html#visualizations)

## Handlebars template substitution

Files that end in `.hbs` are Handlebars templates, and can use the context that `amprsa` passes in to it. Here are several examples of templated variables used:

- `dam.imagesMap.<key>`

    where `key` is a camel-cased reference to an asset in dam

- `contentMap.<key>`

    where `key` is a slugified version of the content item's delivery key

- `cms.repositories.<key>`

    where `key` is a slugified version of the repository name

- `url`

    the application deployment URL (for visualizations)

- `cms.hub.name`

    hub name