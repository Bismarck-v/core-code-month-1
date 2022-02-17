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
