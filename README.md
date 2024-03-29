** Modified version for local use -- paginification still styled like a donkey's ass and even harder to understand how to customize ?? {{text}} or {{content}} with page class... If you find a work about post it in issues. 

*** can conflict with cfs.collections if you don't have all your session, null variables aligned. 



Easy Search [![Commitizen friendly](https://img.shields.io/badge/commitizen-friendly-brightgreen.svg)](http://commitizen.github.io/cz-cli/) 
=====================

Easy Search is a simple and flexible solution for adding search functionality to your Meteor App. Use the Blaze Components + Javascript API to [get started](http://matteodem.github.io/meteor-easy-search/getting-started).

```javascript
// On Client and Server
const Players = new Mongo.Collection('players'),
  PlayersIndex = new EasySearch.Index({
    collection: Players,
    fields: ['name'],
    engine: new EasySearch.Minimongo()
  });
```

```javascript
// On Client
Template.searchBox.helpers({
  playersIndex: () => PlayersIndex
});
```

```html
<template name="searchBox">
    {{> EasySearch.Input index=playersIndex }}

    <ul>
        {{#EasySearch.Each index=playersIndex }}
            <li>Name of the player: {{name}}</li>
        {{/EasySearch.Each}}
    </ul>
</template>
```

Check out the [searchable leaderboard example](https://github.com/matteodem/easy-search-leaderboard) or have a look at the [current documentation](http://matteodem.github.io/meteor-easy-search/) ([v1 docs](https://github.com/matteodem/meteor-easy-search/tree/gh-pages/_v1docs)) for more information.

