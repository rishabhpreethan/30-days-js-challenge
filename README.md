# 30 Days of LC JavaScript Challenge

### Day 1
##### 2667. Create Hello World Function

Write a function createHelloWorld. It should return a new function that always returns "Hello World".
 

Example 1:<br>
Input: args = []<br>
Output: "Hello World"<br>


Example 2:<br>
Input: args = [{},null,42]<br>
Output: "Hello World"

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


Example 1:<br>
Input: <br>
n = 10 <br>
["call","call","call"]<br>
Output: [10,11,12]<br>

Example 2:<br>
Input: <br>
n = -2<br>
["call","call","call","call","call"]<br>
Output: [-2,-1,0,1,2]

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

The three functions are:<br>
increment() increases the current value by 1 and then returns it.<br>
decrement() reduces the current value by 1 and then returns it.<br>
reset() sets the current value to init and then returns it.
 

Example 1<br>
Input init = 5, calls = ["increment","reset","decrement"]<br>
Output: [6,5,4]

Example 2:<br>
Input: init = 0, calls = ["increment","increment","decrement","reset","reset"]<br>
Output: [1,2,1,0,0]

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


Example 1:<br>
Input: arr = [1,2,3], fn = function plusone(n) { return n + 1; }<br>
Output: [2,3,4]

Example 2:<br>
Input: arr = [1,2,3], fn = function plusI(n, i) { return n + i; }<br>
Output: [1,3,5]

Example 3:<br>
Input: arr = [10,20,30], fn = function constant() { return 42; }<br>
Output: [42,42,42]

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

Given an integer array arr and a filtering function fn, return a new array with a fewer or equal number of elements.<br>
The returned array should only contain elements where fn(arr[i], i) evaluated to a truthy value.<br>
Please solve it without the built-in Array.filter method.<br>


Example 1:<br>
Input: arr = [0,10,20,30], fn = function greaterThan10(n) { return n > 10; }<br>
Output: [20,30]<br>

Example 2:<br>
Input: arr = [1,2,3], fn = function firstIndex(n, i) { return i === 0; }<br>
Output: [1]

Example 3:<br>
Input: arr = [-2,-1,0,1,2], fn = function plusOne(n) { return n + 1 }<br>
Output: [-2,0,1,2]

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

Given an integer array nums, a reducer function fn, and an initial value init, return a reduced array.<br>
A reduced array is created by applying the following operation: val = fn(init, nums[0]), val = fn(val, nums[1]), val = fn(val, nums[2]), ... until every element in the array has been processed. The final value of val is returned.<br>
If the length of the array is 0, it should return init.<br>
Please solve it without using the built-in Array.reduce method.


Example 1:<br>
Input: <br>
nums = [1,2,3,4]<br>
fn = function sum(accum, curr) { return accum + curr; }<br>
init = 0<br>
Output: 10

Example 2:<br>
Input: <br>
nums = [1,2,3,4]<br>
fn = function sum(accum, curr) { return accum + curr * curr; }<br>
init = 100<br>
Output: 130

Example 3:<br>
Input: <br>
nums = []<br>
fn = function sum(accum, curr) { return 0; }<br>
init = 25<br>
Output: 25

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