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
