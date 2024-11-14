![javascript](images/logo-js.png)

# JavaScript Coding Challenges for Beginners

## 1. Write a function `calculateStrikeRate` that takes in two parameters - the runs scored by a batsman and the total number of balls they faced. The function should return the batsman's strike rate, which is calculated as the number of runs scored per 100 balls faced.



```js
For example, if the batsman scored 45 runs off 30 balls, their strike rate would be calculated as follows:

(45 / 30) * 100 = 150

The function should round the strike rate to two decimal places.

Example Input/Output:

- calculateStrikeRate(45, 30) should return 150.00
- calculateStrikeRate(100, 60) should return 166.67
- calculateStrikeRate(25, 40) should return 62.50
```

<details><summary>Solution</summary>

```js
const calculateStrikeRate=(run,ball)=>{
    let rate=(run/ball)*100;
    return rate.toFixed(2);
}
console.log(calculateStrikeRate(45,30))
console.log(calculateStrikeRate(100,60))
console.log(calculateStrikeRate(25,40))
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 2. Even or Odd

Have the function `CountPairs` take in a string of lowercase letters and digits. The function should return the count of all pairs of characters in the string that add up to an even number.

For example, if the input string is "a1b2c3d4e5f6", there are 3 pairs that add up to an even number: "b2", "d4", and "f6". So the function should return 3.

If there are no such pairs, the function should return 0.



```js
Examples:

- `CountPairs("a1b2c3d4e5f6")` should return 3
- `CountPairs("x1y2z3")` should return 1
- `CountPairs("a2b2c2d2")` should return 4
```

<details><summary>Solution</summary>

```js
const CountPairs=(s)=>{
    let cnt=0,n=s.length;
    for(let i=1;i<n;i+=2){
        if('2468'.includes(s[i])){
            cnt++;
        } 
    }
    return cnt;
}
console.log(CountPairs('a1b2c3d4e5f6'));     //3
console.log(CountPairs('x1y2z3'));           //1
console.log(CountPairs('a2b2c2d2'));         //4
```

</details>
<details><summary>Solution Using Filter </summary>

```js
const CountPairs=(s)=> [...s].filter((char,i)=> i&1 && '2468'.includes(char)).length

console.log(CountPairs('a1b2c3d4e5f6'));     //3
console.log(CountPairs('x1y2z3'));           //1
console.log(CountPairs('a2b2c2d2'));         //4
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 3. Clock

Write a function called `reverseString` that takes a string as input and returns the reverse of that string. Your function should not use the built-in `reverse()` method.

```js
Example Input/Output:

- reverseString('hello') should return 'olleh'
- reverseString('racecar') should return 'racecar'
- reverseString('12345') should return '54321'
```

<details><summary>Solution</summary>

```js
const reverseString=s=>s.split('').reverse().join('');

console.log(reverseString('hello'));     // 'olleh'
console.log(reverseString('racecar'));   // 'racecar'
console.log(reverseString('12345'));     // '54321'
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 4. Returning Strings

Write a function isPalindrome that takes in a string and returns true if the string is a palindrome (reads the same forwards and backwards) and false otherwise.


```js
Example Input/Output:

- isPalindrome("racecar") should return true
- isPalindrome("hello") should return false
- isPalindrome("rotator") should return true
- isPalindrome("peep") should return true
```

<details><summary>Solution</summary>

```js
const reverseString=s=>s.split('').reverse().join('');

const isPalindrome=s=>{
    return (s==reverseString(s));
}

console.log(isPalindrome("racecar"));
console.log(isPalindrome("hello"));
console.log(isPalindrome("rotator"));
console.log(isPalindrome("peep")); 
```

</details>
<details><summary>Solution</summary>

```js
const isPalindrome=s=>{
    for(let i=0,j=s.length-1;i<j;i++,j--){
        if(s[i]!=s[j]) return false;
    }
    return true;
}

console.log(isPalindrome("racecar"));
console.log(isPalindrome("hello"));
console.log(isPalindrome("rotator"));
console.log(isPalindrome("peep")); 
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 5. Century From Year

Write a function `mergeArrays` that takes in two arrays of integers and returns a new array that contains all the elements from both arrays, sorted in ascending order.



