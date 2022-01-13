#core-code-month-1
Core Code bootcamp

<h4 class=”text-center”>Week challenges</h4>
#Tuesday

**1. I have finished watching the video about the complication.**

---
**2. Java language is compiled or interpreted?**

Java is an interpreted language

---
**3. Create an algorithm to calculate the equivalent of your local currencty to USD**

1. Find the price of the dollar relative to the local currency.
2. Enter the value of the local currency (Córdobas) and multiply it by the dollar value, in my case it would be C$ 30*0.028USD = C$ 0.85.
```python
Cordobas = int(input("Enter the amount in cordobas: "))
USD = 0.028
c = Cordobas*USD
print("The equivalent amount of cordobas to dollars is: ",c)
```
---
**4. Read about Pseudocode here, you can also find some examples here. Completed**

---
**5. Why pseudocode is helpfull?**

Because it allows you to plan instructions that follow a logical pattern without including technical details, it also helps to explain exactly what each line of a computer program should do.

---
**6. Create a pseudocode to calculate the aproximated age of a user base on the year they born, (you can define a variable with the actual year if you need it, like for example i could define Y <-- 2022)**
1. Create a variable that contains the current year.
```python
Newyear = 2022
```
2. Create another variable that asks for the year of birth.
```python
BornYear= int(input("Enter your year of birth: "))
```
3. Create a last variable, where the previous variables will be subtracted (YearNew-BornYear).
```python
age = Newyear - BornYear
```
4. Print the result on the screen age
```python
print("You are", age ,"years old")
```

 ---
 **7. Read about flowcharts here. Completed**
 
 ---
 **8. Why are flowcharts important to us as developers?**

Because they facilitate the way to visually represent the flow of data through an information processing system, in this we make an analysis of the processes or procedures that we require to carry out a program or an objective

---
**9. Search about High-level languages and Low-level languages, you can start with this [video](https://www.youtube.com/watch?v=1vRPOp5p-qs&ab_channel=EliasTheProfe "Comienza a aprender"). Completed**
