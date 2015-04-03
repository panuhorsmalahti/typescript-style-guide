# TypeScript style guide

This guide tries to optimize for readability and maintainability over performance. It includes style conventions and some TypeScript best practices.

General
-------

Use [TSLint](https://www.npmjs.com/package/tslint) in your build process to enforce the style.

Types
-----

Enable noImplicitAny option the compiler. Use types instead of the any type. Use type inference freely. Add type information when the inference is not clear.

```
// myDocument type is not obvious to the reader
getFromDatabase.done((myDocument: DocumentType) => {
    response(myDocument);
});

// Type of streetName is clear
streetNames.forEach(streetName => {
    console.log(streetName);
});
```

Formatting
----------

Indent with 4 spaces. Always use curly braces and add semicolons. Add a new line for each property in an object. Use [camelCase](http://en.wikipedia.org/wiki/CamelCase) for variables, PascalCase for classes and constructor functions.

```
var myObject = {
    foo: bar
};
```


Comments
--------

Strike a balance between commenting too much and attempting to write "self-documenting" code. Most comments should explain why instead of what, but sometimes it's necessary to explain what with comments. Leave a space before the comment text and start with a capital letter unless the first word is a variable. Use [JSDoc](http://usejsdoc.org/) for documenting all named functions.

Control structures
------------------

Prefer functional style .forEach, .map, .filter etc. over for/while loops whenever possible. If for/while is required for performance reasons leave a comment stating so.

```
// Authorization is required since commands include all commands.
commands.filter(authorizedCommand).forEach(executeCommand);
```

Functions
---------

Use the far-arrow syntax over the function keyword.