```js
For example, if the two input arrays are:

[1, 3, 5, 7, 9]

[2, 4, 6, 8, 10]

The function should return the following array:

[1, 2, 3, 4, 5, 6, 7, 8, 9, 10]

Example Input/Output:

- mergeArrays([1, 3, 5, 7, 9], [2, 4, 6, 8, 10]) should return [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
- mergeArrays([2, 4, 6, 8, 10], [1, 3, 5, 7, 9]) should return [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
- mergeArrays([1, 2, 3], [4, 5, 6]) should return [1, 2, 3, 4, 5, 6]
```

<details><summary>Solution</summary>

```js
mergeArrays=(arr,brr)=> [...arr,...brr].sort((a,b)=>a-b);

console.log(mergeArrays([1, 3, 5, 7, 9],[2, 4, 6, 8, 10]));
```

</details>
<details><summary>Solution</summary>

```js
mergeArrays=(arr,brr)=> (arr.concat(brr)).sort((a,b)=>a-b);

console.log(mergeArrays([1, 3, 5, 7, 9],[2, 4, 6, 8, 10]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 6. Keep Hydrated!

Write a function called `findShortestWord` that takes in a string as a parameter and returns the shortest word in the string. If there are two or more words that are the same length and shortest, return the first word from the string with that length. Ignore punctuation and assume the string will not be empty. Words may also contain numbers.

For example, if the input string is "The quick brown fox jumps over the lazy dog", the function should return "The".


```js
Example Input/Output:

- findShortestWord("The quick brown fox jumps over the lazy dog") should return "The"
- findShortestWord("Hello world") should return "world"
- findShortestWord("Today is Monday") should return "is"

```

<details><summary>Solution</summary>

```js
const findShortestWord=s=>{
    let n=s.split(' ').length;
    s=s.split(' ');
    let res=s[0];
    for(let i=1;i<n;i++){
        if(res.length>s[i].length){
            res=s[i];
        }
    }
    return res;
}

console.log( findShortestWord("The quick brown fox jumps over the lazy dog")) // should return "The"
console.log( findShortestWord("Hello world")) // should return "world"
console.log( findShortestWord("Today is Monday"))//  should return "is"
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 7. Is n Divisible by x and y?

Suppose you are building a student database for your class that will track student’s names and their marks. Your class has 40 students but now you are seeing that there are 41 entries in your database so you decide to check the database. And you find out that you have mistakenly uploaded a student’s name twice.

Task

Write a `removeDuplicates` function that takes in an array of names and returns a new array with any duplicates removed.



```js
Sample Input:

Student_names = [‘Zara’, ‘Sadia’ , ‘Mahin’ , ‘Adnan’ , ‘Maisha’, ‘Adnan’, ‘Faiyaz’]

Sample Output :

Student_names = [‘Zara’, ‘Sadia’ , ‘Mahin’ , ‘Adnan’ , ‘Maisha’, ‘Faiyaz’]
```

<details><summary>Solution</summary>

```js
const removeDuplicates=s=>{
    const ss=s.map(ch=>ch.toLowerCase());
    return ([...new Set(ss)]);
}

console.log( removeDuplicates(['zara','sadia','mahir','adnan','maisha','adnan','Adnan'])) 
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 8. Vowel Count

You are giving a book stall at Dhaka International book fair and need to create a list of books to be featured at the event.

Task:

- Write a function `createBookList` that takes in three parameters: `bookTitles`, an array of book titles, `authorNames`, an array of corresponding author names and ‘number of copies available’ , an array of corresponding copies available for the book.
- Write a function ‘Add Copies’ that takes two parameters : `bookTitle` and the number of copies you are adding to that book. The function should add copies to that particular book.
- Write a function ‘Sell Book’ that takes two parameters : `bookTitle` and the number of copies you are selling of that book. The function should deduct copies of that particular book.
- Write a function ‘GetDetails’ that takes no parameters and returns all the titles of the book in the bookTitles array ,the author names of the book in the `authorNames’ array and the number of copies available of the corresponding books, which should be updated after adding or selling a book.

.



