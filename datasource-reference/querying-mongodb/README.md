# MongoDB

{% hint style="warning" %}
The following document assumes that you understand the [basics of connecting to databases on Appsmith](../../core-concepts/connecting-to-databases/). If not, please go over them before reading further.
{% endhint %}

{% hint style="warning" %}
The mongo database command syntax is slightly different from the mongo collection methods you may be familiar with. [Read more](https://docs.mongodb.com/manual/reference/command/nav-crud/)
{% endhint %}

All mongo queries return an array of objects where each object is a mongo document and properties of the object are the keys of the document.

Appsmith provides template queries to help with the syntax

* [Insert Query](mongo-syntax.md#insert-query)
* [Find Query](mongo-syntax.md#find-query)
* [Update Query](mongo-syntax.md#update-query)
* [Delete Query](mongo-syntax.md#delete-query)



## Taking Inputs from Widgets

Queries can take inputs from widgets using the mustache syntax inside the query **`{{ searchInput.text }}`** where **searchInput** is the name of the widget and **text** is the property of the widget.

{% hint style="warning" %}
You may need to wrap your string mustache bindings in quotes to make your query a valid JSON
{% endhint %}

```javascript
{
  "find": "users",
  "filter": {
    "role": "{{statusDropdown.selectedOptionValue}}"
  },
  "limit": 10
}
```

![Click to expand](../../.gitbook/assets/mongo-query-binding.gif)

{% page-ref page="../../core-concepts/connecting-to-databases/querying-a-database.md" %}
