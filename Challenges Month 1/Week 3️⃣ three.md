# Index
- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)
---

## Monday

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

**3. Code Morse**
```Javascript
decodeMorse = function(morseCode){
   return morseCode.split("   ").
           map(s=>s.split(" ")).
           map(s=>s.map(s=>MORSE_CODE[s])).
           map(s=>s.join("")).
           join(" ").trim();
  
}
```

## Tuesday

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

**2.Count the number of Duplicates**
**Write a function that will return the count of distinct case-insensitive alphabetic characters and numeric digits that occur more than once in the input string. The input string can be assumed to contain only alphabets (both uppercase and lowercase) and numeric digits.**

Example
``
"abcde" -> 0 # no characters repeats more than once
"aabbcde" -> 2 # 'a' and 'b'
"aabBcde" -> 2 # 'a' occurs twice and 'b' twice (`b` and `B`)
"indivisibility" -> 1 # 'i' occurs six times
"Indivisibilities" -> 2 # 'i' occurs seven times and 's' occurs twice
"aA11" -> 2 # 'a' and '1'
"ABBA" -> 2 # 'A' and 'B' each occur twice
``
```Javascript
function duplicateCount(text){
let count = 0
let obj = {}

for (let i of text){
  i = i.toLowerCase()
  if (!obj[i]){
    obj[i] = 1
  }else{
    obj[i]++
  }
}
  for (let i in obj){
    if(obj[i] > 1){
      count++
    }
  }
  return count
}
```

**3.Move the first letter of each word to the end of it, then add "ay" to the end of the word. Leave punctuation marks untouched.**

Examples
```
pigIt('Pig latin is cool'); // igPay atinlay siay oolcay
pigIt('Hello world !');     // elloHay orldway !
```
```Javascript
function pigIt(str){
  let newArr = [],
  strArr = str.split(" ")
  strArr.forEach(x => {
    let wordArr = x.split("")
    wordArr.push(wordArr[0], "ay"), wordArr.shift()
    if (x === "!" || x === "?" || x === "."){
      newArr.push(x)
    }else{
      newArr.push(wordArr.join(""))
    }
  })
  return newArr.join(" ")
}
```
