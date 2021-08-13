---
title: Rejex In Javascript
tags:
  - javascript
published: true
date: '2021-01-06'
---
# Patterns and flags

Regular expressions are patterns that provide a powerful way to search and replace in text.

In JavaScript, they are available via the [RegExp](mdn:js/RegExp) object, as well as being integrated in methods of strings.

## Regular Expressions

A regular expression (also "regexp", or just "reg") consists of a _pattern_ and optional _flags_.

There are two syntaxes that can be used to create a regular expression object.

The "long" syntax:

```js
regexp = new RegExp("pattern", "flags");
```

And the "short" one, using slashes `"/"`:

```js
regexp = /pattern/; // no flags
regexp = /pattern/gim; // with flags g,m and i (to be covered soon)
```

Slashes `pattern:/.../` tell JavaScript that we are creating a regular expression. They play the same role as quotes for strings.

In both cases `regexp` becomes an instance of the built-in `RegExp` class.

The main difference between these two syntaxes is that pattern using slashes `/.../` does not allow for expressions to be inserted (like string template literals with `${...}`). They are fully static.

Slashes are used when we know the regular expression at the code writing time -- and that's the most common situation. While `new RegExp` is more often used when we need to create a regexp "on the fly" from a dynamically generated string. For instance:

```js
let tag = prompt("What tag do you want to find?", "h2");

let regexp = new RegExp(`<${tag}>`); // same as /<h2>/ if answered "h2" in the prompt above
```

## Flags

Regular expressions may have flags that affect the search.

There are only 6 of them in JavaScript:

`pattern:i`
: With this flag the search is case-insensitive: no difference between `A` and `a` (see the example below).

`pattern:g`
: With this flag the search looks for all matches, without it -- only the first match is returned.

`pattern:m`
: Multiline mode (covered in the chapter <info:regexp-multiline-mode>).

`pattern:s`
: Enables "dotall" mode, that allows a dot `pattern:.` to match newline character `\n` (covered in the chapter <info:regexp-character-classes>).

`pattern:u`
: Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter <info:regexp-unicode>.

`pattern:y`
: "Sticky" mode: searching at the exact position in the text (covered in the chapter <info:regexp-sticky>)

```smart header="Colors"
From here on the color scheme is:

- regexp -- `pattern:red`
- string (where we search) -- `subject:blue`
- result -- `match:green`
```

## Searching: str.match

As mentioned previously, regular expressions are integrated with string methods.

The method `str.match(regexp)` finds all matches of `regexp` in the string `str`.

It has 3 working modes:

1. If the regular expression has flag `pattern:g`, it returns an array of all matches:

   ```js run
   let str = "We will, we will rock you";

   alert(str.match(/we/gi)); // We,we (an array of 2 substrings that match)
   ```

   Please note that both `match:We` and `match:we` are found, because flag `pattern:i` makes the regular expression case-insensitive.

2. If there's no such flag it returns only the first match in the form of an array, with the full match at index `0` and some additional details in properties:

   ```js run
   let str = "We will, we will rock you";

   let result = str.match(/we/i); // without flag g

   alert(result[0]); // We (1st match)
   alert(result.length); // 1

   // Details:
   alert(result.index); // 0 (position of the match)
   alert(result.input); // We will, we will rock you (source string)
   ```

   The array may have other indexes, besides `0` if a part of the regular expression is enclosed in parentheses. We'll cover that in the chapter <info:regexp-groups>.

3. And, finally, if there are no matches, `null` is returned (doesn't matter if there's flag `pattern:g` or not).

   This a very important nuance. If there are no matches, we don't receive an empty array, but instead receive `null`. Forgetting about that may lead to errors, e.g.:

   ```js run
   let matches = "JavaScript".match(/HTML/); // = null

   if (!matches.length) {
     // Error: Cannot read property 'length' of null
     alert("Error in the line above");
   }
   ```

   If we'd like the result to always be an array, we can write it this way:

   ```js run
   let matches = "JavaScript".match(/HTML/)*!* || []*/!*;

   if (!matches.length) {
     alert("No matches"); // now it works
   }
   ```

