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
console.log(findGCD(1680, 640)); // 80
```

### Exercise 4.1

Write out the code for the sum function that recursively sums all the elements of the array.

Solution on JavaScript (ES6 syntax):

```js
// Recursive summation of array elements
const sum = (arr) => arr.length === 1
	? arr.shift()
	: arr.shift() + sum(arr);

// Print the sum of the array
const arr = [3, 2, 6, 9];
console.log(sum(arr)); // 20
```
### Exercise 4.2

Write a recursive function to count the number of elements in a array.

Solution on JavaScript (ES6 syntax):

```js
// Recursively counting the number of elements in an array
// Warning: the function assumes that the array will not contain undefined values.
const getElementsCount = (arr) => {
	return arr[0] === undefined
		? 0
		: arr.shift()*0 + 1 + getElementsCount(arr);
};

// Print the count of elements in an array
const arr = [2, 7, 47, 3, 99];
console.log(getElementsCount(arr)); // 5

// Will print 3, see line 2 for the reason
const invalidArr = [2, 7, 47, undefined, 3, 99];
console.log(getElementsCount(invalidArr)); // 3
```

### Exercise 4.3

Find the maximum number in a array.

Solution on JavaScript (ES6 syntax):

```js
// Recursively find the maximum number in a array
const getMax = (arr) => {
	if (arr.length === 2) {
		return arr[0] > arr[1] ? arr[0] : arr[1];
	}
	const tempMax = getMax(arr.slice(1));
	return arr[0] > tempMax ? arr[0] : tempMax;
};

// Print the maximum number in a array
const arr = [5, 2, 1, 18, 9];
console.log(getMax(arr)); // 18
```
