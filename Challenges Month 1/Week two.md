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
