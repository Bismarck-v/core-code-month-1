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

## Wednesday

**1. Write a function that takes a string of parentheses, and determines if the order of the parentheses is valid. The function should return true if the string is valid, and false if it's invalid.**

Examples
```
"()"              =>  true
")(()))"          =>  false
"("               =>  false
"(())((()())())"  =>  true
```
```Javascript
function validParentheses(parens) {
  let openNum = 0;
  for (let i = 0; i < parens.length; i++){
    if ( parens.charAt(i) == "(" ){
      openNum += 1;
    }else{
      openNum -= 1;
    }
    if ( openNum < 0){
      return false
    }
    }
    if ( openNum === 0){
      return true
    }else{
  return false;
}
}
```

**2. omplete the method/function so that it converts dash/underscore delimited words into camel casing. The first word within the output should be capitalized only if the original word was capitalized (known as Upper Camel Case, also often referred to as Pascal case).**

Examples
```
"the-stealth-warrior" gets converted to "theStealthWarrior"
"The_Stealth_Warrior" gets converted to "TheStealthWarrior"
```
```Javascript
function toCamelCase(str){
  let strArray;
  if (str === ""){
    return "";
  }
  if (str.indexOf("-") !== -1){
    strArray = str.split("-")
  }else{
    strArray = str.split("_")
  }
  let ccString = strArray[0];
  for (let i = 1; i < strArray.length; i++){
    ccString += capitalize(strArray[i]);
  }
  return ccString;
}
let capitalize = (str) =>{
  return str[0].toUpperCase() + str.slice(1);
}
```

**3.Implement the function unique_in_order which takes as argument a sequence and returns a list of items without any elements with the same value next to each other and preserving the original order of elements.**

For example:
```
uniqueInOrder('AAAABBBCCDAABBB') == ['A', 'B', 'C', 'D', 'A', 'B']
uniqueInOrder('ABBCcAD')         == ['A', 'B', 'C', 'c', 'A', 'D']
uniqueInOrder([1,2,2,3,3])       == [1,2,3]
```
```Javascript
var uniqueInOrder=function(iterable){
  let newArr = []
  for (let i = 0; i < iterable.length; i++){
    if(iterable[i] != iterable[i+1]){
      newArr.push(iterable[i])
    }
  }
  return newArr
}
```

## Thursday

**1. In this kata you have to write a method that folds a given array of integers by the middle x-times.
An example says more than thousand words:**
```
Fold 1-times:
[1,2,3,4,5] -> [6,6,3]

A little visualization (NOT for the algorithm but for the idea of folding):

 Step 1         Step 2        Step 3       Step 4       Step5
                     5/           5|         5\          
                    4/            4|          4\      
1 2 3 4 5      1 2 3/         1 2 3|       1 2 3\       6 6 3
----*----      ----*          ----*        ----*        ----*


Fold 2-times:
[1,2,3,4,5] -> [9,6]
```
**As you see, if the count of numbers is odd, the middle number will stay. Otherwise the fold-point is between the middle-numbers, so all numbers would be added in a way.
The array will always contain numbers and will never be null. The parameter runs will always be a positive integer greater than 0 and says how many runs of folding your method has to do.
If an array with one element is folded, it stays as the same array.
The input array should not be modified!
Have fun coding it and please don't forget to vote and rank this kata! :-)
I have created other katas. Have a look if you like coding and challenges.**
```Javascript
function foldArray(array, runs) {
  let counterRuns = 0;
  let arrayPrimary = [...array];
  let result = [];
  while (counterRuns != runs) {
    result = arrayPrimary.map((value, index, arr) => {
      if (index != arr.length - 1) {
        value += arr[arr.length - 1];
      }
      arr.pop();
      return value;
    });
    arrayPrimary = result.filter((num) => num != undefined);
    counterRuns++;
  }
  return result.filter((num) => num != undefined);
}
```

**2. Acknowledgments:
I thank yvonne-liu for the idea and for the example tests :)

Description:
Encrypt this!
You want to create secret messages which can be deciphered by the Decipher this! kata. Here are the conditions:
Your message is a string containing space separated words.
You need to encrypt each word in the message using the following rules:
The first letter must be converted to its ASCII code.
The second letter must be switched with the last letter
Keepin' it simple: There are no special characters in the input.**
Examples:
```
encryptThis("Hello") === "72olle"
encryptThis("good") === "103doo"
encryptThis("hello world") === "104olle 119drlo"
```
```Javascript
function encryptThis(text) {
  let strArr = text.split(' ');
  let output = [];
  
  strArr.forEach(str => {
    if (str.length === 1) {
      output.push(str.charCodeAt(0));
    } 
    else {
      let tempStr = str.split('');
      tempStr[0] = str.charCodeAt(0);
      tempStr[1] = str[str.length - 1];
      tempStr[str.length - 1] = str[1];
      output.push(tempStr.join(''));
    }
  });
  
  return output.join(' ');
}
```
