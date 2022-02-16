# Index
- [Monday](#monday)
- [Tuesday](#tuesday)
- [Wednesday](#wednesday)
- [Thursday](#thursday)
---

## Monday

**1. Read [this](https://www.typescriptlang.org/docs/handbook/2/everyday-types.html) from `The primitives: string, number and boolean` to `Differences Between Type Aliases and Interfaces` section. Completed**
**2.Complete the square sum function so that it squares each number passed into it and then sums the results together.
For example, for [1, 2, 2] it should return 9 because 1^2 + 2^2 + 2^2 = 9.**
```Javascript
export function squareSum(numbers: number[]): number {
    let sum = 0
    for(const num of numbers) {
        sum += num * num
    }
    return sum
}
```