# Tuts about how to using Regular Expression In Javascript
Thanks to Flavio Copes (https://flaviocopes.com/) for the simple to understand tutorial

## Key Idea
```
The rule of thumb is that **simple regular expressions are simple to read and write**,
while **complex regular expressions can quickly turn into a mess** if you don’t deeply grasp the basics.
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
## Anchoring
```
/hello/
```
matches `hello` wherever it was put inside the string
If u wanna match strings that **start** with `halo` , just use the `^` operator:
```
/^halo/.test('Remember those walls I built');        //false
/^halo/.test('I can feel your halo (halo) halo');    //false
/^halo/.test('Halo (hello) from the outside');       //true  
```
If u wanna match strings that **end** with `halo`, just use `$` operator:
```
/halo$/.test('halo');                                //true
/halo$/.test('halo from the outside');               //false
/halo$/.test('haaalllloooo');                        //false
/halo$/.test('Baby, I can feel your halo');          //true
/halo$/.test('Pray it won't fade away');             //true
```
Combine those, we have regex to matching exactly string `halo`:
```
/^halo$/.test('halo')   //true
```
