# Part II: forEach

Before getting started, make sure that you have a JavaScript console open (like <a href="http://www.repl.it/languages/javascript" target="_blank">repl.it</a>), so you can complete these exercises.

## Exercises

1. Refactor the following imperative code to be declarative by using the `forEach()` native array method instead of a `for` loop:

```js
var sumImperative = function(array) {
  var result = 0;
  for (var i = 0; i < array.length; i++) {
    result = result + array[i];
  }
  return result;
};

var sumDeclarative = function(array) {
  // your code here:
  var result = 0;
  array.forEach(num => result += num);
  return result;
};
sumDeclarative([1, 3, 5]);
```

2. Refactor the following imperative code to be declarative by using the `forEach()` native array method instead of a `for` loop:

```js
var maxNumImperative = function(array) {
  var max = array[0];
  for (var i = 0; i < array.length; i++) {
    if (array[i] > max) {
      max = array[i];
    }
  }
  return max;
};

var maxNumDeclarative = function(array) {
  // your code here:
  var max = 0;
  array.forEach(function(num){
    if(num > max) {
      max = num;
    }
  });
  return max;
};
maxNumDeclarative([1, 3, 5]);
```

3. Write a function called `min` that find the smallest number in an array of numbers and returns it.

```js
var min = function(array) {
  // your code here:
  small = array[0];
  array.forEach(function(num) {
    if (num < small) {
      small = num;
    }
  });
  return small;
};

min([100, 54, 73, 8, 12, 3]); // => 3
```

4. Write a function called printNames that takes an array of names and console.logs them:

```js
var printNames = function(names) {
  // your code here:
  names.forEach(name => console.log(name));
};

printNames(['Tom', 'Jerry', 'Arnold', 'Casper']);
```

## More Practice

## Exercises

Try to write all of these exercises using .forEach() rather than `for` or `while` loops.

### Basic Requirements

1. Try the following at a console:

  ```js
  "the quick brown fox jumped over the lazy dog".split(" ");
  "Hello, world!".split("")
  "1,2,3,4,5,6".split(",")
  ```

  What is returned by `split` (You can read more about it
  [here](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String/split)),
  and how does it work?

  Use `split` to write a function `longestWord` that takes a string as an
  argument and returns the longest word.
    ```js
    // your code here:
  var arr = "the quick brown fox jumped over the lazy dog".split(" ");
  var longWord = arr[0];
  function longestWord(arr) {
     arr.forEach(function(word) {
      if(word.length >= longWord.length) {
        longWord = word;
      }
    });
    return longWord;
  };
  longestWord(arr);
    ```

2. Write a function `remove` that accepts an *array* and an *element*, and
   returns an array with all ocurrences of *element* removed.

   ```js
   function remove(array, element) {
     // your code here:
     var newArray = [];
     array.forEach(function(num) {
       if (num != element) {
         newArray.push(num);
       }
     });
     return newArray;
   }
   remove([1, 3, 6, 2, 3], 3); // => [1, 6, 2]
   ```

3. Write a function `evens` that accepts an array as an argument, and returns
   an array consisting of all of the *even* numbers in that array.
   
     ```js
    var even = [];
    var evens = function(array) {
      array.forEach(function(num){
        if (num % 2 == 0) {
          even.push(num);
        }
      });
    return even;
    };
    evens([0, 1, 3, 6, 2, 3, 28, 44]);//=>[ 0, 6, 2, 28, 44 ]
    ```

### Exercises Continued

1. Write a function called `average` that takes an array of numbers as a
   parameter and returns the *average* of those numbers.
   
   ```js
   var average = function(array) {
    var i = 0;
    var sum = 0;
    array.forEach(function(num) {
     sum += num;
      i += 1;
    });
   return sum/i;
   };
   average([1, 3, 6, 2, 3]);//=> 3
   ```

2. Write a function `shortestWord` that works like `longestWord`, but returns
   the *shortest* word instead.
   //your code goes here:
    ```js
    var arr = "the quick brown fox jumped over a lazy dog".split(" ");
    var shortestWord = function(arr) {
    var short = arr[0];
      arr.forEach(function(word) {
        if(word.length <= short.length) {
          short = word;
        }
      });
      return short;
    };
    shortestWord(arr);//=> a
    ```

3. Write a function `countChar` that takes two arguments: any string, and a
   *character* (string of one letter), and returns the number of times that the
   character occurs in the string.

   ```js
    //Your code goes here:
    var arr = "supercalifragilisticexpialidoucious".split("");
    var countChar = function(arr, char) {
    counter = 0;
      arr.forEach(function(el) {
        if(el == char) {
          counter += 1;
        }
      });
      return counter;
    };
    countChar(arr, "i");//=> 7
    ```
4. Write a function `evenLengthWords` that takes an array of *strings* as an
   argument, and returns an array of just the words that have an even length.

   ```js
    //Your code goes here:
    var arr = "the quick brown fox jumped over a lazy dog".split(" ");
    var evenLengthWords = function(arr) {
    evens = [];
      arr.forEach(function(word) {
        if (word.length % 2 == 0) {
          evens.push(word);
        }
      });
      return evens;
    };
    evenLengthWords(arr);//=> [jumped, over, lazy]
    ```
    
### Advanced

1. Read about the `join` method on
   [MDN](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array/join)
   and use it to implement a function that accepts a string as an argument and
   returns that string *reversed*.
   
   ```js
   //Your code goes here:
   var arr = "supercalifragilisticexpialidocious".split("");
   reversed = [];
   var reverse = function(arr) {
      arr.forEach(letter => reversed.unshift(letter));
      return reversed.join("");
   };
   reverse(arr);
   ```

2. Write a function `keep` that "keeps" certain elements in an array. The
   function will need to take *two* arguments, an array, and something else --
   the second argument will be what is used to determine which elements to keep.
  
  ```js
  //Your code goes here:
  var arr = "the quick brown fox jumped over the lazy dog".split(" ");
  var keep = function(arr, arg) {
  newArr = [];
    arr.forEach(function(element) {
      if (arg(element) === true) {
        newArr.push(element);
     }
   });
   return newArr;
  };
  keep(arr, function(element){
  return element.length === 4;
  });
  ```
  
   You should be able to use this function to write `evens`, `evenLengthWords`,
   a hypothetical `odds` function, or `oddLengthWords` *without changing the
   `keep` function*.
   ```js
   //Your code goes here:
  var arr = "the quick brown fox jumped over the lazy dog".split(" ");
  var evenLengthWords = function(arr, arg) {
  newArr = [];
    arr.forEach(function(element) {
      if (arg(element) === true) {
        newArr.push(element);
      }
    });
    return newArr;
  };
  evenLengthWords(arr, function(element){
  return element.length %2 == 0;
  });
  ```
