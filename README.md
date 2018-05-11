# Tuts about how to using Regular Expression In Javascript
Thanks to Flavio Copes (https://flaviocopes.com/) for the simple to understand tutorial

## Key Idea
```
The rule of thumb is that simple regular expressions are simple to read and write, while complex regular expressions can quickly turn into a mess if you don’t deeply grasp the basics.
```

## Create Regex
Using object
```
const regex = new RegExp('hello')
```
or using regex literals
```
const regex = /hello/
```

## Check if string contain Regex
```
const regex = /hello/;

regex.test('hello');             //true
regex.test('fuga hoge');         //false
regex.test('he');                //false
regex.test('blab hello blahh');  //true
```
