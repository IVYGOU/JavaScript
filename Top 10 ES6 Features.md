**Reference:** https://webapplog.com/es6/

1. Default Parameters in ES6
---
In ES6, we can put the default values right in the signature of the functions:
```javascript
var link = function(height = 50, color = 'red', url = 'http://azat.co') {
  ...
}
```

2. Template Literals in ES6
---
In ES6 we can use a new syntax ${NAME}:
```javascript
var name = `Your name is ${first} ${last}.`
var url = `http://localhost:3000/api/messages/${id}`
```

3. Multi-line Strings in ES6
---
While in ES6, simply utilize the backticks:
```javscript
var roadPoem = `Then took the other, as just as fair,
    And having perhaps the better claim
    Because it was grassy and wanted wear,
    Though as for that the passing there
    Had worn them really about the same,`

var fourAgreements = `You have the right to be you.
    You can only be you when you do your best.`
```
