# How to Configure EntityInfo Components

> EntityInfo is a collection of data visualization components that allows an entity’s information to display by opening the side panel and loading its data inside. It assigns that flow to the "click" event of whatever tag element you define. The default is a DIV, but you can configure this to a button or any other element. (Note: This requires programming knowledge.)

EntityInfo allows you to create any HTML element (and HTML children) in a custom page. That element is assigned an _onClick_ event. That click opens the side panel and displays that entity’s info on the panel. It mimics the behavior of clicking a Card in the library: the entity’s info is shown on the side panel.

This component allows you to leave the design to the page coder, so there are no styles applied. You can turn this into a button, it could be an entire section of the page, or even an area inside a graph. You decide where to use it and Uwazi provides the "click" functionality.

```jsx
<EntityInfo entity="entitySharedId" tag="div" classname="classes">More Info</EntityInfo>
```

Creates an HTML element of the type described in tag ("div" is default and can be omitted) bound to a "click" event that will load and display in the side panel, the info of the entity described in the "entity" property. The element allows further HTML structure inside, which allows you to tailor the 'button' look however you want.

## Query component

This component allows you to do API request to fetch data you may need and expose it in a react [context](https://reactjs.org/docs/context.html) ([https://reactjs.org/docs/context.html](https://reactjs.org/docs/context.html)) for that page, for example:

```jsx
<Query name="entities" url="search?limit=10&order=desc&sort=creationDate"/>
```

Will search for the last 10 entities created and will store them in the "entities" dataset to be consumed. You can access this dataset with Value or Repeat for example.

## Value component

This component prints the value in a given path of the context . For example:

```jsx
<Query name="entities" url="search?limit=10&order=desc&sort=creationDate"/>
<Value path="entities.rows.0.title"/>
```

This example will request 10 entities and then print the title of the first one.

Repeat component

The purpose of this component is to iterate over data in the context and print its contents for each entry, for example:

```jsx
<Query name="entities" url="search?limit=10&order=desc&sort=creationDate"/>

<ul>
<Repeat path="entities.rows">
     <li><Value path="title"/></li>
</Repeat>
</ul>
```

## EntityLink component

This component will generate a link to the correct entity viewer based on a given entity property.

```jsx
<Query name="entities" url="search?limit=10&order=desc&sort=creationDate"/>

<ul>
<Repeat path="entities.rows">
    <li>
         <EntityLink><Value path="title"/></EntityLink>
    </li>
</Repeat>
</ul>
```

## EntityLink implementation

Right now EntityLink is a very basic component that expects an Entity object in the property key "entity" to generate a Link to that Entity. Because of this reason, when used in the Pages it needs to be wrapped in a Value component that is connected to the context and passes the entity down, like in the example:

```jsx
<Value propkey="entity"><EntityLink>Some text</EntityLink></Value>
```
