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
## Match items in ranges
Instead of matching particular string, u can choose to match any character in a rang, like this:
```
/[a-z]/ //a, b, c, ... , x, y, z 
/[A-Z]/ //A, B, C, ... , X, Y, Z 
/[a-c]/ //a, b, c 
/[0-9]/ //0, 1, 2, 3, ... , 8, 9
```
These regexes match strings that contain at least one of the characters in those ranges:
```
/[a-z]/.test('a')     // true
/[a-z]/.test('1')     // false
/[a-z]/.test('A')     // false
/[a-c]/.test('d')     // false
/[a-c]/.test('dc')    //true

```
Ranges can be combined
```
/[A-Za-z0-9]/

/[A-Za-z0-9]/.test('a') //true
/[A-Za-z0-9]/.test('1') //true
/[A-Za-z0-9]/.test('A') //true
```

### Matching a range item multiple times
You can check if a string contains one and only one character in a range by using `^` and `$` char:
*Note: Flavio Copes said that "You can check if a string.... by using `-` char:", I don't understand why
```
/^[A-Za-z0-9]$/

/^[A-Za-z0-9]$/.test('A');      //true
/^[A-Za-z0-9]$/.test('Ab');     /false
```