```js
Sample Input:

- createBookList(‘Bohubrihi’ , ‘Humayun Ahmed’ , 10)
- Add Copies(‘Bohubrihi’ , 5)
- Updates number of copies available of Bohubrihi to 15)
- ‘Sell Book’(‘Bohubrihi’ , 3)
- Updates number of copies available of Bohubrihi to 12)
- ‘GetDetails’()
- Returns (“Bohubrihi” by “Humayun Ahmed” number of copies available 12)

Hint :Make 3 arrays of the same length.
```

<details><summary>Solution</summary>

```js
Not Able to solve 
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 9. Disemvowel Trolls

Write a Javascript Program that takes String as a parameter and checks if the parameters are number or text. If the parameters are numbers then it will return a summation of the numbers. If the parameters are not numbers then it will generate a text by concatenating the strings.


```js
Sample Input:

- parseString(“21” , “24’ , “40”)
- parseString(“Hello” , “Alpha”)
- parseString(“Summer” , “2022”)

Sample Output:

- 85
- Hello Alpha
- Summer 2022

```

<details><summary>Solution</summary>

```js

parseString=(...arguments)=>{
    let sum=0;
    let concat="";
    for(const num of arguments){
        if(!isNaN(num) && num.trim()!==''){
            sum+=Number(num);
        }
        else{
            concat+=num+' ';
        }
    }
    return concat===""?sum:concat;
}

console.log(parseString("21", "24", "40")); // Output: 85
console.log(parseString("Hello", "Alpha")); // Output: "Hello Alpha"
console.log(parseString("Summer", "2022")); // Output: "Summer 2022"
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 10. Find the Odd Int

Given an array exists that has integers, write a function called "getPositiveNumbers" that takes the entire array as input and returns a new array containing only the positive numbers from the original array.



```js
Sample Input : [2, -5, 10, -3, 8, -1, 0, 7]

Sample Output: [2, 10, 8, 7]
console.log(findOdd([10])); // 10
```

<details><summary>Solution</summary>

```js
getPositiveNumbers=arr=>{
    return arr.filter(val=>val>0);
}
console.log(getPositiveNumbers([2, -5, 10, -3, 8, -1, 0, 7]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 11. Get the Middle Character

Write a function called "findMissingNumber" that takes an array of consecutive integers from 1 to n, with one number missing, and returns the missing number.

```js
For example:

Input: [1, 2, 3, 5, 6, 7, 8]