## Replacing: str.replace

The method `str.replace(regexp, replacement)` replaces matches found using `regexp` in string `str` with `replacement` (all matches if there's flag `pattern:g`, otherwise, only the first one).

For instance:

```js run
// no flag g
alert("We will, we will".replace(/we/i, "I")); // I will, we will

// with flag g
alert("We will, we will".replace(/we/gi, "I")); // I will, I will
```

The second argument is the `replacement` string. We can use special character combinations in it to insert fragments of the match:

| Symbols              | Action in the replacement string                                                                                                  |
| -------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| `$&`                 | inserts the whole match                                                                                                           |
| <code>$&#096;</code> | inserts a part of the string before the match                                                                                     |
| `$'`                 | inserts a part of the string after the match                                                                                      |
| `$n`                 | if `n` is a 1-2 digit number, then it inserts the contents of n-th parentheses, more about it in the chapter <info:regexp-groups> |
| `$<name>`            | inserts the contents of the parentheses with the given `name`, more about it in the chapter <info:regexp-groups>                  |
| `$$`                 | inserts character `$`                                                                                                             |

An example with `pattern:$&`:

```js run
alert("I love HTML".replace(/HTML/, "$& and JavaScript")); // I love HTML and JavaScript
```

## Testing: regexp.test

The method `regexp.test(str)` looks for at least one match, if found, returns `true`, otherwise `false`.

```js run
let str = "I love JavaScript";
let regexp = /LOVE/i;

alert(regexp.test(str)); // true
```

Later in this chapter we'll study more regular expressions, walk through more examples, and also meet other methods.

Full information about the methods is given in the article <info:regexp-methods>.

## Summary

- A regular expression consists of a pattern and optional flags: `pattern:g`, `pattern:i`, `pattern:m`, `pattern:u`, `pattern:s`, `pattern:y`.
- Without flags and special symbols (that we'll study later), the search by a regexp is the same as a substring search.
- The method `str.match(regexp)` looks for matches: all of them if there's `pattern:g` flag, otherwise, only the first one.
- The method `str.replace(regexp, replacement)` replaces matches found using `regexp` with `replacement`: all of them if there's `pattern:g` flag, otherwise only the first one.
- The method `regexp.test(str)` returns `true` if there's at least one match, otherwise, it returns `false`.



# Character classes

Consider a practical task -- we have a phone number like `"+7(903)-123-45-67"`, and we need to turn it into pure numbers: `79031234567`.

To do so, we can find and remove anything that's not a number. Character classes can help with that.

A _character class_ is a special notation that matches any symbol from a certain set.

For the start, let's explore the "digit" class. It's written as `pattern:\d` and corresponds to "any single digit".

For instance, let's find the first digit in the phone number:

```js run
let str = "+7(903)-123-45-67";

let regexp = /\d/;

alert(str.match(regexp)); // 7
```

Without the flag `pattern:g`, the regular expression only looks for the first match, that is the first digit `pattern:\d`.

Let's add the `pattern:g` flag to find all digits:

```js run
let str = "+7(903)-123-45-67";

let regexp = /\d/g;

alert(str.match(regexp)); // array of matches: 7,9,0,3,1,2,3,4,5,6,7

// let's make the digits-only phone number of them:
alert(str.match(regexp).join("")); // 79031234567
```

That was a character class for digits. There are other character classes as well.

Most used are:

`pattern:\d` ("d" is from "digit")
: A digit: a character from `0` to `9`.

`pattern:\s` ("s" is from "space")
: A space symbol: includes spaces, tabs `\t`, newlines `\n` and few other rare characters, such as `\v`, `\f` and `\r`.

`pattern:\w` ("w" is from "word")
: A "wordly" character: either a letter of Latin alphabet or a digit or an underscore `_`. Non-Latin letters (like cyrillic or hindi) do not belong to `pattern:\w`.

For instance, `pattern:\d\s\w` means a "digit" followed by a "space character" followed by a "wordly character", such as `match:1 a`.

**A regexp may contain both regular symbols and character classes.**

For instance, `pattern:CSS\d` matches a string `match:CSS` with a digit after it:

```js run
let str = "Is there CSS4?";
let regexp = /CSS\d/;

alert(str.match(regexp)); // CSS4
```

Also we can use many character classes:

```js run
alert("I love HTML5!".match(/\s\w\w\w\w\d/)); // ' HTML5'
```

The match (each regexp character class has the corresponding result character):

![](love-html5-classes.svg)

## Inverse classes

For every character class there exists an "inverse class", denoted with the same letter, but uppercased.

The "inverse" means that it matches all other characters, for instance:

`pattern:\D`
: Non-digit: any character except `pattern:\d`, for instance a letter.

`pattern:\S`
: Non-space: any character except `pattern:\s`, for instance a letter.

`pattern:\W`
: Non-wordly character: anything but `pattern:\w`, e.g a non-latin letter or a space.

In the beginning of the chapter we saw how to make a number-only phone number from a string like `subject:+7(903)-123-45-67`: find all digits and join them.

```js run
let str = "+7(903)-123-45-67";

alert(str.match(/\d/g).join("")); // 79031234567
```

An alternative, shorter way is to find non-digits `pattern:\D` and remove them from the string:

```js run
let str = "+7(903)-123-45-67";

alert(str.replace(/\D/g, "")); // 79031234567
```

## A dot is "any character"

A dot `pattern:.` is a special character class that matches "any character except a newline".

For instance:

```js run
alert("Z".match(/./)); // Z
```

Or in the middle of a regexp:

```js run
let regexp = /CS.4/;

alert("CSS4".match(regexp)); // CSS4
alert("CS-4".match(regexp)); // CS-4
alert("CS 4".match(regexp)); // CS 4 (space is also a character)
```

Please note that a dot means "any character", but not the "absence of a character". There must be a character to match it:

```js run
alert("CS4".match(/CS.4/)); // null, no match because there's no character for the dot
```

### Dot as literally any character with "s" flag

By default, a dot doesn't match the newline character `\n`.

For instance, the regexp `pattern:A.B` matches `match:A`, and then `match:B` with any character between them, except a newline `\n`:

```js run
alert("A\nB".match(/A.B/)); // null (no match)
```

There are many situations when we'd like a dot to mean literally "any character", newline included.

That's what flag `pattern:s` does. If a regexp has it, then a dot `pattern:.` matches literally any character:

```js run
alert("A\nB".match(/A.B/s)); // A\nB (match!)
```

````warn header="Not supported in IE"
The `pattern:s` flag is not supported in IE.

Luckily, there's an alternative, that works everywhere. We can use a regexp like `pattern:[\s\S]` to match "any character" (this pattern will be covered in the article <info:regexp-character-sets-and-ranges>).

```js run
alert( "A\nB".match(/A[\s\S]B/) ); // A\nB (match!)
```

The pattern `pattern:[\s\S]` literally says: "a space character OR not a space character". In other words, "anything". We could use another pair of complementary classes, such as `pattern:[\d\D]`, that doesn't matter. Or even the `pattern:[^]` -- as it means match any character except nothing.

Also we can use this trick if we want both kind of "dots" in the same pattern: the actual dot `pattern:.` behaving the regular way ("not including a newline"), and also a way to match "any character" with `pattern:[\s\S]` or alike.
````

````warn header="Pay attention to spaces"
Usually we pay little attention to spaces. For us strings `subject:1-5` and `subject:1 - 5` are nearly identical.

But if a regexp doesn't take spaces into account, it may fail to work.

Let's try to find digits separated by a hyphen:

```js run
alert( "1 - 5".match(/\d-\d/) ); // null, no match!
```

Let's fix it adding spaces into the regexp `pattern:\d - \d`:

```js run
alert( "1 - 5".match(/\d - \d/) ); // 1 - 5, now it works
// or we can use \s class:
alert( "1 - 5".match(/\d\s-\s\d/) ); // 1 - 5, also works
```

**A space is a character. Equal in importance with any other character.**

We can't add or remove spaces from a regular expression and expect it to work the same.

In other words, in a regular expression all characters matter, spaces too.
````

## Summary

There exist following character classes:

- `pattern:\d` -- digits.
- `pattern:\D` -- non-digits.
- `pattern:\s` -- space symbols, tabs, newlines.
- `pattern:\S` -- all but `pattern:\s`.
- `pattern:\w` -- Latin letters, digits, underscore `'_'`.
- `pattern:\W` -- all but `pattern:\w`.
- `pattern:.` -- any character if with the regexp `'s'` flag, otherwise any except a newline `\n`.

...But that's not all!

Unicode encoding, used by JavaScript for strings, provides many properties for characters, like: which language the letter belongs to (if it's a letter), is it a punctuation sign, etc.

We can search by these properties as well. That requires flag `pattern:u`, covered in the next article.




# Methods of RegExp and String

In this article we'll cover various methods that work with regexps in-depth.

## str.match(regexp)

The method `str.match(regexp)` finds matches for `regexp` in the string `str`.

It has 3 modes:

1. If the `regexp` doesn't have flag `pattern:g`, then it returns the first match as an array with capturing groups and properties `index` (position of the match), `input` (input string, equals `str`):

   ```js run
   let str = "I love JavaScript";

   let result = str.match(/Java(Script)/);

   alert(result[0]); // JavaScript (full match)
   alert(result[1]); // Script (first capturing group)
   alert(result.length); // 2

   // Additional information:
   alert(result.index); // 7 (match position)
   alert(result.input); // I love JavaScript (source string)
   ```

2. If the `regexp` has flag `pattern:g`, then it returns an array of all matches as strings, without capturing groups and other details.

   ```js run
   let str = "I love JavaScript";

   let result = str.match(/Java(Script)/g);

   alert(result[0]); // JavaScript
   alert(result.length); // 1
   ```

3. If there are no matches, no matter if there's flag `pattern:g` or not, `null` is returned.

   That's an important nuance. If there are no matches, we don't get an empty array, but `null`. It's easy to make a mistake forgetting about it, e.g.:

   ```js run
   let str = "I love JavaScript";

   let result = str.match(/HTML/);

   alert(result); // null
   alert(result.length); // Error: Cannot read property 'length' of null
   ```

   If we want the result to be an array, we can write like this:

   ```js
   let result = str.match(regexp) || [];
   ```

## str.matchAll(regexp)

[recent browser="new"]

The method `str.matchAll(regexp)` is a "newer, improved" variant of `str.match`.

It's used mainly to search for all matches with all groups.

There are 3 differences from `match`:

1. It returns an iterable object with matches instead of an array. We can make a regular array from it using `Array.from`.
2. Every match is returned as an array with capturing groups (the same format as `str.match` without flag `pattern:g`).
3. If there are no results, it returns an empty iterable object instead of `null`.

Usage example:

```js run
let str = "<h1>Hello, world!</h1>";
let regexp = /<(.*?)>/g;

let matchAll = str.matchAll(regexp);

alert(matchAll); // [object RegExp String Iterator], not array, but an iterable

matchAll = Array.from(matchAll); // array now

let firstMatch = matchAll[0];
alert(firstMatch[0]); // <h1>
alert(firstMatch[1]); // h1
alert(firstMatch.index); // 0
alert(firstMatch.input); // <h1>Hello, world!</h1>
```

If we use `for..of` to loop over `matchAll` matches, then we don't need `Array.from` any more.

## str.split(regexp|substr, limit)

Splits the string using the regexp (or a substring) as a delimiter.

We can use `split` with strings, like this:

```js run
alert("12-34-56".split("-")); // array of ['12', '34', '56']
```

But we can split by a regular expression, the same way:

```js run
alert("12, 34, 56".split(/,\s*/)); // array of ['12', '34', '56']
```

## str.search(regexp)

The method `str.search(regexp)` returns the position of the first match or `-1` if none found:

```js run
let str = "A drop of ink may make a million think";

alert(str.search(/ink/i)); // 10 (first match position)
```

**The important limitation: `search` only finds the first match.**

If we need positions of further matches, we should use other means, such as finding them all with `str.matchAll(regexp)`.

## str.replace(str|regexp, str|func)

This is a generic method for searching and replacing, one of most useful ones. The swiss army knife for searching and replacing.

We can use it without regexps, to search and replace a substring:

```js run
// replace a dash by a colon
alert("12-34-56".replace("-", ":")); // 12:34-56
```

There's a pitfall though.

**When the first argument of `replace` is a string, it only replaces the first match.**

You can see that in the example above: only the first `"-"` is replaced by `":"`.

To find all hyphens, we need to use not the string `"-"`, but a regexp `pattern:/-/g`, with the obligatory `pattern:g` flag:

```js run
// replace all dashes by a colon
alert( '12-34-56'.replace( *!*/-/g*/!*, ":" ) )  // 12:34:56
```

The second argument is a replacement string. We can use special characters in it:

| Symbols              | Action in the replacement string                                                                                   |
| -------------------- | ------------------------------------------------------------------------------------------------------------------ |
| `$&`                 | inserts the whole match                                                                                            |
| <code>$&#096;</code> | inserts a part of the string before the match                                                                      |
| `$'`                 | inserts a part of the string after the match                                                                       |
| `$n`                 | if `n` is a 1-2 digit number, inserts the contents of n-th capturing group, for details see [](info:regexp-groups) |
| `$<name>`            | inserts the contents of the parentheses with the given `name`, for details see [](info:regexp-groups)              |
| `$$`                 | inserts character `$`                                                                                              |

For instance:

```js run
let str = "John Smith";

// swap first and last name
alert(str.replace(/(john) (smith)/i, "$2, $1")); // Smith, John
```

**For situations that require "smart" replacements, the second argument can be a function.**

It will be called for each match, and the returned value will be inserted as a replacement.

The function is called with arguments `func(match, p1, p2, ..., pn, offset, input, groups)`:

1. `match` -- the match,
2. `p1, p2, ..., pn` -- contents of capturing groups (if there are any),
3. `offset` -- position of the match,
4. `input` -- the source string,
5. `groups` -- an object with named groups.

If there are no parentheses in the regexp, then there are only 3 arguments: `func(str, offset, input)`.

For example, let's uppercase all matches:

```js run
let str = "html and css";

let result = str.replace(/html|css/gi, (str) => str.toUpperCase());

alert(result); // HTML and CSS
```

Replace each match by its position in the string:

```js run
alert("Ho-Ho-ho".replace(/ho/gi, (match, offset) => offset)); // 0-3-6
```

In the example below there are two parentheses, so the replacement function is called with 5 arguments: the first is the full match, then 2 parentheses, and after it (not used in the example) the match position and the source string:

```js run
let str = "John Smith";

let result = str.replace(
  /(\w+) (\w+)/,
  (match, name, surname) => `${surname}, ${name}`
);

alert(result); // Smith, John
```

If there are many groups, it's convenient to use rest parameters to access them:

```js run
let str = "John Smith";

let result = str.replace(
  /(\w+) (\w+)/,
  (...match) => `${match[2]}, ${match[1]}`
);

alert(result); // Smith, John
```

Or, if we're using named groups, then `groups` object with them is always the last, so we can obtain it like this:

```js run
let str = "John Smith";

let result = str.replace(/(?<name>\w+) (?<surname>\w+)/, (...match) => {
  let groups = match.pop();

  return `${groups.surname}, ${groups.name}`;
});

alert(result); // Smith, John
```

Using a function gives us the ultimate replacement power, because it gets all the information about the match, has access to outer variables and can do everything.

## str.replaceAll(str|regexp, str|func)

This method is essentially the same as `str.replace`, with two major differences:

1. If the first argument is a string, it replaces _all occurences_ of the string, while `replace` replaces only the _first occurence_.
2. If the first argument is a regular expression without the `g` flag, there'll be an error. With `g` flag, it works the same as `replace`.

The main use case for `replaceAll` is replacing all occurences of a string.

Like this:

```js run
// replace all dashes by a colon
alert("12-34-56".replaceAll("-", ":")); // 12:34:56
```

## regexp.exec(str)

The `regexp.exec(str)` method returns a match for `regexp` in the string `str`. Unlike previous methods, it's called on a regexp, not on a string.

It behaves differently depending on whether the regexp has flag `pattern:g`.

If there's no `pattern:g`, then `regexp.exec(str)` returns the first match exactly as `str.match(regexp)`. This behavior doesn't bring anything new.

But if there's flag `pattern:g`, then:

- A call to `regexp.exec(str)` returns the first match and saves the position immediately after it in the property `regexp.lastIndex`.
- The next such call starts the search from position `regexp.lastIndex`, returns the next match and saves the position after it in `regexp.lastIndex`.
- ...And so on.
- If there are no matches, `regexp.exec` returns `null` and resets `regexp.lastIndex` to `0`.

So, repeated calls return all matches one after another, using property `regexp.lastIndex` to keep track of the current search position.

In the past, before the method `str.matchAll` was added to JavaScript, calls of `regexp.exec` were used in the loop to get all matches with groups:

```js run
let str = "More about JavaScript at https://javascript.info";
let regexp = /javascript/gi;

let result;

while ((result = regexp.exec(str))) {
  alert(`Found ${result[0]} at position ${result.index}`);
  // Found JavaScript at position 11, then
  // Found javascript at position 33
}
```

This works now as well, although for newer browsers `str.matchAll` is usually more convenient.

**We can use `regexp.exec` to search from a given position by manually setting `lastIndex`.**

For instance:

```js run
let str = "Hello, world!";

let regexp = /\w+/g; // without flag "g", lastIndex property is ignored
regexp.lastIndex = 5; // search from 5th position (from the comma)

alert(regexp.exec(str)); // world
```

If the regexp has flag `pattern:y`, then the search will be performed exactly at the position `regexp.lastIndex`, not any further.

Let's replace flag `pattern:g` with `pattern:y` in the example above. There will be no matches, as there's no word at position `5`:

```js run
let str = "Hello, world!";

let regexp = /\w+/y;
regexp.lastIndex = 5; // search exactly at position 5

alert(regexp.exec(str)); // null
```

That's convenient for situations when we need to "read" something from the string by a regexp at the exact position, not somewhere further.

## regexp.test(str)

The method `regexp.test(str)` looks for a match and returns `true/false` whether it exists.

For instance:

```js run
let str = "I love JavaScript";

// these two tests do the same
alert( *!*/love/i*/!*.test(str) ); // true
alert( str.search(*!*/love/i*/!*) != -1 ); // true
```

An example with the negative answer:

```js run
let str = "Bla-bla-bla";

alert( *!*/love/i*/!*.test(str) ); // false
alert( str.search(*!*/love/i*/!*) != -1 ); // false
```

If the regexp has flag `pattern:g`, then `regexp.test` looks from `regexp.lastIndex` property and updates this property, just like `regexp.exec`.

So we can use it to search from a given position:

```js run
let regexp = /love/gi;

let str = "I love JavaScript";

// start the search from position 10:
regexp.lastIndex = 10;
alert(regexp.test(str)); // false (no match)
```

````warn header="Same global regexp tested repeatedly on different sources may fail"
If we apply the same global regexp to different inputs, it may lead to wrong result, because `regexp.test` call advances `regexp.lastIndex` property, so the search in another string may start from non-zero position.

For instance, here we call `regexp.test` twice on the same text, and the second time fails:

```js run
let regexp = /javascript/g;  // (regexp just created: regexp.lastIndex=0)

alert( regexp.test("javascript") ); // true (regexp.lastIndex=10 now)
alert( regexp.test("javascript") ); // false
```

That's exactly because `regexp.lastIndex` is non-zero in the second test.

To work around that, we can set `regexp.lastIndex = 0` before each search. Or instead of calling methods on regexp, use string methods `str.match/search/...`, they don't use `lastIndex`.
````
