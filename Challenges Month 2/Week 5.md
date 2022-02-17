# Index
- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)
---

## Monday

**1. Read [this](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html) from `The primitives: string, number and boolean` to `Differences Between Type Aliases and Interfaces` section. Completed**

**2. Complete the square sum function so that it squares each number passed into it and then sums the results together.
For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.**
```Typescript
export function squareSum(numbers: number[]): number {
    let sum = 0
    for(const num of numbers) {
        sum += num * num
    }
    return sum
}
```

**3. Growth of a Population**
```Typescript
export class G964 {

    public static nbYear = (p0, percent, aug, p) => {
     let sum = p0, i = 0
     while (sum < p){
       sum += sum *(percent / 100) + aug
       i++
     }
      return i
    }
}
```

**4. Mumbling**
```Typescript
export function accum(s: string): string {
  const result = []
  const lowerStr = s.toLowerCase()

  for(let i = 0; i < lowerStr.length; i++) {
    let str = lowerStr[i].toUpperCase()
    for(let j = 0; j < i; j++) {
      str += lowerStr[i]
    }
    result.push(str)
  }

  return result.join("-")
}
```

**5. A wolf in sheep's clothing**
```Typescript
export function warnTheSheep(queue: string[]): string {
   if (queue[queue.length -1] === 'wolf') {
    return 'Pls go away and stop eating my sheep';
    } else {
     let index = queue.findIndex( (x) => x == 'wolf' );
     return `Oi! Sheep number ${queue.length - index - 1}! You are about to be eaten by a wolf!`;
    }
}
```

---

## Tuesday

**1. A Rule of Divisibility by 13**
```Typescript
export function thirt(n: number): number {
  let res : number = n, last : number = -1, tenmod : number[] = [1, 10, 9, 12, 3, 4];
  while(last != res){
    last = res;
    let temp : number = 0, i = 0;
    while(res){
      temp += (res % 10) * tenmod[i];
      res =  Math.floor(res / 10);
      i = (i + 1) % 6;
    }
    res = temp;
  }
  return res;
}
```
