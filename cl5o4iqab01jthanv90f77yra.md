## JavaScript Array Methods: how to use map and reduce

Methods are property names that we can dole out to capabilities. They can be summoned whenever by simply utilizing the name to execute a capability. Cluster protests likewise have techniques and properties that permit us to alter or inquire them onto the article.

In JavaScript, cluster strategies make it simple to oversee and sort out information in a helpful manner. Today, we will plunge into two famous exhibit strategies: map() and reduce(). These strategies give a changed form of an exhibit and make clusters significantly more helpful.

## JavaScript arrays refresher

While making variables in JavaScript, getting to a scope of values can be precarious. Essentially, making objects expects you to make key names for every one of the information, which can prompt mess. Clusters are the arrangement. This information structure oversees requested information in one connection point.

Clusters are an assortment of individual qualities isolated by a comma, each with its own file/area. Exhibits are objects with strategies and properties utilized for overseeing information things in an organized style.

They are list-like information structures that gather information, making them available through mathematical files.

![Screenshot 2022-07-16 at 9.59.36 PM.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1657989000578/b_BEVunqc.png align="left")


In JavaScript, arrays are easy to declare. Below, we create an array of fruit types and store them in an orderly fashion.


```
var fruit = [
  "Orange",
  "Apple",
  "Banana"
];
``` 

Arrays in JavaScript have special features that make them particularly useful, including:

- They are dynamic
- They can be sparse or dense
- They are mutable
- They have methods and properties to make organization convenient

## What are array methods?

Array objects have methods and properties that allow us to modify or query them onto an object. These make it much easier to manage, access and organize data. This way, we don’t have to create custom objects.

The property of an array is an attribute of that array, such as length or memory size. They are usually static values that can be used to change a particular quality of the object. prototype and length are common properties.

Methods of an array are actions that we can apply to an array. These are similar to properties but are of the type function. push() and pop() are common array methods that allow us to add or remove elements.

> Refresher: Functions are a set of instructions that carry out a task. They allow us to reuse code anywhere in the program.

Array methods help make your programs far more convenient and useful. Next, we’ll look at two unique JavaScript array methods that make arrays even more convenient: map() and reduce.

## JavaScript map() method
The map() method is used to get a modified version of the array or a reduced value using callback functions. map() applies a function to each array element and creates a new array of the returned values.

The syntax of the method is as follows:

```
array.map(function(currentValue, index, arr), thisValue)

```
The map() method accepts two parameters:

- function(currentValue, index, arr): This is a required parameter that runs on each element of array. It contains three parameters: currentValue, index, and arr.
- thisValue: This parameter is optional. It holds the value of passed to the function.
The map method will take a function invoked for each element in the array as in input. The function that is passed is given arguments by the map method in the following order.


```
function callback fn(value: any, index: number, array: any[])

```

For each element, the callback fn will be passed with the value of the element as the first argument, followed by the index of the element as the second argument. Lastly the array itself is the third argument. This callback fn function takes between 0 to 3 arguments.

Finally, a new array with all the returned values from the callback fn function will be returned by the map method. Check out an example below.

For each element, the callback fn will be passed with the value of the element as the first argument, followed by the index of the element as the second argument. Lastly, the array itself is the third argument. This callback fn function takes between 0 to 3 arguments.

Finally, a new array with all the returned values from the callback fn function will be returned by the map method. Check out an example below.

```
var arr = [10, 20, 30, 40, 50]; // initialise an array and assign to arr
var arr1 = arr.map(a => a * 2); // double the element in the array
console.log("arr:",arr); // print original array
console.log("doubled array:",arr1); // print doubled array 

```
> Note: You can see that the map method maps the arrow function to each element and returns a new array. The original array remains unchanged.

## map() examples and uses
There are many uses of the map() in your JavaScript code. Let’s break down the most common ones.


## Generic use of map()
Below, our code shows how to use this method on a String to generate an array of bytes in ASCII encoding.


```
let map = Array.prototype.map
let a = map.call('Hello World', function(x) { 
  return x.charCodeAt(0)
})
```

Mapping an array of numbers to an array of their square roots
Below, our code takes an array of numbers and creates a new array with the square roots of each number.


```
let numbers = [3, 25, 100]
let roots = numbers.map(function(num) {
    return Math.sqrt(num)
})
```
> Note: Since map() builds a new array, you should not use this method if:
- You are not using the array that is returned
- You are not returning any value from the callback


## JavaScript reduce method

The reduce method reduces the array to a single value from left to right. This method leaves the original array unchanged.

The syntax of the method is as follows:

```
arr.reduce(<function>);
```

The reduce method takes a function invoked for each element in the array. It uses the reduced value of the previous element to the next. The reduce method gives arguments to the passed function in the following order:

```
function callbackfn(prev: any, curr: any, index: number, array: number[])
```

For each element, the callbackfn will be passed with the previous callbackfn function’s return value as the first argument, and the value of the element as the second argument.

This is followed by the index of the element as the third argument. Lastly, the array itself is taken as the fourth argument.

The callbackfn function returns a value passed onto the callbackfn function for the next element. If the array has only one value, that value is returned. For an empty array, an error is thrown.

Let’s learn more about reduce with an example below.

```
var arr = [10, 20, 30, 40, 50]; // initialise an array and assign to arr
var val = arr.reduce((prev, curr) => prev + curr); // reduce element to sum
console.log("arr:",arr); // print original array
console.log("reduced val:",val); // print element returned by reduce 
```
We can see here that the arrow function takes the previous value prev and adds it to the value iterated in the array curr. The reduce method sums the entire array.

## reduce examples and uses
There are many uses of reduce in your JavaScript code.Let’s break down the most common ones.


## Sum the values of an array

We can use reduce to sum all the values of an array in an easy way.

```
let sum = [0, 1, 2, 3].reduce(function (accumulator, currentValue) {
  return accumulator + currentValue
}, 0)

```
## Flatten an array of arrays

```
let flattened = [[0, 1], [2, 3], [4, 5]].reduce(
  function(accumulator, currentValue) {
    return accumulator.concat(currentValue)
  },
  []
)

```

## Group objects by a property

```
let people = [
  { name: 'Matt', age: 25 },
  { name: 'Asma', age: 23 },
  { name: 'Cami', age: 29 }
];

function groupBy(objectArray, property) {
  return objectArray.reduce(function (acc, obj) {
    let key = obj[property]
    if (!acc[key]) {
      acc[key] = []
    }
    acc[key].push(obj)
    return acc
  }, {})
}

let groupedPeople = groupBy(people, 'age')

```
## Using reduce and map() together
Now let’s learn how an example of how we can use the two methods together to make certain tasks easier. Often, we need to count array elements that satisfy a certain condition. Here’s how it’s done:

- Map the array into an array of zeros and ones.
- Reduce the array of zeros and ones into the sum.

The final output is a count of elements that satisfy a given condition.

```
var arr = ['Hello', 1, true, NaN, 'Bye']; // initialise an array of elements
var countArr = arr.map(ele => typeof ele === 'string' ? 1 : 0); // map to 0 and 1
var sum = countArr.reduce((prev, curr)=> prev + curr); // reduce for sum
console.log("arr:",arr); // print original array
console.log("array from map:", countArr); // print array returned from map method
console.log("number of Strings:",sum); // print number of strings 

```

On line 2, we apply a map to get an array of ones and zeroes. Each satisfying element has one value. In line 3, we use reduce to find the sum of the array. This means we have a count of ones. then, using combo, we find the element count in the array assigned to arr where the element is a string.

> Note: We can also use these methods together to find the number of elements in a two-dimensional array.
