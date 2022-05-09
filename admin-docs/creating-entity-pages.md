# CREATING ENTITY PAGES

## Basic concepts

Uwazi allows you to create pages for two different purposes:

- [Designing your website](https://uwazi.readthedocs.io/en/latest/admin-docs/designing-your-website.html#designing-your-website) with pages that render mostly static content with additional options to include collection-wide data analysis.
- Replacing the standard Entity View with a custom page to better display and showcase data for each entity of a particular template type.

## Defining a page for a particular template

The procedure to assign a page to be used as the default view of entities of a particular template is the following:

- Create a Page: Settings -> Pages -> Add Page (or edit an existing page).
- Give it a descriptive name and select the "Enable this page to be used as an entity view page" toggle button. This flags this page as enabled for entity view.
- Edit the desired template configuration (Settings -> Templates -> Edit) and enable the "Display entity view from page" toggle.
- From the dropdown, select the previously created or edited page to use as page for entity view.

Once this is done, when you enter the entity view for entities of that particular template, you will be presented with the page you just defined, instead of the traditional "metadata view" for that entity.

## Designing the page

The page design follows the same guidelines described in [DESIGNING YOUR WEBSITE](https://uwazi.readthedocs.io/en/latest/admin-docs/designing-your-website.html#designing-your-website) and you can include all of the extended components described on the article to further design your page. You can also include the data visualization components described in [ANALYSING & VISUALISING YOUR COLLECTION](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#analysing-visualising-your-collection).

### EntitySection component

Sometimes you want to display a section of the entity based on whether a given condition is met.

Examples:

You want to display the name of a person if they are older than 18 years old.
A simple implementation would look like this:

```html
<EntitySection show-if='{"metadata.age": { "$gt": 18 }}'>
  <EntityData label-of="name" />: <EntityData value-of="name" />
</EntitySection>
```

you want to only show the name of a person if the name exists in the entity metadata

```html
<EntitySection show-if='{"metadata.name": { "$exists": true }}'>
  <EntityData label-of="name" />: <EntityData value-of="name" />
</EntitySection>
```

You want to show the name of a person if it matches value `John` in the entity metadata

```html
<EntitySection show-if='{"metadata.name": "John"}'>
  <EntityData label-of="name" />: <EntityData value-of="name" />
</EntitySection>
```

Inherited properties:

```html
<EntitySection show-if='{"metadata.inherited_text": { "$in": ["something"] }}'>
  <EntityData label-of="name" />: <EntityData value-of="name" />
</EntitySection>
```

Note: `show-if` value is a JSON string and the query should follow query string specified by [sift](https://github.com/crcn/sift.js)

The metadata is unwrapped into a JSON object with keys as the property names and values as the property values.

```js
metadata: {
  name: "John",
  age: 18
}

// Note that if the metadata property name has spaces, they are replaced with underscores and uppercase letters are converted to lowercase letters
// Eg: a metadata property name of "First Name" will be converted to "first_name" therefore:
metadata: {
  "first_name": "John",
  age: 18
}

```

Some values takes the following format, this includes inherited values and values like multiselect:

```js
metadata: {
    inherited_text: ['text value'], //Can contain more than one values depending on entities inherited from
    inherited_multiselect: ['option 1', 'option 2'],
    inherited_geolocation: [{ lat: 23, lon: 12}]
}
```

Note that some values like Date added and Date modified are replaced with `creationDate` and `editDate` respectively and also are presented as timestamps. So, to use them, you can do this:

```html
<EntitySection show-if='{"editDate": 12434564323 }'>
  <EntityData label-of="name" />: <EntityData value-of="name" /> // This only
  shows if the entity
</EntitySection>
```

### EntityData component

The simplest way to extract values from an Entity in a Page is with the new component `<EntityData>`.

This component will render the same HTML you see when you go to an Entity view. Therefore, it is already pre-processed and text fields will render as plain text, rich texts will have HTML tags to render properly, images will include an HTML `<img>` tag with the correct source, etc. This is a convenient way to quickly access property values and their corresponding labels (properly translated for each language).

The `<EntityData>` component takes one of two properties:

- `value-of`: a string representing the name of the property of the **value** be rendered
- `label-of`: a string representing the name of the property of the **label** to be rendered

Take the following entity structure as example:

| Properties          | Values                             |
| ------------------- | ---------------------------------- |
| Title               | Name of a book                     |
| Brief Description   | Something nice                     |
| Country             | Ecuador                            |
| Date of Publication | 13 July, 1977                      |
| Cover Image         | yourdomain.com/media/bookCover.jpg |

You have access to property names and values passing the correct HTML syntax. For example, the following code:

```html
<h1><EntityData value-of="title" /></h1>
<ul>
  <li>
    <EntityData label-of="Brief Description" />:
    <EntityData value-of="Brief Description" />
  </li>
  <li><EntityData label-of="Country" />: <EntityData value-of="Country" /></li>
  <li>
    <EntityData label-of="Date of Publication" />:
    <EntityData value-of="Date of Publication" />
  </li>
  <li>
    <EntityData label-of="Cover Image" />: <EntityData value-of="cover_image" />
  </li>
</ul>
```

will output:

---

Name of a book

- Brief Desription: Something nice
- Country: Ecuador
- Date of Publication: 13 July, 1977
- Image: ![Book Cover](https://binaries.templates.cdn.office.net/support/templates/en-us/lt22301254_quantized.png)

---

Notice that the code would be identical for different languages if you have your content and labels properly translated, so this is a useful feature. You would still need to define the HTML for each language, but they would all be identical.

### Advanced design

If the EntityData component is not verstaile enough for your needs, pay particular attention to the [Query Component](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#query-component) section of the [ANALYSING & VISUALISING YOUR COLLECTION](https://uwazi.readthedocs.io/en/latest/admin-docs/analysing-and-visualising-your-collection.html#analysing-visualising-your-collection) document.

The preparation steps of defining the page as "Enabled" to be used in entity view are important because they provide the data you need to display each entity's data. With them you have access to four automatically-generated DATASETS:

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

The data has some values stored at the root level of the object, while most are stored inside the `metadata` object.

If `EntityData` is not a valid option for your needs, this is the easiest dataset to use. This data has the advantage of having some values already pre-processed for you, but not to the level of `EntityData`. For example, dates in Uwazi are stored using [Unix time](https://en.wikipedia.org/wiki/Unix_time). The `entity` dataset provides the original value, but also a formatted value you can use that already takes into account date formats according to language, etc. It also includes the template labels correctly translated.

Take the following entity structure:

| Properties          | Values                             | Observations                           |
| ------------------- | ---------------------------------- | -------------------------------------- |
| Title               | Name of a book                     |                                        |
| Brief Description   | Something nice                     |                                        |
| Country             | Ecuador                            | Data based on a Thesaurus of countries |
| Date of Publication | 13 July, 1977                      | Internally this would be: 1621618430   |
| Cover Image         | yourdomain.com/media/bookCover.jpg |                                        |

Depending on the type, each property could have somewhat different structures. As an example, the above entity will look like this in the `entity` dataset:

```js
{
  title: 'Name of a book',
  metadata: {
    brief_description: {
      label: "Brief Description",
      value: "Something nice"
    },
    country: {
      label: "Country",
      value: "Ecuador"
    },
    date_of_publication: {
      label: "Date of Publication",
      value: "13 July, 1977",
      timestamp: 1621618430
    },
    cover_image: {
      label: "Cover Image",
      value: "yourdomain.com/media/bookCover.jpg"
    }
  }
}
```

Note: this a simplified version of the actual data, if you want to see all the data, there are a couple of ways. One is described at the end of this page, another is to install the "React Developer Tools" extension for Chrome and inspect the "Redux" state tree. You will find the full structure on `page -> datasets -> entity`.

With this data, you can print out values and labels following the usual `Value` component flow. Here's a brief example:

```
<h1><Value path="entity.title" /></h1>
<ul>
  <li><Value path="entity.metadata.brief_description.label" />: <Value path="entity.metadata.brief_description.value" /></li>
  <li><Value path="entity.metadata.country.label" />: <Value path="entity.metadata.country.value" /></li>
  <li><Value path="entity.metadata.date_of_publication.label" />: <Value path="entity.metadata.date_of_publication.value" /></li>
  <li><Value path="entity.metadata.cover_image.label" />: <Value path="entity.metadata.cover_image.value" /></li>
</ul>
```

This HTML code will print:

---

Name of a book

- Brief Description: Something nice
- Country: Ecuador
- Date of Publication: 13 July, 1977
- Image: yourdomain.com/media/bookCover.jpg

---

The metadata keys are the property names (sanitized to lower case and spaces replaced with underscores). Please note that you cannot directly use the Cover Image URL (value) to present an image instead of the URL text in the HTML of the page. To accomplish this, you need to use the `EntityData` component or, if you need more options, you would need to use the javascript area to assign the source of the image dynamically.

### entityRaw and template datasets

The `entity` and `entityRaw` datasets have some values stored at the root level of the object, while most are stored inside the `metadata` object. Here is a brief example of what you can expect from the `entityRaw` dataset. Take the following entity structure:

| Properties       | Values                                           | Observations                                                   |
| ---------------- | ------------------------------------------------ | -------------------------------------------------------------- |
| Title            | Title of Entity                                  |                                                                |
| Country          | India                                            | Data based on a Thesaurus of countries                         |
| Description      | A rich text description                          |                                                                |
| Related Entities | Title of another entity, Title of a third entity | Data based on two relationships selected in Relationship field |

Most properties will be inside the `metadata` object where the keys are the property names (sanitized to lower case and spaces replaced with underscores) and every value is actually an array of objects that have either `value` or `label` (or both keys, depending on their type). So, internally, the above entity will look like:

```
{
  _id: "89af7g8ad98ads"
  title: "Title of Entity"
  metadata: {
    country: [{ label: "India", key: "df9a88" }],
    description: [{ value: "A rich text description" }],
    related_entities: [
      { label: "Title of another entity", value: "9ad8f212" },
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

As noted, you could use the `Repeat` component to list both items that are stored in the "Related Entities" metadata property. Here is a more in depth example of how to create a more complex display of property name and property values (also using the `template` dataset):

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

- Title of another entity
- Title of a third entity

---

Notice that the position of the property in `template` (in this case "2") needs to be hardcoded to the array. The order respects the order in which the properties are defined in the template. Still, you can inspect this by analyzing the correct array position within the template. There are several ways to accomplish this:

- explore your datasets (described in the next section)
- do a `repeat` section of all the properties and extract their labels
- inspect the response to the browser request to the `templates` endpoint
- inspect the redux store in `page -> datasets -> template`
- doing an API call to fetch the template
- inspecting the database directly

These are all advanced procedures. Please refer to the different sections of this documentation depending on your desired approach. As noted, whenever possible, use the `EntityData` component first, if this does not provide with enough versatility try the `entity` dataset as it has more data and it is simpler to use. If not, default to the `entityRaw` dataset. Only use the javascript section of a page if all else fails.

## Dynamically accessing data from entities or templates

You can insert values from the entity or the template dynamically by using an expression similarly to JavaScript’s string literal variable interpolation: `${...}`

Any property path wrapped in `${...}` will be parsed and converted into the corresponding value. For example:

- `${entity.title}` will return the entity’s title.
- `${template.color}` will return the template’s color.
- `${entity.metadata.my_property_name}` will bring the value from that property.
- `${entity.metadata.my_select_property.displayValue}` will bring the value as displayed by the UI. In the case of selects or dates the display value would be a human readable value, instead of a thesauri ID or a timestamp.
- `${entity.metadata.my_multiselect_property[1]}` in cases where a property can have multiple values, using a numeric index will select the value corresponding to the index. When the numeric index is omitted it will be interpreted as if it was [0] and bring the first value.
- `${entity.metadata.my_multiselect_property[2].displayValue}` similar to the previous case, only that this would return the display value.

This can be used to dynamically insert any property from the entity or template anywhere: an HTML label property like a class, an `<img />` source attribute, in the displayed content of the page itself, etc…

An interesting way of using these dynamic values is to create `<Query />`components with urls that can vary depending on the entity's values.

For example: `<Query name="myQuery" url="search?limit=10&order=desc&sort=creationDate&filters:(text:'`**${entity.metadata.text}**`')"/>`

If you only want to display an entity's property, `EntitySection` and `EntityData` components are a better suited to do it. This dynamic access via property paths is an alternative for other advanced uses.

## Exploring your datasets

You can check the specific Entity-related datasets in a page by following this procedure.

1. Create a new page with a title and the following contents:

```
<h1>My page's Datasets</h1>
<h3>Formatted entity data</h3>
<pre id="formatted-entity"></pre>
<hr />
<h3>Raw entity data</h3>
<pre id="raw-entity"></pre>
<hr />
<h3>Entity for dynamic values</h3>
<pre id="entity-data"></pre>
<hr />
<h3>Template data</h3>
<pre id="template-data"></pre>
```

2. Add the following script to the page:

```
document.getElementById('formatted-entity').innerHTML = JSON.stringify(datasets.entity, null, 1);
document.getElementById('raw-entity').innerHTML = JSON.stringify(window.store.getState().page.datasets.toJS().entityRaw, null, 1);
document.getElementById('entity-data').innerHTML = JSON.stringify(window.store.getState().page.datasets.toJS().entityData, null, 1);
document.getElementById('template-data').innerHTML = JSON.stringify(window.store.getState().page.datasets.toJS().template, null, 1);
```

3. Enable the page to be used as an entity view.
4. Assign the page to any template you would like for viewing it's entities datasets.

Now, when you go to `view` any of the entities using that template, you will be able to see the Entity-specific datasets available.