Output: 4
```

<details><summary>Solution</summary>

```js
findMissingNumber=arr=>{
    let mx=Math.max(...arr);
    let missingValue=[];
    for(let i=1;i<=mx;i++){
        if(!arr.includes(i)){
            missingValue.push(i);
        }
    }
    return missingValue.join("");
}
console.log(findMissingNumber([1, 2, 3, 5, 6, 7, 8]));
```

</details>
<details><summary>Solution</summary>

```js
findMissingNumber=arr=>{
    let n=arr.length+1;
    let totalSum=(n*(n+1))/2;
    let arrSum=arr.reduce((prev,curr)=>prev+curr,0);

    return totalSum-arrSum;
}
console.log(findMissingNumber([1, 2, 3, 5, 6, 7, 8]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 12. Write a function called "getMaxProduct" that takes an array of integers as input and returns the maximum product that can be obtained by multiplying any two distinct elements from the array.



```js
Sample Input: [2, 3, 5, 6, 7]

Sample Output: 42 (obtained by multiplying 6 and 7)
```

<details><summary>Solution</summary>

```js
getMaxProduct=arr=>{
    let newArr=arr.sort((a,b)=>a-b);
    let n=newArr.length;
    return newArr[n-1]*newArr[n-2];
}
console.log(getMaxProduct([2,3,5,6,7]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 13. Write a function called "findPrimeNumbers" that takes an array of positive integers as input and returns a new array containing only the prime numbers from the original array.

```js
For example:

Input: [2, 3, 4, 5, 6, 7, 8, 9, 10]

Output: [2, 3, 5, 7]
```

<details><summary>Solution</summary>

```js
findPrimeNumbers=arr=>{
    let n=arr.length;
    let primes=[];
    for(let i=0;i<n;i++){
        let isPrime=true;
        if(arr[i]<2) continue;

        for(let j=2;j<=arr[i]/j;j++){
            if(arr[i]%j===0){
                isPrime=false;
                break;
            }
        }
        if(isPrime){
            primes.push(arr[i]);
        }
    }
    return primes;
}

console.log(findPrimeNumbers([2, 3, 4, 5, 6, 7, 8, 9, 10]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 14. Write a program that prints a triangle asterisk (*). The number of rows in the triangle is determined by the user's input. Each row should contain a  string where the characters are repeated in a mirrored pattern.

F

```js
or example, if the user inputs 5, the program should print:
```

<details><summary>Solution</summary>

```js
let n=5;
for(let i=1;i<=n;i++){
    let star='';
    for(let j=1;j<=n-i;j++){
        star+=' ';
    }
    for(let k=1;k<=i;k++){
        star+='*';
    }
    if(i==1)console.log(star);
    else console.log(star+'*');
}
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 15. Write a program that prints a triangle of palindromic strings. The number of rows in the triangle is determined by the user's input. Each row should contain a palindromic string where the characters are repeated in a mirrored pattern.

```js
let n=5;
for(let i=1;i<=n;i++){
    let patt="";
    // taken space 
    for(let j=1;j<=n-i;j++){
        patt+=' ';
    }
    // first part : before mid
    for(let j=1;j<=i;j++){
        patt+=(j+i-1);
    }
    // rest part: after mid
    for(let j=i-1;j>=1;j--){
        patt+=(j+i-1);
    }

    console.log(patt);
}
```

<details><summary>Solution</summary>

```js
const isSquare = n => {
  return Math.sqrt(n) % 1 === 0;
};
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 16. A Fibonacci number is a sequence of numbers in which each number is the sum of the two preceding ones, usually starting with 0 and 1. In mathematical terms, the Fibonacci sequence is defined as:

F(n) = F(n-1) + F(n-2) for n > 1

So, the Fibonacci sequence begins as follows: 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, and so on. Each subsequent number in the sequence is the sum of the two preceding numbers. The Fibonacci sequence has numerous mathematical properties and applications in various fields, including mathematics, computer science, and nature.



```js
**Task 1:**

Write a function called "fibonacciSequence" that takes a positive integer n as input and returns an array containing the first n numbers in the Fibonacci sequence.

Sample Input: 8

Sample Output: [0, 1, 1, 2, 3, 5, 8, 13]

**Task 2:** 

Write a function called "isFibonacciNumber" that takes a number as input and returns true if the number is a Fibonacci number, and false otherwise.

For example:

Input: 8

Output: true

Input: 10

Output: false
```

<details><summary>Solution</summary>

```js
// task 1 
fibonacciSeries=n=>{
    let fibo=[];
    fibo.push(0)
    fibo.push(1)
    let sum=1;
    for(let i=0;i<n-2;i++){
        fibo.push(fibo[fibo.length-1]+fibo[fibo.length-2]);
    }
    return fibo
}
// task 2 

isInFibonacciSeries=n=>{
    return fibonacciSeries(n).includes(n);
}

console.log(fibonacciSeries(10));
console.log(isInFibonacciSeries(10));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 17. Write a function called "findMedian" that takes an array of numbers as input and returns the median value of the numbers.



```js
For example:

Input: [5, 2, 8, 1, 9]

Output: 5

Input: [4, 2, 7, 1, 9, 10]

Output: 5.5
```

<details><summary>Solution</summary>

```js
const findMedian=arr=>{
    let n=arr.length;
    arr=arr.sort((a,b)=>a-b);
    if(n&1){
        return arr[Math.floor(n / 2)];
    }
    else{
        let mid1=arr[(n/2)-1];
        let mid2=arr[(n/2)];
        return (mid1+mid2)/2;
    }
}

console.log(findMedian([5, 2, 8, 1, 9]));
console.log(findMedian([4, 2, 7, 1, 9, 10]));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**

## 18. Write a function called ‘countCharacter’ that takes a string as parameters and returns an object with character count.



```js
For Example:

Input: “Hello”

Output: {H:1, e:1, l: 2, o:1}
```

<details><summary>Solution</summary>

```js
countCharacter=s=>{
    let count={};
    for(let i=0;i<s.length;i++){
        let char=s[i];
        count[char]=(count[char]||0)+1;
    }
    return count;
}
console.log(countCharacter('Hello'));
```

</details>

---

**[⬆ Back to Top](#javascript-coding-challenges-for-beginners)**
