# Part IV: filter

Before getting started, make sure that you have a JavaScript console open (like <a href="http://www.repl.it/languages/javascript" target="_blank">repl.it</a>), so you can complete these exercises.

## Exercises

1. Write a function that takes an array of numbers and returns an array of all numbers less than 10:

```js
var lessThanTen = function(numbers) {
  // your code here:
  var filteredNum = numbers.filter(num => num < 10);
  return filteredNum;
};

lessThanTen([1, 5, 12, 18, 94, 3, 16]); // => [1, 5, 3]
```

2. Write a function that takes an array of numbers and returns an array of just the even numbers:

```js
var onlyEvens = function(numbers) {
  // your code here:
  var filterEvens = numbers.filter(num => num %2 === 0);
  return filterEvens;
};

onlyEvens([25, 16, 12, 99, 8, 37]); // => [16, 12, 8]
```

3. Write a function that takes an array of strings and returns an array of just the words that have an odd number of characters:

```js
var onlyOddWords = function(words) {
  // your code here:
  var filterOdd = words.filter(function(word){
    if(word.length %2 != 0){
      return word;
    }
  });
  return filterOdd;
};

onlyOddWords(['hello', 'my', 'name', 'is', 'alexa']); // => ['hello', 'alexa']
```

4. Write a function that takes an array of words and returns an array of just the words that are pluralized (end with 's'):

```js
var onlyPlural = function(words) {
  // your code here:
  var pluralized = words.filter(function(word){
    var arr = word.split("");
    if(arr.pop() == "s"){
      return word;
    }
  });
  return pluralized;
};

onlyPlural(['dogs', 'cat', 'humans', 'kyle']); // => ['dogs', 'humans']
```

5. Write a function that takes an array of characters and returns an array of just the characters that are superheroes:
```js
var characters = [
  { character: 'Superman', hero: true },
  { character: 'Sinestro', hero: false },
  { character: 'Wonder Woman', hero: true },
  { character: 'Lex Luthor', hero: false },
  { character: 'Green Lantern', hero: true }
]

var isHero = function(chars) {
  // your code here:
  var arr = [];
  var hero = chars.filter(function(char){
    if(char.hero){
      arr.push(char.character);
    }
  });
  return arr;
};
isHero(characters);
```

#### More Practice

Filter is used to find certain items in a data set. Take a look at the array of spell objects in spell.js (in this folder). Using that as your input data set:

1. Write a function that returns a new array of spells whose level is no higher than 1:

```js
var lowLevelSpells = function(spells) {
  // your code here:
  var lowLevel = spells.filter(spell => spell.level <= 1);
  return lowLevel;
};

lowLevelSpells(spells);
```

2. Write a function that returns a new array of spells that have `"M"` as one of their components:

```js
var componentMSpells = function(spells) {
  // your code here:
  var component = spells.filter(function(spell){
    var check = spell.components.filter(comp => comp == "M"); 
    if(check == "M"){
      return true;
    }
  });
  return component;
};

componentMSpells(spells);
```

3. Write a function that returns a new array of spells that can be used by the 'Paladin' class:

```js
var paladinSpells = function(spells) {
  // your code here:
  var component = spells.filter(function(spell){
    var check = spell.classes.filter(comp => comp.name == "Paladin"); 
    if(check[0] !== undefined){
      return true;
    }
  });
  return component;
};

paladinSpells(spells);
```

4. Write a function that returns a new array of spells that can be cast instantaneously:

```js
var instantSpells = function(spells) {
  // your code here:
  var component = spells.filter(spell => spell.duration == "Instantaneous");
  return component;
};

instantSpells(spells);
```
