# Tuts about how to using Regular Expression In Javascript

## Key Idea
```
The rule of thumb is that simple regular expressions are simple to read and write, while complex regular expressions can quickly turn into a mess if you don’t deeply grasp the basics.
```

## Create Regex
Using object
```
const regex = new RegExp('hey')
```
or using regex literals
```
const regex = /hey/
```

## Check if string contain Regex
```
const regex = /hey/;

regex.test('hey');             //true
regex.test('blah blah');       //false
regex.test('he');              //false
regex.test('blab hey blahh');  //true
```
