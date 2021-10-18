# My notes on the "Grokking Algorithms" book

## Chapter 4

### Land problem

![Land problem](images/land_problem.jpg?raw=true "Land problem")

Solution on JavaScript (ES6 syntax):

```js
// Recursive search for the greatest common divisor
const findGCD = (num1, num2) => {
	const getGCD = (bigger, smaller) => bigger % smaller === 0
		? smaller
		: getGCD(smaller, bigger % smaller);

	return num1 > num2
		? getGCD(num1, num2)
		: getGCD(num2, num1)
};

// Print the answer to the problem
console.log(findGCD(1680, 640));
```
