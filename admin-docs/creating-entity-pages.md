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

The prepartion steps of defining the page as "Enabled" to be used in entity view are important because that provides the data you need to display each entity's data. This preparation steps provide you with two automatically-created DATASETS:

- `currentEntity`
- `currentTemplate`.

These new datasets can be consumed via the `Value` and `Repeat`, just as with any other `Query` defined data.

For example, to extract the Entity's title, you would use something like:

```
<p><Value path="currentEntity.title" /></p>
```

This already wraps the entity's title within a paragraph tag element.

Accessing the entity's metadata requires a little more knowledge into the way Uwazi stores the data, but here is a brief explanation of what you can expect. For the following entity example:

| Properties       | Values                                           | Observations                                                   |
| ---------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| Title            | Title of Entity                                  |                                                                |
| Country          | India                                            | Data based on a Thesaurus of countries                         |
| Description      | A rich text description                          |                                                                |
| Related Entities | Title of another entity, Title of a third entity | Data based on two relationships selected in Relationship field |

You need to know that every entity has its `metadata` stored in `entity.metadata`. This property is an object where property names are the keys (sanitized to lower case and spaces replaced with underscores) and every value is actually an array of objects that have either `value` or `label` or both keys, depending on their type. So, internally, the above entity will look like:

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

So, to expand on the previous explanation, the way to extract the data for properties other than `title`, you would need something like this:

```
<Value path="currentEntity.metadata.country.0.value />
```

This will print the value `India` on the page's HTML.

As noted, you could use the `Repeat` component to list al the "Related Entities". Here is a more complex example of how to create a more complex display of property name and property values:

```
<p><Value path="currentTemplate.properties.2.label" />: </p>
<ul>
  <Repeat path="currentEntity.metadata.related_entities">
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

Notice that the position of the property in `currentTemplate` (in this case "2") needs to be inspected via the API or analyzing the respose to the request on the browser. There is no way to know before hand the position of a property in the template. In the entites, they are namespaced by property name, so it is easier to extract the data.
