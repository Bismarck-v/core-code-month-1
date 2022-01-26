# Index

- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)

---
## Monday

1. Follow the github course, you can find it [here](./../../../recommended). Completed
2. Watch [this](https://www.youtube.com/watch?v=A37-3lflh8I) video. Completed
3. Read [this](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/Math). Completed
4. Create an account in [Codewars](https://www.codewars.com/dashboard). completed
[User](https://www.codewars.com/users/Bismarck-v/)

## Thuesday

**0. Watch [this](https://www.youtube.com/watch?v=cEBkvm0-rg0) video. Completed**

**1. This code does not execute properly. Try to figure out why.**
``` Javascript
function multiply(a, b){
 let c = a * b;
 return c;
}
console.log(multiply(3,5));
```

**2. You'll be given a string, and have to return the sum of all characters as an int. The function should be able to handle all ASCII characters.**
```Javascript
function uniTotal(string) {
  return Array.prototype.reduce.call(string, (a, c) => a + c.charCodeAt(0), 0);
}
```

**3. Write a function get_char() / getChar() which takes a number and returns the corresponding ASCII char for that value.**
```Javascript
function getChar(c){
  return String.fromCharCode(c);
}
```

**4. Implement a function that adds two numbers together and returns their sum in binary. The conversion can be done before, or after the addition.**
```Javascript
function addBinary(a,b) {
 let add = a + b;
  return add.toString(2);
}
```

**5. Create a function finalGrade, which calculates the final grade of a student depending on two parameters: a grade for the exam and a number of completed projects. This function should take two arguments: exam - grade for exam (from 0 to 100); projects - number of completed projects (from 0 and above); This function should return a number (final grade). There are four types of final grades:**

- 100, if a grade for the exam is more than 90 or if a number of completed projects more than 10.
- 90, if a grade for the exam is more than 75 and if a number of completed projects is minimum 5.
- 75, if a grade for the exam is more than 50 and if a number of completed projects is minimum 2.
0, in other cases
```Javascript
function finalGrade (exam, projects) {
   let finalGrade = 0;
    
     if(exam == 0){
         if(projects > 10){
             finalGrade = 100;
         }
     }else if(exam > 90 || projects > 10 ){
         finalGrade = 100;
     }else if(exam > 75 && projects >= 5){
         finalGrade = 90;
     }else if(exam > 50 && projects >= 2){
         finalGrade = 75;
     }
  return finalGrade;
}
```
---

## Wednesday

**1. The purpose of this kata is to work out just how many bottles of duty free whiskey you would have to buy such that the saving over the normal high street price would effectively cover the cost of your holiday. You will be given the high street price (normPrice), the duty free discount (discount) and the cost of the holiday.
For example, if a bottle cost £10 normally and the discount in duty free was 10%, you would save £1 per bottle. If your holiday cost £500, the answer you should return would be 500. All inputs will be integers. Please return an integer. Round down.**
```Javascript
function dutyFree(normPrice, discount, hol){
  return Math.floor( hol / (normPrice * (discount / 100 )));
}
```
**2. Your function takes two arguments:
current father's age (years)
current age of his son (years)
Сalculate how many years ago the father was twice as old as his son (or in how many years he will be twice as old)**
```Javascript
function twiceAsOld(dadYearsOld, sonYearsOld) {
  return Math.abs((sonYearsOld *2) - dadYearsOld ); 
}
```

**3. Your task is to write a function called valid_spacing() or validSpacing() which checks if a string has valid spacing. The function should return either True or False.
For this kata, the definition of valid spacing is one space between words, and no leading or trailing spaces. Below are some examples of what the function should return.**
```Javascript
function validSpacing(s) {
  return s.trim() == s && !s.includes("  ");
}
```

**4. Given a string of digits, you should replace any digit below 5 with '0' and any digit 5 and above with '1'. Return the resulting string.**
```javascript
function fakeBin(x){
let fakebin = "";
  for(let i = 0; i < x.length; i++){
    fakebin += (Number(x[i]) < 5) ? "0" : "1";
  }
  return fakebin;
}
```

## Thursday

**1. Remove all exclamation marks from the end of sentence.**
```Javascript
function remove (string) {  
  return string.replace (/!+$/,'');
}
```

**2. Create a function called shortcut to remove the lowercase vowels (a, e, i, o, u ) in a given string.**
```Javascript
function shortcut(string){
  return string.replace(/[a,e,i,o,u]/g, '')
  }
  ```
**3. Let's play! You have to return which player won! In case of a draw return Draw!.**
```Javascript
const rps = (p1, p2) => {
  const options = ['scissors', 'paper', 'rock'];
  let player1 = options.indexOf(p1);
  let player2 = options.indexOf(p2);
  let result;
    if(player1 == player2) return 'Draw!';
    if(player1 == 0 && player2 == 1) result = 1;
    if(player1 == 0 && player2 == 2) result = 2;
    if(player1 == 2 && player2 == 0) result = 1;
    if(player1 == 2 && player2 == 1) result = 2;
    if(player1 == 1 && player2 == 0) result = 2;
    if(player1 == 1 && player2 == 2) result = 1;
  return `Player ${result} won!`;
};
```

**4. Write a function, persistence, that takes in a positive parameter num and returns its multiplicative persistence, which is the number of times you must multiply the digits in num until you reach a single digit.**

**For example (Input --> Output):**
```
39 --> 3 (because 3*9 = 27, 2*7 = 14, 1*4 = 4 and 4 has only one digit)
999 --> 4 (because 9*9*9 = 729, 7*2*9 = 126, 1*2*6 = 12, and finally 1*2 = 2)
4 --> 0 (because 4 is already a one-digit number)
```

```Javascript
function persistence(num, count) {
  count = count || 0; 
  let numstr = num.toString(); 
  
  if (numstr.length === 1) {
    return count
  } 
  let new_num = numstr.split('').reduce((acc, val) => {
    return acc * val
  }, 1)
  return persistence(new_num, count + 1) 
}
```
