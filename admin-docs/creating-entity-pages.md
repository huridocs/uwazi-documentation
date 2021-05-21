# CREATING ENTITY PAGES

## Basic concepts

Uwazi allows you to create pages for two different purposes:

- Designing your webiste (Link to wiki?) with pages that render mostly static content with additional options to include collection-wide data analysis.
- Replacing the standard Entity View with a custom page to better display and showcase data for each entity of a particular template type.

## Defining a page for a particular template

The procedure to assign a page to be used as the default view of entities of a particular template is the following:

- Create a Page: settings -> pages -> Add Page (or edit an existing page).
- Give it a descriptive name and select the "Enable this page to be used as an entity view page" toggle button. This flags this page as enabled for entity view.
- Edit the desired template configuration (settings -> templates -> edit) and enable the "Display entity view from page" toggle
- From the dropdown, select the previously created or edited page to use as page for entity view

Once this is done, when you enter the entity view for entities of that particular template, you will be presented with the page you just defined, instead of the traditional "metadata view" for that entity.

## Designing the page

The page design follows the same guidelines described in [DESIGNING YOUR WEBSITE](https://uwazi.readthedocs.io/en/latest/admin-docs/designing-your-website.html#designing-your-website) and you can include all of the extended components described on the article to further design your page. You can also include the data visualization components described in [ANALYSING & VISUALISING YOUR COLLECTION](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#analysing-visualising-your-collection).

Pay particular attention to the [Query Component](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#query-component) section of the [ANALYSING & VISUALISING YOUR COLLECTION](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#analysing-visualising-your-collection) document.

The prepartion steps of defining the page as "Enabled" to be used in entity view are important because they provide the data you need to display each entity's data. With them you have access to three automatically-created DATASETS:

- `entity`
- `entityRaw`
- `template`

These new datasets can be consumed via the `Value` and `Repeat` components, just as with any other `Query` defined data. The `entity` dataset presents "formatted" entity data, where some values have presentational values or labels added to them (like dates, for example). The `entityRaw` dataset presents you with the unprocessed data as it is stored in the database.

To use this data, you would access the entity's properties normally. For example, to print the Entity's title, you would use something like:

```
<p><Value path="entity.title" /></p>
```

This, as expected, wraps the entity's title within a paragraph tag element.

Accessing the entity's metadata requires a little more knowledge into the way Uwazi data is structured.

### entity dataset

The data has some values stored at the root level of the object, while most are stored inside the `metadata` array.

Whenever possible, this is the easiest dataset to use. This data has the advantage of having some values already processed for you. For example, dates in Uwazi are stored using [Unix time](https://en.wikipedia.org/wiki/Unix_time). The entity dataset provides the original value, but also a formatted value you can use that already takes into account date formats according to language, etc.

Take the following enttiy structure:

| Properties          | Values                             | Observations                           |
| ------------------- | ---------------------------------- | -------------------------------------- |
| Title               | Name of a book                     |                                        |
| Brief Description   | Something nice                     |                                        |
| Country             | Ecuador                            | Data based on a Thesaurus of countries |
| Date of Publication | 13 July, 1977                      | Internally this would be: 1621618430   |
| Cover Image         | yourdomain.com/media/bookCover.jpg |                                        |

Depending on the type, each property could have somewhat diferent structures. As an example, the above entity will look like this in the `entity` dataset:

```
{
  title: 'Name of a book',
  metadata: [
    {
      label: "Brief Description",
      value: "Something nice"
    },
    {
      label: "Country",
      value: "Ecuador"
    },
    {
      label: "Date of Publication",
      value: "13 July, 1977",
      timestamp: 1621618430
    },
    {
      label: "Cover Image",
      value: "yourdomain.com/media/bookCover.jpg"
    }
  ]
}
```

Note: this a simplified version of the actual data, if you want to see all the dat, the simplest way is to install the "React Developer Tools" extension for Chrome and inspect the "Redux" state tree. You will find the full structure on `page -> datasets -> entity`.

With this data, you can print out values normally. Here's a brief example:

```
<h1><Value path="entity.title" /></h1>
<ul>
  <li><Value path="entity.metadata.0.label" />: <Value path="entity.metadata.0.value" /></li>
  <li><Value path="entity.metadata.1.label" />: <Value path="entity.metadata.1.value" /></li>
  <li><Value path="entity.metadata.2.label" />: <Value path="entity.metadata.2.value" /></li>
  <li><Value path="entity.metadata.3.label" />: <Value path="entity.metadata.3.value" /></li>
</ul>
```

This HTML code will print:

---

Name of a book

- Brief Desription: Something nice
- Country: Ecuador
- Date of Publication: 13 July, 1977
- Image: yourdomain.com/media/bookCover.jpg

---

Please note that, at this point, there is no way to directly use the Cover Image URL (value) to present an image instead of the URL text in the HTML of the page. To accomplish this, you would need to use the javascript area to assign the source of the image dynamically.

### entityRaw dataset

The data has some values stored at the root level of the object, while most are stored inside the `metadata` object. Please note the different from the `entity` data, where metadata is an array of properties. Here is a brief example of what you can expect. Take the following entity structure:

| Properties       | Values                                           | Observations                                                   |
| ---------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| Title            | Title of Entity                                  |                                                                |
| Country          | India                                            | Data based on a Thesaurus of countries                         |
| Description      | A rich text description                          |                                                                |
| Related Entities | Title of another entity, Title of a third entity | Data based on two relationships selected in Relationship field |

Most properties will be inside the `metadata` object where property names are the keys (sanitized to lower case and spaces replaced with underscores) and every value is actually an array of objects that have either `value` or `label` (or both keys, depending on their type). So, internally, the above entity will look like:

```
{
  _id: "89af7g8ad98ads"
  title: "Title of Entity"
  metadata: {
    country: [{ label: "India", key: "df9a88" }],
    description: [{ value: "A rich text description" }],
    related_entities: [
      { label: "Title of another entitiy", value: "9ad8f212" },
      { label: "Title of a third entity", value: "as182736a" },
    ]
  }
}
```

So, to expand on the previous explanation, the way to extract the data for properties other than `title`, is with something like this:

```
<Value path="entityRaw.metadata.country.0.value />
```

This will print the value `India` on the page's HTML.

As noted, you could use the `Repeat` component to list both items that are stored in the "Related Entities" metadata property. Here is a more in depth example of how to create a more complex display of property name and property values:

```
<p><Value path="template.properties.2.label" />: </p>
<ul>
  <Repeat path="entityRaw.metadata.related_entities">
    <li>
      <Value path="label" />
    </li>
  </Repeat>
</ul>
```

This will print:

---

Related Entities:

- Title of another entitiy
- Title of a third entity

---

Notice that the position of the property in `template` (in this case "2") needs to be known. The order is respecting the order in which the properties are defined in the template. Still, you can ensure this by analyzing the correct array position within the template. There are several ways to accomplish this:

- do a `repeat` section of all the properties and extract their labels
- inspect the respose to the browser request to the `templates` endpoint
- inspect the redux store in `page -> datasets -> template`
- doing an API call to fetch the template
- inspecting the database directly

These are all advanced procedures. Please refer to the different sections of this documentation depending on your desired approach. Currently, there is no way to know before hand the position of a property within the template. Entites, on the other hand, are namespaced by property name, so it is easier to extract the data.
