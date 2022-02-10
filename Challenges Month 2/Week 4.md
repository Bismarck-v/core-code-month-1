# Index
- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)
---

## Monday

**1. Check [this](https://www.youtube.com/watch?v=sXQxhojSdZM) video. Completed**

**2. Follow [this](https://www.youtube.com/watch?v=909NfO1St0A) video. Completed**

**3. Follow [this](https://dev.to/codebubb/javascript-regex-exercises-01-5078) guide. Completed**

**4. Check [this](https://www.youtube.com/watch?v=RvYYCGs45L4) video. Completed**

**5. Follow [this](https://www.youtube.com/watch?v=DHvZLI7Db8E) video. Completed**

**6. Check [this](https://www.youtube.com/watch?v=rKK1q7nFt7M) video. Completed**

---

## Tuesday

**1. [This](https://www.typescriptlang.org/docs/handbook/intro.html) link is nice to have and read. Completed**

**2. [Typescript object type](https://typescript-exercises.github.io/#exercise=1). Completed**

**3. Read [this](https://blog.logrocket.com/types-vs-interfaces-in-typescript/). Completed**

**4. [Typescript union types](https://typescript-exercises.github.io/#exercise=2). Completed**

**5. [Typescript in operator](https://typescript-exercises.github.io/#exercise=3). Completed**

**6. Given an array of integers, find the one that appears an odd number of times. Completed**
**There will always be only one integer that appears an odd number of times.. Completed**
Examples
```
[7] should return 7, because it occurs 1 time (which is odd).
[0] should return 0, because it occurs 1 time (which is odd).
[1,1,2] should return 2, because it occurs 1 time (which is odd).
[0,1,0,1,0] should return 0, because it occurs 3 times (which is odd).
[1,2,2,3,3,3,4,3,3,3,2,2,1] should return 4, because it appears 1 time (which is odd).
```
```Javascript
function findOdd(A) {
  let odd = {};
  A.forEach(elemento => odd[elemento] = odd[elemento] + 1 || 1)
  console.log(odd)
  const num = Object.keys(odd).filter(key => odd[key] %2 === 1)
  console.log(num)
  return Number(num)
}
```

**7.Write a function that takes in a string of one or more words, and returns the same string, but with all five or more letter words reversed (Just like the name of this Kata). Strings passed in will consist of only letters and spaces. Spaces will be included only when more than one word is present.**

Examples:```spinWords( "Hey fellow warriors" ) => returns "Hey wollef sroirraw" spinWords( "This is a test") => returns "This is a test" spinWords( "This is another test" )=> returns "This is rehtona test"```

```Javascript
function spinWords(words){
   const array = words.split(' ');
   let result = '';
   array.map((str, i) => {
    if (str.length >= 5){
      array[i] = str.split('').reverse().join('');
    } else {
      array[i] = str;
    }
  result = array.join(' ');
  });
return result;
}
```
---

## Wednesday

**1.Your goal in this kata is to implement a difference function, which subtracts one list from another and returns the result.**

**It should remove all values from list a, which are present in list b keeping their order.**
```arrayDiff([1,2],[1]) == [2]```
**If a value is present in b, all of its occurrences must be removed from the other:**
```arrayDiff([1,2,2,2,3],[2]) == [1,3]```
```Javascript
function arrayDiff(array1, array2) {
if(array1.length === 0){return []}
if(array2.length === 0){return array1}
let returnArray = [];
array1.forEach(function included(element){
if(!array2.includes(element)){returnArray.push(element)}
})
return returnArray;
}
```
