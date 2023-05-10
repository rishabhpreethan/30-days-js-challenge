# 30 Days of LC JavaScript Challenge

### Day 1
##### 2667. Create Hello World Function

Write a function createHelloWorld. It should return a new function that always returns "Hello World".
 

Example 1:
Input: args = []
Output: "Hello World"
------------------------------------------------------
Explanation:
const f = createHelloWorld();
f(); // "Hello World"
The function returned by createHelloWorld should always return "Hello World".

Example 2:
Input: args = [{},null,42]
Output: "Hello World"
------------------------------------------------------
Explanation:
const f = createHelloWorld();
f({}, null, 42); // "Hello World"
Any arguments could be passed to the function but it should still always return "Hello World".

```js
var createHelloWorld = function() {
    return () => "Hello World"; {
    }
};
```
<br>


### Day 2
##### 2620. Counter

Given an integer n, return a counter function. This counter function initially returns n and then returns 1 more than the previous value every subsequent time it is called (n, n + 1, n + 2, etc).


Example 1:
Input: 
n = 10 
["call","call","call"]
Output: [10,11,12]
------------------------------------------------------------------
Explanation: 
counter() = 10 // The first time counter() is called, it returns n.
counter() = 11 // Returns 1 more than the previous time.
counter() = 12 // Returns 1 more than the previous time.

Example 2:
Input: 
n = -2
["call","call","call","call","call"]
Output: [-2,-1,0,1,2]
------------------------------------------------------------------
Explanation: counter() initially returns -2. Then increases after each sebsequent call.

```js
var createCounter = function(n) {
    return () => n++; {
    };
};
```
<br>



### Day 3
##### 2665. Counter II

Write a function createCounter. It should accept an initial integer init. It should return an object with three functions.
The three functions are:
increment() increases the current value by 1 and then returns it.
decrement() reduces the current value by 1 and then returns it.
reset() sets the current value to init and then returns it.
 

Example 1:
Input: init = 5, calls = ["increment","reset","decrement"]
Output: [6,5,4]
-------------------------------------------------
Explanation:
const counter = createCounter(5);
counter.increment(); // 6
counter.reset(); // 5
counter.decrement(); // 4

Example 2:
Input: init = 0, calls = ["increment","increment","decrement","reset","reset"]
Output: [1,2,1,0,0]
-------------------------------------------------
Explanation:
const counter = createCounter(0);
counter.increment(); // 1
counter.increment(); // 2
counter.decrement(); // 1
counter.reset(); // 0
counter.reset(); // 0

```js
var createCounter = function(init) {
    var c = init;
    return {
        increment: () => ++c,
        decrement:() => --c,
        reset: () => c = init,
    }
};
```
<br>



### Day 4
##### 2635. Apply Transform Over Each Element in Array

Given an integer array arr and a mapping function fn, return a new array with a transformation applied to each element.
The returned array should be created such that returnedArray[i] = fn(arr[i], i).
Please solve it without the built-in Array.map method.


Example 1:
Input: arr = [1,2,3], fn = function plusone(n) { return n + 1; }
Output: [2,3,4]
-----------------------------------------------
Explanation:
const newArray = map(arr, plusone); // [2,3,4]
The function increases each value in the array by one. 

Example 2:
Input: arr = [1,2,3], fn = function plusI(n, i) { return n + i; }
Output: [1,3,5]
-----------------------------------------------
Explanation: The function increases each value by the index it resides in.

Example 3:
Input: arr = [10,20,30], fn = function constant() { return 42; }
Output: [42,42,42]
-----------------------------------------------
Explanation: The function always returns 42.

```js
var map = function(arr, fn) {
    const a=[];
    for(let i=0;i<arr.length;i++){
        a[i]=fn(arr[i],i)
    }
    return a;
};
```
<br>



### Day 5
##### 2634. Filter Elements from Array

Given an integer array arr and a filtering function fn, return a new array with a fewer or equal number of elements.
The returned array should only contain elements where fn(arr[i], i) evaluated to a truthy value.
Please solve it without the built-in Array.filter method.


Example 1:
Input: arr = [0,10,20,30], fn = function greaterThan10(n) { return n > 10; }
Output: [20,30]
----------------------------------------
Explanation:
const newArray = filter(arr, fn); // [20, 30]
The function filters out values that are not greater than 10

Example 2:
Input: arr = [1,2,3], fn = function firstIndex(n, i) { return i === 0; }
Output: [1]
----------------------------------------
Explanation:
fn can also accept the index of each element
In this case, the function removes elements not at index 0

Example 3:
Input: arr = [-2,-1,0,1,2], fn = function plusOne(n) { return n + 1 }
Output: [-2,0,1,2]
----------------------------------------
Explanation:
Falsey values such as 0 should be filtered out

```js
var filter = function(arr, fn) {
    a=[];
    for (let i = 0; i < arr.length; i++){
        if (fn(arr[i],i)){
            a.push(arr[i])
        }
    }
    return a;
};
```
<br>



### Day 6
##### 2626. Array Reduce Transformation

Given an integer array nums, a reducer function fn, and an initial value init, return a reduced array.
A reduced array is created by applying the following operation: val = fn(init, nums[0]), val = fn(val, nums[1]), val = fn(val, nums[2]), ... until every element in the array has been processed. The final value of val is returned.
If the length of the array is 0, it should return init.
Please solve it without using the built-in Array.reduce method.


Example 1:
Input: 
nums = [1,2,3,4]
fn = function sum(accum, curr) { return accum + curr; }
init = 0
Output: 10
----------------------------------------------------------
Explanation:
initially, the value is init=0.
(0) + nums[0] = 1
(1) + nums[1] = 3
(3) + nums[2] = 6
(6) + nums[3] = 10
The final answer is 10.

Example 2:
Input: 
nums = [1,2,3,4]
fn = function sum(accum, curr) { return accum + curr * curr; }
init = 100
Output: 130
----------------------------------------------------------
Explanation:
initially, the value is init=100.
(100) + nums[0]^2 = 101
(101) + nums[1]^2 = 105
(105) + nums[2]^2 = 114
(114) + nums[3]^2 = 130
The final answer is 130.

Example 3:
Input: 
nums = []
fn = function sum(accum, curr) { return 0; }
init = 25
Output: 25
----------------------------------------------------------
Explanation: For empty arrays, the answer is always init.

```js
var reduce = function(nums, fn, init) {
    let c = init;
    for(var v of nums)
    {
        c = fn(c,v);
    }
    return c;
};
```
<br>



### Day 7