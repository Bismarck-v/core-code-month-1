# Index
- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)
---

##Monday

**1.You probably know the "like" system from Facebook and other pages. People can "like" blog posts, pictures or other items. We want to create the text that should be displayed next to such an item.
Implement the function which takes an array containing the names of people that like an item. It must return the display text as shown in the examples:**
```
[]                                -->  "no one likes this"
["Peter"]                         -->  "Peter likes this"
["Jacob", "Alex"]                 -->  "Jacob and Alex like this"
["Max", "John", "Mark"]           -->  "Max, John and Mark like this"
["Alex", "Jacob", "Mark", "Max"]  -->  "Alex, Jacob and 2 others like this"
```
```Javascript
var names= ["", "Peter", "Jacob", "Alex", "Max", "John", "Mark"];
function likes (names) {
  var templates = [
    'no one likes this',
    '{name} likes this',
    '{name} and {name} like this',
    '{name}, {name} and {name} like this',
    '{name}, {name} and {n} others like this'
  ];
  var idx = Math.min(names.length, 4);

  return templates[idx].replace(/{name}|{n}/g, function (val) {// 
    return val === "{name}" ? names.shift() : names.length;// 
  });
}
var ilikes= likes(names);
console.log(ilikes);
```

**2. Write a function that takes an integer as input, and returns the number of bits that are equal to one in the binary representation of that number. You can guarantee that input is non-negative.**
**Example: The binary representation of 1234 is 10011010010, so the function should return 5 in this case.**
```Javascript
var countBits = function(n) {
  let num = 0
  
  Array.from(n.toString(2)).forEach(function(bit){
    if (bit == 1) num++;
})
return num;
};
```

3. Code Morse
```Javascript
decodeMorse = function(morseCode){
   return morseCode.split("   ").
           map(s=>s.split(" ")).
           map(s=>s.map(s=>MORSE_CODE[s])).
           map(s=>s.join("")).
           join(" ").trim();
  
}
```

##Tuesday

**1. Your task is to sort a given string. Each word in the string will contain a single number. This number is the position the word should have in the result.
Note: Numbers can be from 1 to 9. So 1 will be the first word (not 0).
If the input string is empty, return an empty string. The words in the input String will only contain valid consecutive numbers.**

Examples
```
"is2 Thi1s T4est 3a"  -->  "Thi1s is2 3a T4est"
"4of Fo1r pe6ople g3ood th5e the2"  -->  "Fo1r the2 g3ood 4of th5e pe6ople"
""  -->  ""
```
```JavaScript
function order(words){
  if(!words){
    return words;
  }
  return words.split(" ").sort(function(a,b){
    return getNumber(a) - getNumber(b);
  }).join(" ");
  }
function getNumber(str){
  return str.match(/\d/)[0];
}
```
