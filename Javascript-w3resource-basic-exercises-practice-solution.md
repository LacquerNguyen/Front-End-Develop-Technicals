#### I. JavaScript basic - Exercises, Practice, Solution
---
**1. Write a JavaScript program to display the current day and time in the following format.**
- Today is : Friday. 
- Current time is : 4 PM : 50 : 22

>JavaScript Code:
```javascript
var today = new Date();
var day = today.getDay();
var daylist = ["Sunday", "Monday", "Tuesday", "Wednesday ", "Thursday", "Friday", "Saturday"];
console.log("Today is : " + daylist[day] + ".");
var hour = today.getHours();
var minute = today.getMinutes();
var second = today.getSeconds();
var prepand = (hour >= 12) ? " PM " : " AM ";
hour = (hour >= 12) ? hour - 12 : hour;
if (hour === 0 && prepand === ' PM ') {
  if (minute === 0 && second === 0) {
    hour = 12;
    prepand = ' Noon';
  } else {
    hour = 12;
    prepand = ' PM';
  }
}
if (hour === 0 && prepand === ' AM ') {
  if (minute === 0 && second === 0) {
    hour = 12;
    prepand = ' Midnight';
  } else {
    hour = 12;
    prepand = ' AM';
  }
}
console.log("Current Time : " + hour + prepand + " : " + minute + " : " + second);
```

>ES6 Version:
```javascript
const today = new Date();
const day = today.getDay();
const daylist = ["Sunday", "Monday", "Tuesday", "Wednesday ", "Thursday", "Friday", "Saturday"];
console.log(`Today is : ${daylist[day]}.`);
let hour = today.getHours();
const minute = today.getMinutes();
const second = today.getSeconds();
let prepand = (hour >= 12) ? " PM " : " AM ";
hour = (hour >= 12) ? hour - 12 : hour;
if (hour === 0 && prepand === ' PM ') {
  if (minute === 0 && second === 0) {
    hour = 12;
    prepand = ' Noon';
  } else {
    hour = 12;
    prepand = ' PM';
  }
}
if (hour === 0 && prepand === ' AM ') {
  if (minute === 0 && second === 0) {
    hour = 12;
    prepand = ' Midnight';
  } else {
    hour = 12;
    prepand = ' AM';
  }
}
console.log(`Current Time : ${hour}${prepand} : ${minute} : ${second}`);
```

>Result:
```javascript
Today is : Tuesday.
Current Time : 5 PM  : 51 : 20
```

**2. Write a JavaScript function to print the contents of the current window**

>JavaScript Code:
```javascript
function print_current_page(){
  window.print();
}
```

>ES6 Version:
```javascript
function print_current_page(){
  window.print();
}
```

**3. Write a JavaScript program to get the current date.**
**Expected Output :**
- mm-dd-yyyy, mm/dd/yyyy or dd-mm-yyyy, dd/mm/yyyy

>JavaScript Code:
```javascript
var today = new Date();
var dd = today.getDate();

var mm = today.getMonth() + 1;
var yyyy = today.getFullYear();
if (dd < 10) {
  dd = '0' + dd;
}

if (mm < 10) {
  mm = '0' + mm;
}
today = mm + '-' + dd + '-' + yyyy;
console.log(today);
today = mm + '/' + dd + '/' + yyyy;
console.log(today);
today = dd + '-' + mm + '-' + yyyy;
console.log(today);
today = dd + '/' + mm + '/' + yyyy;
console.log(today);
```

>ES6 Version:
```javascript
let today = new Date();
let dd = today.getDate();

let mm = today.getMonth() + 1;
const yyyy = today.getFullYear();
if (dd < 10) {
  dd = `0${dd}`;
}

if (mm < 10) {
  mm = `0${mm}`;
}
today = `${mm}-${dd}-${yyyy}`;
console.log(today);
today = `${mm}/${dd}/${yyyy}`;
console.log(today);
today = `${dd}-${mm}-${yyyy}`;
console.log(today);
today = `${dd}/${mm}/${yyyy}`;
console.log(today);
```

**4. Write a JavaScript function to find the area of a triangle where lengths of the three of its sides are 5, 6, 7**

>JavaScript Code:
```javascript
var side1 = 5; 
var side2 = 6; 
var side3 = 7; 
var perimeter = (side1 + side2 + side3)/2;
var area =  Math.sqrt(perimeter*((perimeter-side1)*(perimeter-side2)*(perimeter-side3)));
console.log(area);
```

>ES6 Version:
```javascript
const side1 = 5; 
const side2 = 6; 
const side3 = 7; 
const perimeter = (side1 + side2 + side3)/2;
const area =  Math.sqrt(perimeter*((perimeter-side1)*(perimeter-side2)*(perimeter-side3)));
console.log(area);
```
>Result:
```javascript
14.696938456699069
```

**5. Rotate the string 'w3resource' in right direction by periodically removing one letter from the end of the string and attaching it to the front**

>JavaScript Code:
```javascript
function animate_string(id) {
  var element = document.getElementById(id);
  var textNode = element.childNodes[0]; // assuming no other children
  var text = textNode.data;

  setInterval(function() {
    text = text[text.length - 1] + text.substring(0, text.length - 1);
    textNode.data = text;
  }, 100);
}
```

>ES6 Version:
```javascript
function animate_string(id) {
  const element = document.getElementById(id);
  const textNode = element.childNodes[0]; // assuming no other children
  let text = textNode.data;

  setInterval(() => {
    text = text[text.length - 1] + text.substring(0, text.length - 1);
    textNode.data = text;
  }, 100);
}
```

**6. Write a JavaScript program to determine whether a given year is a leap year in the Gregorian calendar.**

>JavaScript Code:
```javascript
year = window.prompt("Input a Year : ");
x = (year % 100 === 0) ? (year % 400 === 0) : (year % 4 === 0);
console.log(x);
```

```javascript
var elm = document.getElementById('year_check');
elm.addEventListener('input', leapYear);

function leapYear() {
  if (this.value % 4 === 0) {
    if (this.value % 100 === 0) {
      if (this.value % 400 === 0) {
        document.getElementById('demo').innerHTML = 'Năm ' + this.value + ' Là Năm Nhuận';
      } else {
        document.getElementById('demo').innerHTML = 'Năm ' + this.value + ' Không Phải Là Năm Nhuận';
      }
    } else {
      document.getElementById('demo').innerHTML = 'Năm ' + this.value + ' Là Năm Nhuận';
    }
  } else {
    document.getElementById('demo').innerHTML = 'Năm ' + this.value + ' Không Phải Là Năm Nhuận';
  }
}
```

>ES6 Version:
```javascript
year = window.prompt("Input a Year : ");
x = (year % 100 === 0) ? (year % 400 === 0) : (year % 4 === 0);
console.log(x);
```

**7. Write a JavaScript program to find which 1st January is being a Sunday between 2014 and 2050.**

>JavaScript Code:
```javascript
for (let year = 2014; year <= 2050; year++) {
  const date = new Date(year, 0, 1);
  if (date.getDay() === 0) {
    console.log("1st January is being a Sunday  " + year);
  }
}
```

>ES6 Version:
```javascript
console.log('--------------------');
for (let year = 2014; year <= 2050; year++){
  const d = new Date(year, 0, 1);
  if ( d.getDay() === 0 )
     console.log(`1st January is being a Sunday  ${year}`);
}
console.log('--------------------');
```

**8. Write a JavaScript program where the program takes a random integer between 1 to 10, the user is then prompted to input a guess number. If the user input matches with guess number, the program will display a message "Good Work" otherwise display a message "Not matched".**

>JavaScript Code:
```javascript
// Get a random integer from 1 to 10 inclusive
 var num = Math.ceil(Math.random() * 10);
 var gnum = prompt('Guess the number between 1 and 10 inclusive');
 if (gnum == num)
   alert('Matched');
  else
   alert('Not matched, the number was ' + num);
```

>ES6 Version:
```javascript
const num = Math.ceil(Math.random() * 10);
const gnum = prompt('Guess the number between 1 and 10 inclusive');
if (gnum == num)
  alert('Matched');
else
  alert('Not matched, the number was ${num}');
```

**9. Write a JavaScript program to calculate number of days left until next Christmas.**

>JavaScript Code:
```javascript
today=new Date();
var cmas=new Date(today.getFullYear(), 11, 25);
if (today.getMonth()==11 && today.getDate()>25) {
  cmas.setFullYear(cmas.getFullYear()+1); 
}
// convert to milliseconds for a day
var one_day=1000*60*60*24;
console.log(Math.ceil((cmas.getTime()-today.getTime())/(one_day))+" days left until Christmas!");
```

>ES6 Version:
```javascript
today=new Date();
const cmas=new Date(today.getFullYear(), 11, 25);
if (today.getMonth()==11 && today.getDate()>25) {
  cmas.setFullYear(cmas.getFullYear()+1); 
}
// convert to milliseconds for a day
const one_day=1000*60*60*24;
console.log(`${Math.ceil((cmas.getTime()-today.getTime())/(one_day))} days left until Christmas!`);
```

**10. Write a JavaScript program to calculate multiplication and division of two numbers (input from user).**

>HTML:
```javascript
<form>
  1st Number : <input type="text" id="firstNumber" /><br>
  2nd Number: <input type="text" id="secondNumber" /><br>
  <input type="button" onClick="multiplyBy()" Value="Multiply" />
  <input type="button" onClick="divideBy()" Value="Divide" />
</form>
<p>The Result is : <br>
  <span id = "result"></span>
</p>
```

>JavaScript Code:
```javascript
function multiplyBy(){
  num1 = document.getElementById("firstNumber").value;
  num2 = document.getElementById("secondNumber").value;
  document.getElementById("result").innerHTML = num1 * num2;
}

function divideBy() { 
  num1 = document.getElementById("firstNumber").value;
  num2 = document.getElementById("secondNumber").value;
  document.getElementById("result").innerHTML = num1 / num2;
}
```

>ES6 Version:
```javascript
function multiplyBy(){
  num1 = document.getElementById("firstNumber").value;
  num2 = document.getElementById("secondNumber").value;
  document.getElementById("result").innerHTML = num1 * num2;
}

function divideBy() { 
  num1 = document.getElementById("firstNumber").value;
  num2 = document.getElementById("secondNumber").value;
  document.getElementById("result").innerHTML = num1 / num2;
}
```

**11. Write a JavaScript program to get the website URL (loading page).**

>JavaScript Code:
```javascript
alert(document.URL);
```

>ES6 Version:
```javascript
alert(document.URL);
```

**12. Write a JavaScript exercise to create a variable using a user-defined name.**

>JavaScript Code:
```javascript
var var_name = 'abcd';
var n = 120;
this[var_name] = n;
console.log(this[var_name])
```

>ES6 Version:
```javascript
const var_name = 'abcd';
const n = 120;
this[var_name] = n;
console.log(this[var_name])
```

**13. Write a JavaScript exercise to get the extension of a filename.**
- The ```split()``` method is used to split a string into an array of substrings, and returns the new array.
- The ```pop()``` method removes the last element of an array, and returns that element.

>JavaScript Code:
```javascript
filename = "system.php"
console.log(filename.split('.').pop());
filename = "abc.js"
console.log(filename.split('.').pop());
```

>ES6 Version:
```javascript
filename = "system.php"
console.log(filename.split('.').pop());
filename = "abc.js"
console.log(filename.split('.').pop());
```

**14. Write a JavaScript program to get the difference between a given number and 13, if the number is greater than 13 return double the absolute difference.**

>JavaScript Code:
```javascript
function difference(n)
 {
    if (n <= 13)
        return 13 - n;
    else
        return (n - 13) * 2;
 }
console.log(difference(50))
console.log(difference(10))
```

>ES6 Version:
```javascript
function difference(n){
    if (n <= 13)
        return 13 - n;
    else
        return (n - 13) * 2;
 }
console.log(difference(50))
console.log(difference(10))
```

**15. Write a JavaScript program to compute the sum of the two given integers. If the two values are same, then returns triple their sum.**

>JavaScript Code:
```javascript
function sumTriple(x, y){
  if(x == y){
    return 3*(x+y);
  }
  else{
    return (x+y);
  }
}
console.log(sumTriple(10, 20));
console.log(sumTriple(10, 10));
```

>ES6 Version:
```javascript
function sumTriple (x, y) {
  if (x == y) {
    return 3 * (x + y);
    } 
   else
   {
    return (x + y);
   }
 }
console.log(sumTriple(10, 20));
console.log(sumTriple(10, 10));
```

**16. Write a JavaScript program to compute the absolute difference between a specified number and 19. Returns triple their absolute difference if the specified number is greater than 19.**

>JavaScript Code:
```javascript
function diff_num(n) {
  if (n <= 19) {
    return (19 - n);
  }
  else{
     return (n - 19) * 3;
  }
}

console.log(diff_num(12));
console.log(diff_num(19));
console.log(diff_num(22));
```

>ES6 Version:
```javascript
function diff_num(n) {
  if (n <= 19) {
    return (19 - n);
  }
  else {
     return (n - 19) * 3;
  }
}

console.log(diff_num(12));
console.log(diff_num(19));
console.log(diff_num(22));
```

**17. Write a JavaScript program to check two given numbers and return true if one of the number is 50 or if their sum is 50.**

>JavaScript Code:
```javascript
function test50(x, y){
  if((x == 50 || y == 50) || (x+y == 50)){
    return true;
  }
  else{
    return false;
  }
 }
  console.log(test50(10, 10));
  console.log(test50(25, 25));
  console.log(test50(25, 50));
  console.log(test50(50, 25));
```

```javascript
function test50(x, y) {
  return ((x == 50 || y == 50) || (x + y == 50));
}
console.log(test50(50, 50))
console.log(test50(20, 50))
console.log(test50(20, 20))
console.log(test50(20, 30))
```

>ES6 Version:
```javascript
function test50(x, y) {
  return ((x == 50 || y == 50) || (x + y == 50));
}
console.log(test50(50, 50))
console.log(test50(20, 50))
console.log(test50(20, 20))
console.log(test50(20, 30))
```

**18. Write a JavaScript program to check a given integer is within 20 of 100 or 400**

>JavaScript Code:
```javascript
function testhundred(x) {
  return ((Math.abs(100 - x) <= 20) ||
	 (Math.abs(400 - x) <= 20));
}

console.log(testhundred(10));
console.log(testhundred(90));
console.log(testhundred(99));
console.log(testhundred(199));
console.log(testhundred(200));
```

>ES6 Version:
```javascript
function testhundred(x) {
  return ((Math.abs(100 - x) <= 20) ||
	 (Math.abs(400 - x) <= 20));
}

console.log(testhundred(10));
console.log(testhundred(90));
console.log(testhundred(99));
console.log(testhundred(199));
console.log(testhundred(200));
```

```javascript
false
true
true
false
false
```

**19. Write a JavaScript program to check from two given integers, if one is positive and one is negative**

>JavaScript Code:
```javascript
function positive_negative(x, y){
  if ((x < 0 && y > 0) || x > 0 && y < 0) {
    return true;
  }
  else {
    return false;
  }
}
console.log(positive_negative(2, 2));
console.log(positive_negative(-2, 2));
console.log(positive_negative(2, -2));
console.log(positive_negative(-2, -2));
```

>ES6 Version:
```javascript
function positive_negative(x, y){
  if ((x < 0 && y > 0) || x > 0 && y < 0) {
    return true;
  }
  else {
    return false;
  }
}
console.log(positive_negative(2, 2));
console.log(positive_negative(-2, 2));
console.log(positive_negative(2, -2));
console.log(positive_negative(-2, -2));
```

**20. Write a JavaScript program to create a new string adding "Py" in front of a given string. If the given string begins with "Py" then return the original string.**
- ```substring(-5)```: If "start" is less than 0, it will start extraction from index position 0

>JavaScript Code:
```javascript
function string_check(str1) {
  if (str1 === null || str1 === undefined || str1.substring(0, 2) === 'Py') {
    return str1;
  }
  return "Py"+str1;
}

console.log(string_check("Python"));
console.log(string_check("thon"));
console.log(string_check(""));
console.log(string_check());
```

>ES6 Version:
```javascript
function string_check(str1) {
  if (str1 === null || str1 === undefined || str1.substring(0, 2) === 'Py') {
    return str1;
  }
  return `Py${str1}`;
}

console.log(string_check("Python"));
console.log(string_check("thon"));
console.log(string_check(""));
console.log(string_check());
```

**21. Write a JavaScript program to remove a character at the specified position of a given string and return the new string**

>JavaScript Code:
```javascript
function remove_character(str, char_pos){
  part1 = str.substring(0, char_pos);
  part2 = str.substring(char_pos+1, str.length);
  return part1 + part2;
}
console.log(remove_character('Python', 2));
console.log(remove_character('Python', 3));
console.log(remove_character('Python', 5));
```

>ES6 Version:
```javascript
function remove_character(str, char_pos) {
  part1 = str.substring(0, char_pos);
  part2 = str.substring(char_pos + 1, str.length);
  return (part1 + part2);
 }

console.log(remove_character("Python",0));
console.log(remove_character("Python",3));
console.log(remove_character("Python",5));
```
>Result:
```javascript
"ython"
"Pyton"
"Pytho"
```

**22. Write a JavaScript program to create a new string from a given string changing the position of first and last characters. The string length must be greater than or equal to 1**
- The ```charAt()``` method returns the character at the specified index in a string.
- The ```index``` of the first character is ```0```, the second character is ```1```, and so on.
- Return the first character of a string: ```var str = "HELLO WORLD"; str.charAt(0)```

>JavaScript Code:
```javascript
function first_last(str1) {
  if (str1.length <= 1){
    return str1;
  }
  mid_char = str1.substring(1, str1.length - 1);
  return (str1.charAt(str1.length - 1)) + mid_char + str1.charAt(0);
}
console.log(first_last('a'));
console.log(first_last('ab'));
console.log(first_last('abc'));
```

>ES6 Version:
```javascript
function first_last(str1) {
  if (str1.length <= 1){
    return str1;
  }
  mid_char = str1.substring(1, str1.length - 1);
  return (str1.charAt(str1.length - 1)) + mid_char + str1.charAt(0);
}
console.log(first_last('a'));
console.log(first_last('ab'));
console.log(first_last('abc'));
```

>Result:
```javascript
a
ba
cba
```

**23. Write a JavaScript program to create a new string from a given string with the first character of the given string added at the front and back**

>JavaScript Code:
```javascript
function front_back(str){
  first = str.substring(0,1);
  return first + str + first;
}
console.log(front_back('a'));
console.log(front_back('ab'));
console.log(front_back('abc'));
```

>ES6 Version:
```javascript
function front_back(str){
  first = str.substring(0,1);
  return first + str + first;
}
console.log(front_back('a'));
console.log(front_back('ab'));
console.log(front_back('abc'));
```

>Result:
```javascript
aaa
aaba
aabca
```

**24. Write a JavaScript program check if a given positive number is a multiple of 3 or a multiple of 7**

>JavaScript Code:
```javascript
function test37(x) {
  if (x % 3 == 0 || x % 7 == 0) {
    return true;
  } 
  else {
    return false;
  }
}

console.log(test37(12));
console.log(test37(14));
console.log(test37(10));
console.log(test37(11));
```

>ES6 Version:
```javascript
function test37(x) {
  if (x % 3 == 0 || x % 7 == 0) {
    return true;
  } else {
    return false;
  }
}

console.log(test37(12));
console.log(test37(14));
console.log(test37(10));
console.log(test37(11));
```
>Result:
```javascript
true
true
false
false
```
**25. Write a JavaScript program to create a new string from a given string taking the last 3 characters and added at both the front and back. The string length must be 3 or more.**

>JavaScript Code:
```javascript
function front_back3(str){
  if (str.length>=3){
   back = str.substring(str.length-3);
   return back + str + back;
  }
  else
   return false;
 }
console.log(front_back3("abc"));
console.log(front_back3("ab"));
console.log(front_back3("abcd"));

```

>ES6 Version:
```javascript
function front_back3(str) {
  if (str.length >= 3) {
    str_len = 3;

    back = str.substring(str.length - 3);
    return back + str + back;
  } else
    return false;
}
console.log(front_back3("abc"));
console.log(front_back3("ab"));
console.log(front_back3("abcd"));
```
>Result:
```javascript
abcabcabc
false
bcdabcdbcd
```
**26. Write a JavaScript program to check if a string starts with 'Java' and false otherwise.**

>JavaScript Code:
```javascript
function start_spec_str(str) {
  if (str.length < 4) {
    return false;
  }
  front = str.substring(0, 4);
  if (front == 'Java') {
    return true;
  } else {
    return false;
  }
}

console.log(start_spec_str("JavaScript"));
console.log(start_spec_str("Java"));
console.log(start_spec_str("Python"));
```

>ES6 Version:
```javascript
function start_spec_str(str) {
  if (str.length < 4) {
    return false;
  }
  front = str.substring(0, 4);
  if (front == 'Java') {
    return true;
  } else {
    return false;
  }
}

console.log(start_spec_str("JavaScript"));
console.log(start_spec_str("Java"));
console.log(start_spec_str("Python"));
```
>Result:
```javascript
true
true
false
```
**27. Write a JavaScript program to check if two given integer values are in the range 50..99 (inclusive). Return true if either of them are in the said range.**

>JavaScript Code:
```javascript
function check_numbers(x, y) {
  if ((x >= 50 && x <= 99) || (y >= 50 && y <= 99)) {
    return true;
  } else {
    return false;
  }
}

console.log(check_numbers(12, 101));
console.log(check_numbers(52, 80));
console.log(check_numbers(15, 99));
```

```
function check_numbers(x, y){
  return (x >= 50 && x <= 99) || y >= 50 && y <= 99
}
```

>ES6 Version:
```javascript
function check_numbers(x, y) {
  if ((x >= 50 && x <= 99) || (y >= 50 && y <= 99)) {
    return true;
  } else {
    return false;
  }
}

console.log(check_numbers(12, 101));
console.log(check_numbers(52, 80));
console.log(check_numbers(15, 99));
```
>Result:
```javascript
false
true
true
```

**28. Write a JavaScript program to check if three given integer values are in the range 50..99 (inclusive). Return true if one or more of them are in the said range.**

>JavaScript Code:
```javascript
function check_three_nums(x, y, z) {
  return (x >= 50 && x <= 99) || (y >= 50 && y <= 99) || (z >= 50 && z <= 99);
}

console.log(check_three_nums(50, 90, 99));
console.log(check_three_nums(5, 9, 199));
console.log(check_three_nums(65, 89, 199));
console.log(check_three_nums(65, 9, 199));
```

>ES6 Version:
```javascript
function check_three_nums(x, y, z) {
  return (x >= 50 && x <= 99) || (y >= 50 && y <= 99) || (z >= 50 && z <= 99);
}

console.log(check_three_nums(50, 90, 99));
console.log(check_three_nums(5, 9, 199));
console.log(check_three_nums(65, 89, 199));
console.log(check_three_nums(65, 9, 199));
```

**29. Write a JavaScript program to check if a string "Script" presents at 5th (index 4) position in a given string, if "Script" presents in the string return the string without "Script" otherwise return the original one**

>JavaScript Code:
```javascript
function check_script(str) {
  if (str.length < 6) {
    return str;
  }
  let result_str = str;
  if (str.substring(10, 4) == 'Script') {
    result_str = str.substring(0, 4) + str.substring(10, str.length);
  }
  return result_str;
}
console.log(check_script("JavaScript"));
console.log(check_script("CoffeeScript"));
```

>ES6 Version:
```javascript
function check_script(str) {
  if (str.length < 6) {
    return str;
  }
  let result_str = str;
  if (str.substring(10, 4) == 'Script') {
    result_str = str.substring(0, 4) + str.substring(10, str.length);
  }
  return result_str;
}

console.log(check_script("JavaScript"));
console.log(check_script("CoffeeScript"));
```
>Result:
```javascript
Java
CoffeeScript
```

**30. Write a JavaScript program to find the largest of three given integers**

>JavaScript Code:
```javascript
function max_of_three(x, y, z) {
  max_val = 0;
  if (x > y) {
    max_val = x;
  } else {
    max_val = y;
  }
  if (z > max_val) {
    max_val = z;
  }
  return max_val;
}

console.log(max_of_three(1, 0, 1));
console.log(max_of_three(0, -10, -20));
console.log(max_of_three(1000, 510, 440));
```

>ES6 Version:
```javascript
function max_of_three(x, y, z) {
  max_val = 0;
  if (x > y) {
    max_val = x;
  } else {
    max_val = y;
  }
  if (z > max_val) {
    max_val = z;
  }
  return max_val;
}

console.log(max_of_three(1, 0, 1));
console.log(max_of_three(0, -10, -20));
console.log(max_of_three(1000, 510, 440));
```
>Result:
```javascript
1
0
1000
```

**31. Write a JavaScript program to find a value which is nearest to 100 from two different given integer values.**

>JavaScript Code:
```javascript
function near_100(x, y) {
  if (x != y) {
    x1 = Math.abs(x - 100);
    y1 = Math.abs(y - 100);

    if (x1 < y1) {
      return x;
    }
    if (y1 < x1) {
      return y;
    }
    return 0;
  } else
    return false;
}

console.log(near_100(90, 89));
console.log(near_100(-90, -89));
console.log(near_100(90, 90));
```

>ES6 Version:
```javascript
function near_100(x, y) {
  if (x != y) {
    x1 = Math.abs(x - 100);
    y1 = Math.abs(y - 100);

    if (x1 < y1) {
      return x;
    }
    if (y1 < x1) {
      return y;
    }
    return 0;
  } else
    return false;
}

console.log(near_100(90, 89));
console.log(near_100(-90, -89));
console.log(near_100(90, 90));
```
>Result:
```javascript
90
-89
false
```

**32. Write a JavaScript program to check if two numbers are in range 40..60 or in the range 70..100 inclusive.**

>JavaScript Code:
```javascript
function numbers_ranges(x, y) {
  if ((x >= 40 && x <= 60 && y >= 40 && y <= 60) || (x >= 70 && x <= 100 && y >= 70 && y <= 100)) {
    return true;
  } else {
    return false;
  }
}

console.log(numbers_ranges(44, 56));
console.log(numbers_ranges(70, 95));
console.log(numbers_ranges(50, 89));
```

>ES6 Version:
```javascript
function numbers_ranges(x, y) {
  if ((x >= 40 && x <= 60 && y >= 40 && y <= 60) || (x >= 70 && x <= 100 && y >= 70 && y <= 100)) {
    return true;
  } else {
    return false;
  }
}

console.log(numbers_ranges(44, 56));
console.log(numbers_ranges(70, 95));
console.log(numbers_ranges(50, 89));
```
>Result:
```javascript
true
true
false
```

**33. Write a JavaScript program to find the larger number from the two given positive integers, the two numbers are in the range 40..60 inclusive.**

>JavaScript Code:
```javascript
function max_townums_range(x, y) {
  if (x >= 40 && y <= 60) {
    let max_val = 0
    if (x > y) {
      max_val = x;
    } else
      max_val = y;
    return max_val;
  } else
    return false;
}

console.log(max_townums_range(45, 60));
console.log(max_townums_range(25, 60));
console.log(max_townums_range(45, 80));
```

>Result:
```javascript
60
60
false
```
**34. Write a JavaScript program to check a given string contains 2 to 4 numbers of a specified character.**

- The ```charAt()``` method returns the character at the specified index in a string.

>JavaScript Code:
```javascript
function check_char(str, char) {
  ctr = 0;
  for (let i = 0; i < str.length; i++) {
    if (str.charAt(i) == char) {
      ctr++;
    }
  }
  return (ctr >= 2 && ctr <= 4);
}

console.log(check_char("Python", "y"));
console.log(check_char("JavaScript", "a"));
console.log(check_char("Console", "o"));
```

>ES6 Version:
```javascript
function check_char(str, char) {
  ctr = 0;
  for (let i = 0; i < str.length; i++) {
    if (str.charAt(i) == char) {
      ctr++;
    }
  }
  return (ctr >= 2 && ctr <= 4);
}

console.log(check_char("Python", "y"));
console.log(check_char("JavaScript", "a"));
console.log(check_char("Console", "o"));
```
>Result:
```javascript
false
true
true
```

**35. Write a JavaScript program to check if the last digit of the three given positive integers is same**

>JavaScript Code:
```javascript
function last_digit(x, y, z) {
  if ((x > 0) && y > 0 && z > 0) {
    return (x % 10 == y % 10 && y % 10 == z % 10 && x % 10 == z % 10);
  } else
    return false;
}

console.log(last_digit(20, 30, 400));
console.log(last_digit(-20, 30, 400));
console.log(last_digit(20, -30, 400));
console.log(last_digit(20, 30, -400));
```

>ES6 Version:
```javascript
function last_digit(x, y, z) {
  if ((x > 0) && y > 0 && z > 0) {
    return (x % 10 == y % 10 && y % 10 == z % 10 && x % 10 == z % 10);
  } else
    return false;
}

console.log(last_digit(20, 30, 400));
console.log(last_digit(-20, 30, 400));
console.log(last_digit(20, -30, 400));
console.log(last_digit(20, 30, -400));
```
>Result:
```javascript
true
false
false
false
```

**36. Write a JavaScript program to create a new string with first 3 characters are in lower case from a given string. If the string length is less than 3 convert all the characters in uppercase**

>JavaScript Code:
```javascript
function upper_lower(str) {
  if (str.length < 3) {
    return str.toUpperCase();
  }
  front_part = (str.substring(0, 3)).toLowerCase();
  back_part = str.substring(3, str.length);
  return front_part + back_part;
}
console.log(upper_lower("Python"));
console.log(upper_lower("JAVAScript"));
```

>ES6 Version:
```javascript
function upper_lower(str) {
  if (str.length <= 3) {
    return str.toUpperCase();
  }
  front_part = (str.substring(0, 3)).toLowerCase();
  back_part = str.substring(3, str.length);  
  return front_part + back_part;
}
console.log(upper_lower("Python"));
console.log(upper_lower("JAVAScript"));
```

>Result:
```javascript
python
javAScript
```

**37. Write a JavaScript program to check the total marks of a student in various examinations. The student will get A+ grade if the total marks are in the range 89..100 inclusive, if the examination is "Final-exam." the student will get A+ grade where total marks must be greater than or equal to 90. Return true if the student get A+ grade or false otherwise**
- Viết một chương trình JavaScript để kiểm tra tổng số điểm của một học sinh trong các kỳ thi khác nhau. Học sinh sẽ nhận được điểm A + nếu tổng số điểm trong phạm vi 89..100 bao gồm, nếu kỳ thi là "Kỳ Thi Cuối Cùng". học sinh sẽ đạt điểm A + và tổng số điểm phải lớn hơn hoặc bằng 90. Trả lại đúng nếu học sinh đạt điểm A + hoặc sai nếu không

>JavaScript Code:
```javascript
function exam_status(totmarks, is_exam) {
  if (is_exam) {
    return totmarks >= 90;
  }
  return (totmarks >= 89 && totmarks <= 100);
}

console.log(exam_status("78", " "));
console.log(exam_status("89", "true "));
console.log(exam_status("99", "true "));
```

>ES6 Version:
```javascript
function exam_status(totmarks,is_exam)
  {
  if (is_exam) {
    return totmarks >= 90;
  }
 return (totmarks >= 89 && totmarks <= 100);
 }

console.log(exam_status("78", " "));
console.log(exam_status("89", "true "));
console.log(exam_status("99", "true "));
```

>Result:
```javascript
false
false
true
```

**38. Write a JavaScript program to compute the sum of the two given integers, If the sum is in the range 50..80 return 65 other wise return 80**

>JavaScript Code:
```javascript
function sortaSum(x, y) {
  const sum_nums = x + y;
  if (sum_nums >= 50 && sum_nums <= 80) {
    return 65;
  }
  return 80;
}

console.log(sortaSum(30, 20));
console.log(sortaSum(90, 80));
```

>ES6 Version:
```javascript
function sortaSum(x, y) {
  const sum_nums = x + y;
  if (sum_nums >= 50 && sum_nums <= 80) {
    return 65;
  }
  return 80;
}

console.log(sortaSum(30, 20));
console.log(sortaSum(90, 80));
```

>Result:
```javascript
65
80
```

**39. Write a JavaScript program to check from two given integers if either one is 8 or their sum or difference is 8.**

>JavaScript Code:
```javascript
function check8(x, y) {
  if (x == 8 || y == 8) {
    return true;
  }

  if (x + y == 8 || Math.abs(x - y) == 8) {
    return true;
  }

  return false;
}

console.log(check8(7, 8));
console.log(check8(16, 8));
console.log(check8(24, 32));
console.log(check8(17, 18));
```

>ES6 Version:
```javascript
function check8(x, y) {
  if (x == 8 || y == 8) {
    return true;
  }

  if (x + y == 8 || Math.abs(x - y) == 8) {
    return true;
  }

  return false;
}

console.log(check8(7, 8));
console.log(check8(16, 8));
console.log(check8(24, 32));
console.log(check8(17, 18));
```

>Result:
```javascript
true
true
true
false
```

**40. Write a JavaScript program to check three given numbers, if the three numbers are same return 30 otherwise return 20 and if two numbers are same return 40**

>JavaScript Code:
```javascript
function three_numbers(x, y, z) {
  if (x == y && y == z) {
    return 30;
  }
  if (x == y || y == z || z == x) {
    return 40;
  }
  return 20;
}
console.log(three_numbers(8, 8, 8));
console.log(three_numbers(8, 8, 18));
console.log(three_numbers(8, 7, 18));
```

>ES6 Version:
```javascript
function three_numbers(x, y, z) {
  if (x == y && y == z) {
    return 30;
  }

  if (x == y || y == z || z == x) {
    return 40;
  }
  return 20;
}
console.log(three_numbers(8, 8, 8));
console.log(three_numbers(8, 8, 18));
console.log(three_numbers(8, 7, 18));
```

>Result:
```javascript
30
40
20
```

**41. Write a JavaScript program to check if three given numbers are increasing in strict mode or in soft mode.
Note: ```Strict mode``` -> 10, 15, 31 : ```Soft mode``` -> 24, 22, 31 or 22, 22, 31**

>JavaScript Code:
```javascript
function number_order(x, y, z) {
  if (y > x && z > y) {
    return "strict mode";
  } else if (z > y)
    return "Soft mode";
  else
    return "Undefinded";
}

console.log(number_order(10, 15, 31));
console.log(number_order(24, 22, 31));
console.log(number_order(50, 21, 15));
```

>ES6 Version:
```javascript
function number_order(x, y, z) {
  if (y > x && z > y) {
    return "strict mode";
  } else if (z > y)
    return "Soft mode";
  else
    return "Undefinded";
}

console.log(number_order(10, 15, 31));
console.log(number_order(24, 22, 31));
console.log(number_order(50, 21, 15));
```

>Result:
```javascript
strict mode
Soft mode
Undefinded
```

**42. Write a JavaScript program to check from three given numbers (non negative integers) that two or all of them have the same rightmost digit.**

>JavaScript Code:
```javascript
function same_last_digit(p, q, r) {
  return (p % 10 === q % 10) ||
    (p % 10 === r % 10) ||
    (q % 10 === r % 10);

}

console.log(same_last_digit(22, 32, 42));
console.log(same_last_digit(102, 302, 2));
console.log(same_last_digit(20, 22, 45));
```

>ES6 Version:
```javascript
function same_last_digit(p, q, r) {
  return (p % 10 === q % 10) ||
    (p % 10 === r % 10) ||
    (q % 10 === r % 10);

}

console.log(same_last_digit(22, 32, 42));
console.log(same_last_digit(102, 302, 2));
console.log(same_last_digit(20, 22, 45));
```

>Result:
```javascript
true
true
false
```

**43. Write a JavaScript program to check from three given integers that if a number is greater than or equal to 20 and less than one of the others**

>JavaScript Code:
```javascript
function lessby20_others(x, y, z) {
  return (x >= 20 && (x < y || x < z)) ||
    (y >= 20 && (y < x || y < z)) ||
    (z >= 20 && (z < y || z < x));
}
console.log(lessby20_others(23, 45, 10));
console.log(lessby20_others(23, 23, 10));
console.log(lessby20_others(21, 66, 75));
```

>Result:
```javascript
true
false
true
```

**44. Write a JavaScript program to check two given integer values and return true if one of the number is 15 or if their sum or difference is 15.**

>JavaScript Code:
```javascript
function test_nmuber(x, y) {
  return (x === 15 || y === 15 || x + y === 15 || Math.abs(x - y) === 15);
}

console.log(test_nmuber(15, 9));
console.log(test_nmuber(25, 15));
console.log(test_nmuber(7, 8));
console.log(test_nmuber(25, 10));
console.log(test_nmuber(5, 9));
console.log(test_nmuber(7, 9));
console.log(test_nmuber(9, 25));
```

>ES6 Version:
```javascript
function test_nmuber(x, y) {
  return (x === 15 || y === 15 || x + y === 15 || Math.abs(x - y) === 15);
}

console.log(test_nmuber(15, 9));
console.log(test_nmuber(25, 15));
console.log(test_nmuber(7, 8));
console.log(test_nmuber(25, 10));
console.log(test_nmuber(5, 9));
console.log(test_nmuber(7, 9));
console.log(test_nmuber(9, 25));
```

>Result:
```javascript
true
true
true
true
false
false
false
```

**45. Write a JavaScript program to check two given non-negative integers and if one of the number (not both) is multiple of 7 or 11**

>JavaScript Code:
```javascript
function check_numbers(x) {
  return ((x % 7 === 0 || x % 11 === 0) && (x % 7 !== x % 11));
}
console.log(check_numbers(14));
console.log(check_numbers(22));
console.log(check_numbers(17));
console.log(check_numbers(120));
```

>ES6 Version:
```javascript
function check_numbers(x) {
  return ((x % 7 === 0 || x % 11 === 0) && (x % 7 !== x % 11));
}
console.log(check_numbers(14));
console.log(check_numbers(22));
console.log(check_numbers(17));
console.log(check_numbers(120));
```

>Result:
```javascript
true
true
false
false
```

**46. Write a JavaScript program to check if a number in the range 40..10000 presents in two number (in same range)**
- For example 40 presents in 400 and 4000.

>JavaScript Code:
```javascript
function test_digit(x, y) {
  let x_div = parseInt(x / 40),
    x_mod = x % 40,
    y_div = parseInt(y / 40),
    y_mod = y % 40;
  return x_div === y_div || x_mod === y_mod ||
    x_div === y_mod || x_mod === y_div;
}

console.log(test_digit(40, 4000));
console.log(test_digit(80, 320));
console.log(test_digit(89, 4000));
```

>ES6 Version:
```javascript
function test_digit(x, y) {
  let x_div = parseInt(x / 40);
  let x_mod = x % 40;
  let y_div = parseInt(y / 40);
  let y_mod = y % 40;
  return x_div === y_div || x_mod === y_mod ||
    x_div === y_mod || x_mod === y_div;
}

console.log(test_digit(40, 4000));
console.log(test_digit(80, 320));
console.log(test_digit(89, 4000));
```

>Result:
```javascript
true
true
false
```

**47. Write a JavaScript program to reverse a given string**

- The ```split()``` method is used to split **(phân chia)** a string into an array of substrings, and returns the new array.
- The ```reverse()``` method reverses **(đảo ngược)** the order of the elements in an array.
- The ```join()``` method joins **(Kết hợp)** the elements of an array into a string, and returns the string.

>JavaScript Code:
```javascript
function string_reverse(str) {
  return str.split("").reverse().join("");
}

console.log(string_reverse("w3resource"));
console.log(string_reverse("www"));
console.log(string_reverse("JavaScript"));
```

>ES6 Version:
```javascript
function string_reverse(str) {
  return str.split("").reverse().join("");
}

console.log(string_reverse("w3resource"));
console.log(string_reverse("www"));
console.log(string_reverse("JavaScript"));
```

>Result:
```javascript
ecruoser3w
www
tpircSavaJ
```

**48. Write a JavaScript program to replace every character in a given string with the character following it in the alphabet.**
- The ```fromCharCode()``` method converts Unicode values into characters

>JavaScript Code:
```javascript
function LetterChanges(text) {
  //https://goo.gl/R8gn7u
  var s = text.split('');
  for (var i = 0; i < s.length; i++) {
    // Caesar cipher
    switch (s[i]) {
      case ' ':
        break;
      case 'z':
        s[i] = 'a';
        break;
      case 'Z':
        s[i] = 'A';
        break;
      default:
        s[i] = String.fromCharCode(1 + s[i].charCodeAt(0));
    }

    // Upper-case vowels
    switch (s[i]) {
      case 'a':
      case 'e':
      case 'i':
      case 'o':
      case 'u':
        s[i] = s[i].toUpperCase();
    }
  }
  return s.join('');
}
console.log(LetterChanges("PYTHON"));
console.log(LetterChanges("W3R"));
console.log(LetterChanges("php"));
```
>Result:
```javascript
QZUIPO
X4S
qIq
```

**49. Write a JavaScript program to capitalize the first letter of each word of a given string.**
The ```substr()```; ```substr(start, length)``` method extracts parts of a string, beginning at the character at the specified position, and returns the specified number of characters. Phương thức substr () trích ra các phần của một chuỗi, bắt đầu từ ký tự tại vị trí đã chỉ định và trả về số ký tự được chỉ định. 

```
var str = "Hello world!"; 
var res = str.substr(0, 1);
Result --> H
```
```
var str = "Hello world!";
var res = str.substr(2);
Result --> llo world!
```

>JavaScript Code:
```javascript
function capital_letter(str) {
  str = str.split(" ");

  for (var i = 0, x = str.length; i < x; i++) {
    str[i] = str[i][0].toUpperCase() + str[i].substr(1);
  }

  return str.join(" ");
}

console.log(capital_letter("Write a JavaScript program to capitalize the first letter of each word of a given string."));
```

>ES6 Version:
```javascript
function capital_letter(str) {
  str = str.split(" ");

  for (let i = 0, x = str.length; i < x; i++) {
    str[i] = str[i][0].toUpperCase() + str[i].substr(1);
  }

  return str.join(" ");
}

console.log(capital_letter("Write a JavaScript program to capitalize the first letter of each word of a given string."));
```

>Result:
```javascript
Write A JavaScript Program To Capitalize The First Letter Of Each Word Of A Given String.
```

**50. Write a JavaScript program to convert a given number to hours and minutes.**
- The ```floor()``` method rounds a number DOWNWARDS to the nearest integer, and returns the result.
- Phương thức ```floor ()``` làm tròn một số DOWNWARDS tới số nguyên gần nhất, và trả về kết quả.

>JavaScript Code:
```javascript
function time_convert(num) {
  var hours = Math.floor(num / 60);
  var minutes = num % 60;
  return hours + ":" + minutes;
}

console.log(time_convert(71));
console.log(time_convert(450));
console.log(time_convert(1441));
```

>ES6 Version:
```javascript
function time_convert(num) {
  const hours = Math.floor(num / 60);
  const minutes = num % 60;
  return `${hours}:${minutes}`;
}

console.log(time_convert(71));
console.log(time_convert(450));
console.log(time_convert(1441));
```

>Result:
```javascript
1:11
7:30
24:1
```

**51. Write a JavaScript program to convert the letters of a given string in alphabetical order.**
- The ```sort()``` method sorts the items of an array.
- The sort order can be either alphabetic or numeric, and either ascending (up) or descending (down).

>JavaScript Code:
```javascript
function alphabet_Soup(str) {
  return str.split("").sort().join("");
}

console.log(alphabet_Soup("Python"));
console.log(alphabet_Soup("Exercises"));
```

>ES6 Version:
```javascript
function alphabet_Soup(str) {
  return str.split("").sort().join("");
}

console.log(alphabet_Soup("Python"));
console.log(alphabet_Soup("Exercises"));
```

>Result:
```javascript
Phnoty
Eceeirssx
```

**52. Write a JavaScript program to check if the characters a and b are separated by exactly 3 places anywhere (at least once) in a given string.**
- The ```test(string)``` method tests for a match in a string.
- The ```string``` to be searched
>JavaScript Code:
```javascript
function ab_Check(str) {
  return (/a...b/).test(str) || (/b...a/).test(str);
}

console.log(ab_Check("Chainsbreak"));
console.log(ab_Check("pane borrowed"));
console.log(ab_Check("abCheck"));
```

>ES6 Version:
```javascript
function ab_Check(str) {
  return (/a...b/).test(str) || (/b...a/).test(str);
}

console.log(ab_Check("Chainsbreak"));
console.log(ab_Check("pane borrowed"));
console.log(ab_Check("abCheck"));
```

>Result:
```javascript
true
true
false
```

**53. Write a JavaScript program to count the number of vowels of a given string.**
- The ```replace()``` method searches a string for a specified value, or a regular expression, and returns a new string where the specified values are replaced.

>JavaScript Code:
```javascript
function vowel_Count(str) {
  return str.replace(/[^aeiou]/g, "").length;
}
console.log(vowel_Count("Python"));
console.log(vowel_Count("w3resource.com"));
```

>ES6 Version:
```javascript
function vowel_Count(str) {
  return str.replace(/[^aeiou]/g, "").length;
}
console.log(vowel_Count("Python"));
console.log(vowel_Count("w3resource.com"));
```

>Result:
```javascript
1
5
```

**54. Write a JavaScript program to check if a given string contains equal number of p's and t's present.**

>JavaScript Code:
```javascript
function equal_pt(str) {
  var str_p = str.replace(/[^p]/g, "");
  var str_s = str.replace(/[^s]/g, "");
  var p_num = str_p.length;
  var s_num = str_s.length;
  return p_num === s_num;
}
console.log(equal_pt("paatpss"));
console.log(equal_pt("paatps"));
```

>ES6 Version:
```javascript
function equal_pt(str) {
  const str_p = str.replace(/[^p]/g, "");
  const str_s = str.replace(/[^s]/g, "");
  const p_num = str_p.length;
  const s_num = str_s.length;
  return p_num === s_num;
}
console.log(equal_pt("paatpss"));
console.log(equal_pt("paatps"));
```

>Result:
```javascript
true
false
```

**55. Write a JavaScript program to divide two positive numbers and return a string with properly formatted commas**
- Viết một chương trình JavaScript để chia hai số dương và trả về một chuỗi với các dấu phẩy được định dạng chính xác.
- The ```toString()``` method converts a number to a string.
- The ```splice()``` method adds/removes items to/from an array, and returns the removed item(s).

>JavaScript Code:
```javascript
n1 = 80;
n2 = 6;
var div = Math.round(n1 / n2).toString(),
  result_array = div.split("");
if (div >= 1000) {
  for (var i = div.length - 3; i > 0; i -= 3) {
    result_array.splice(i, 0, ",");
  }
  result_array;
}
console.log(result_array);
```
>Result:
```javascript
["1","3"]
```

**56.Write a JavaScript program to create a new string of specified copies (positive number) of a given string.**
- The ```repeat()``` method returns a new string with a specified number of copies of the string it was called on.

>JavaScript Code:
```javascript
function string_copies(str, n) {
  if (n < 0)
    return false;
  else
    return str.repeat(n);
}
console.log(string_copies("abc", 5));
console.log(string_copies("abc", 0));
console.log(string_copies("abc", -2));
```

>ES6 Version:
```javascript
function string_copies(str, n) {
  if (n < 0)
    return false;
  else
    return str.repeat(n);
}
console.log(string_copies("abc", 5));
console.log(string_copies("abc", 0));
console.log(string_copies("abc", -2));
```

>Result:
```javascript
abcabcabcabcabc

false
```

**57.Write a JavaScript program to create a new string of 4 copies of the last 3 characters of a given original string. The length of the given string must be 3 and above.**


>JavaScript Code:
```javascript
function newstring(str) {
  if (str.length >= 3) {
    result_str = str.substring(str.length - 3);
    return result_str + result_str + result_str + result_str;
  } else
    return false;
}
console.log(newstring("Python 3.0"));
console.log(newstring("JS"));
console.log(newstring("JavaScript"));
```

>ES6 Version:
```javascript
function newstring(str) {
  if (str.length >= 3) {
    result_str = str.substring(str.length - 3);
    return result_str + result_str + result_str + result_str;
  } else
    return false;
}
console.log(newstring("Python 3.0"));
console.log(newstring("JS"));
console.log(newstring("JavaScript"));
```

>Result:
```javascript
3.03.03.03.0
false
iptiptiptipt
```

**58.Write a JavaScript program to extract the first half of a string of even length.**
- Viết một chương trình JavaScript để trích xuất nửa đầu của một chuỗi thậm chí là chiều dài.

>JavaScript Code:
```javascript
function first_half(str) {
  if (str.length % 2 == 0) {
    return str.slice(0, str.length / 2);
  }
  return str;
}
console.log(first_half("Python"));
console.log(first_half("JavaScript"));
console.log(first_half("PHP"));
```

>ES6 Version:
```javascript
function first_half(str) {
  if (str.length % 2 == 0) {
    return str.slice(0, str.length / 2);
  }
  return str;
}
console.log(first_half("Python"));
console.log(first_half("JavaScript"));
console.log(first_half("PHP"));
```

>Result:
```javascript
Pyt
JavaS
PHP
```

**59.Write a JavaScript program to create a new string without the first and last character of a given string**
- Viết một chương trình JavaScript để tạo một chuỗi mới mà không có ký tự đầu tiên và cuối cùng của một chuỗi nhất định

>JavaScript Code:
```javascript
function without_first_end(str) {
  return str.substring(1, str.length - 1);
}
console.log(without_first_end('JavaScript'));
console.log(without_first_end('JS'));
console.log(without_first_end('PHP'));
```

>ES6 Version:
```javascript
function without_first_end(str) {
  return str.substring(1, str.length - 1);
}
console.log(without_first_end('JavaScript'));
console.log(without_first_end('JS'));
console.log(without_first_end('PHP'));
```

>Result:
```javascript
avaScrip

H
```

**60. Write a JavaScript program to concatenate two strings except their first character.**
- Viết một chương trình JavaScript để nối hai chuỗi trừ nhân vật đầu tiên của họ.

>JavaScript Code:
```javascript
function concatenate(str1, str2) {
  str1 = str1.substring(1, str1.length);
  str2 = str2.substring(1, str2.length);
  return str1 + str2;
}

console.log(concatenate("PHP", "JS"));
console.log(concatenate("A", "B"));
console.log(concatenate("AA", "BB"));
```

>ES6 Version:
```javascript
function concatenate(str1, str2) {
  str1 = str1.substring(1, str1.length);
  str2 = str2.substring(1, str2.length);
  return str1 + str2;
}

console.log(concatenate("PHP","JS"));
console.log(concatenate("A","B"));
console.log(concatenate("AA","BB"));
```

>Result:
```javascript
HPS

AB
```

**61.Write a JavaScript program to move last three character to the start of a given string. The string length must be greater or equal to three**
- Viết một chương trình JavaScript để di chuyển ba ký tự cuối cùng đến đầu của một chuỗi nhất định. Chiều dài chuỗi phải lớn hơn hoặc bằng ba
- The ```slice()``` method returns the selected elements in an array, as a new array object.
- Use negative numbers to select from the end of an array(Sử dụng số âm để chọn từ cuối mảng).

>JavaScript Code:
```javascript
function right_three(str) {
  if (str.length > 1) {
    return str.slice(-3) + str.slice(0, -3);
  }
  return str;
}
console.log(right_three("Python"));
console.log(right_three("JavaScript"));
console.log(right_three("Hi"));
```

>ES6 Version:
```javascript
function right_three(str) {
  if (str.length > 1) {
    return str.slice(-3) + str.slice(0, -3);
  }
  return str;
}
console.log(right_three("Python"));
console.log(right_three("JavaScript"));
console.log(right_three("Hi"));
```

>Result:
```javascript
honPyt
iptJavaScr
Hi
```

**62.Write a JavaScript program to create a string using the middle three characters of a given string of odd length. The string length must be greater or equal to three.**
- Viết một chương trình JavaScript để tạo ra một chuỗi bằng cách sử dụng ba ký tự giữa của một chuỗi cho trước có độ dài lẻ. Chiều dài chuỗi phải lớn hơn hoặc bằng ba.

>JavaScript Code:
```javascript
function middle_three(str) {
  if (str.length % 2 != 0) {
    mid = (str.length + 1) / 2;
    return str.slice(mid - 2, mid + 1);
  }
  return str;
}
console.log(middle_three('abcdefg'));
console.log(middle_three('HTML5'));
console.log(middle_three('Python'));
console.log(middle_three('PHP'));
console.log(middle_three('Exercises'));
```

>ES6 Version:
```javascript
function middle_three(str) {
  if (str.length % 2 != 0) {
    mid = (str.length + 1) / 2;
    return str.slice(mid - 2, mid + 1);
  }
  return str;
}
console.log(middle_three('abcdefg'));
console.log(middle_three('HTML5'));
console.log(middle_three('Python'));
console.log(middle_three('PHP'));
console.log(middle_three('Exercises'));
```

>Result:
```javascript
cde
TML
Python
PHP
rci
```

**63. Write a JavaScript program to concatenate two strings and return the result. If the length of the strings are not same then remove the characters from the longer string**
- Viết một chương trình JavaScript để nối hai chuỗi và trả về kết quả. Nếu độ dài của các chuỗi không giống nhau sau đó loại bỏ các ký tự từ chuỗi dài hơn
- ```Math.min(n1, n2, n3, ..., nX)```: One or more numbers to compare

>JavaScript Code:
```javascript
function str_con_cat(str1, str2) {
  const m = Math.min(str1.length, str2.length);
  return str1.substring(str1.length - m) + str2.substring(str2.length - m);
}

console.log(str_con_cat("Python", "JS"));
console.log(str_con_cat("ab", "cdef"));
```

>ES6 Version:
```javascript
function str_con_cat(str1, str2) {
  const m = Math.min(str1.length, str2.length);
  return str1.substring(str1.length - m) + str2.substring(str2.length - m);
}

console.log(str_con_cat("Python", "JS"));
console.log(str_con_cat("ab", "cdef"));
```

>Result:
```javascript
onJS
abef
```

**64.Write a JavaScript program to test if a string end with "Script". The string length must be greater or equal to 6**
- Viết một chương trình JavaScript để kiểm tra nếu một chuỗi kết thúc bằng "Script". Chiều dài chuỗi phải lớn hơn hoặc bằng 6

>JavaScript Code:
```javascript
function end_script(str) {
  if (str.substring(str.length - 6, str.length) == 'Script') {
    return true;
  } else {
    return false;
  }
}
console.log(end_script("JavaScript"));
console.log(end_script("Java Script"));
console.log(end_script("Java Scripts"));
```

>ES6 Version:
```javascript
function end_script(str) {
  if (str.substring(str.length - 6, str.length) == 'Script') {
    return true;
  } else {
    return false;
  }
}
console.log(end_script("JavaScript"));
console.log(end_script("Java Script"));
console.log(end_script("Java Scripts"));
```

>Result:
```javascript
true
true
false
```

**65.Write a JavaScript program to display the city name if the string begins with "Los" or "New" otherwise return blank.**
- Viết một chương trình JavaScript để hiển thị tên thành phố nếu chuỗi bắt đầu bằng "Los" hoặc "New" nếu không sẽ trở lại trạng thái trống.

>JavaScript Code:
```javascript
function city_name(str) {
  if (str.length >= 3 && ((str.substring(0, 3) == 'Los') || (str.substring(0, 3) == 'New'))){
    return str;
  }
  return '';
}
console.log(city_name("New York"));
console.log(city_name("Los Angeles"));
console.log(city_name("London"));
```

>ES6 Version:
```javascript
function city_name(str) {
  if (str.length >= 3 && ((str.substring(0, 3) == 'Los') || (str.substring(0, 3) == 'New'))){
    return str;
  }
  return '';
}
console.log(city_name("New York"));
console.log(city_name("Los Angeles"));
console.log(city_name("London"));
```

>Result:
```javascript
New York
Los Angeles
""
```

**66.Write a JavaScript program to create a new string from a given string, removing the first and last characters of the string if the first or last character are 'P'. Return the original string if the condition is not satisfied.**
- Viết một chương trình JavaScript để tạo ra một chuỗi mới từ một chuỗi nhất định, loại bỏ các ký tự đầu tiên và cuối của chuỗi nếu ký tự đầu tiên hoặc cuối là 'P'. Trả về chuỗi ban đầu nếu tình trạng không hài lòng.
- ```str.length```: độ dài các phần tử trong chuỗi.
- ```str.length - 1```: độ dài các phần tử trong chuỗi trừ ký tự cuối cùng.

>JavaScript Code:
```javascript
function nop(str) {
  let start_pos = 0;
  let end_pos = str.length;
  if (str.length > 0 && str.charAt(0) == 'P') {
    start_pos = 1;
  }
  if (str.length > 1 && str.charAt(str.length - 1) == 'P') {
    end_pos--;
  }
  return str.substring(start_pos, end_pos);
}
console.log(nop("PythonP"));
console.log(nop("Python"));
console.log(nop("JavaScript"));
```

>ES6 Version:
```javascript
function nop(str) {
  let start_pos = 0;
  let end_pos = str.length;
  if (str.length > 0 && str.charAt(0) == 'P') {
    start_pos = 1;
  }
  if (str.length > 1 && str.charAt(str.length - 1) == 'P') {
    end_pos--;
  }
  return str.substring(start_pos, end_pos);
}

console.log(nop("PythonP"));
console.log(nop("Python"));
console.log(nop("JavaScript"));
```

>Result:
```javascript
ython
ython
JavaScript
```

**67.Write a JavaScript program to create a new string taking the first and last n characters from a given string. The string length must be greater or equal to n**
- Viết một chương trình JavaScript để tạo một chuỗi mới lấy các ký tự n đầu tiên và cuối cùng từ một chuỗi nhất định. Chiều dài chuỗi phải lớn hơn hoặc bằng n

>JavaScript Code:
```javascript
function two_string(str, n) {
  first_part = str.substring(0, n);
  last_part = str.substring(str.length - n);
  return first_part + last_part;
}

console.log(two_string("JavaScript", 2));
console.log(two_string("JavaScript", 3));
```

>ES6 Version:
```javascript
function two_string(str, n) {
  first_part = str.substring(0, n);
  last_part = str.substring(str.length - n);
  return first_part + last_part;
}

console.log(two_string("JavaScript", 2));
console.log(two_string("JavaScript", 3));
```

>Result:
```javascript
Japt
Javipt
```

**68.Write a JavaScript program to compute the sum of three elements of a given array of integers of length 3**
- Viết một chương trình JavaScript để tính tổng của ba phần tử của một mảng các số nguyên có độ dài 3.

>JavaScript Code:
```javascript
function sum_three(nums) {
  return nums[0] + nums[1] + nums[2];
}

console.log(sum_three([10, 32, 20]));
console.log(sum_three([5, 7, 9]));
console.log(sum_three([0, 8, -11]));
```

>ES6 Version:
```javascript
function sum_three(nums) {
  return nums[0] + nums[1] + nums[2];
}

console.log(sum_three([10, 32, 20]));
console.log(sum_three([5, 7, 9]));
console.log(sum_three([0, 8, -11]));
```

>Result:
```javascript
62
21
-3
```

**69.Write a JavaScript program to rotate the elements left of a given array of integers of length 3**
- Viết một chương trình JavaScript để xoay các phần tử bên trái của một mảng các số nguyên có độ dài 3

>JavaScript Code:
```javascript
function rotate_elements_left(array) {
  return [array[1], array[2], array[0]];
}
console.log(rotate_elements_left([3, 4, 5]));
console.log(rotate_elements_left([0, -1, 2]));
console.log(rotate_elements_left([7, 6, 5]));
```

>ES6 Version:
```javascript
function rotate_elements_left(array) {
  return [array[1], array[2], array[0]];
}
console.log(rotate_elements_left([3, 4, 5]));
console.log(rotate_elements_left([0, -1, 2]));
console.log(rotate_elements_left([7, 6, 5]));
```

>Result:
```javascript
[4,5,3]
[-1,2,0]
[6,5,7]
```

**70.Write a JavaScript program to check if 1 appears in first or last position of a given array of integers. The array length must be greater or equal to 1**
- Viết một chương trình JavaScript để kiểm tra nếu 1 xuất hiện ở vị trí đầu tiên hoặc vị trí cuối cùng của một mảng số nguyên. Chiều dài mảng phải lớn hơn hoặc bằng 1

>JavaScript Code:
```javascript
function first_last_1(nums) {
  var end_pos = nums.length - 1;
  return nums[0] == 1 || nums[end_pos] == 1;
}


console.log(first_last_1([1, 3, 5]));
console.log(first_last_1([1, 3, 5, 1]));
console.log(first_last_1([2, 4, 6]));
```

>ES6 Version:
```javascript
function first_last_1(nums) {
  const end_pos = nums.length - 1;
  return nums[0] == 1 || nums[end_pos] == 1;
}


console.log(first_last_1([1, 3, 5]));
console.log(first_last_1([1, 3, 5, 1]));
console.log(first_last_1([2, 4, 6]));
```

>Result:
```javascript
true
true
false
```
**71. Write a JavaScript program to check if the first and last elements are equal of a given array of integers length 3**
- Viết một chương trình JavaScript để kiểm tra xem các phần tử đầu tiên và cuối cùng có bằng nhau không, một mảng các số nguyên có độ dài 3.

>JavaScript Code:
```javascript
function first_last_same(nums) {
  var end = nums.length - 1;
  if (nums.length >= 1) {
    return nums[0] == nums[end];
  } else { return false; }
}

console.log(first_last_same([10, 20, 30]));
console.log(first_last_same([10, 20, 30, 10]));
console.log(first_last_same([20, 20, 20]));
```

>ES6 Version:
```javascript
function first_last_same(nums) {
  const end = nums.length - 1;
  if (nums.length >= 1) {
    return nums[0] == nums[end];
  } else { return false; }
}

console.log(first_last_same([10, 20, 30]));
console.log(first_last_same([10, 20, 30, 10]));
console.log(first_last_same([20, 20, 20]));
```

>Result:
```javascript
false
true
true
```

**72.Write a JavaScript program to reverse the elements of a given array of integers length 3.**

- Viết một chương trình JavaScript để đảo các phần tử của một mảng các số nguyên dài nhất 3.
- ```map(currentValue, index, arr)```: The ```map()``` method creates a new array with the results of calling a function for every array element--> Phương thức ```map ()``` tạo một mảng mới với kết quả gọi một hàm cho mỗi phần tử mảng
- The ```map()``` method calls the provided function once for each element in an array, in order.
--> Phương thức ```map()``` gọi hàm đã cung cấp một lần cho mỗi phần tử trong một mảng theo thứ tự.
- ```currentValue```: The value of the current element
- ```index```: The array index of the current element
- ```arr```: The array object the current element belongs to(Mảng đối tượng phần tử hiện tại thuộc về)

>JavaScript Code:
```javascript
function reverse3(array) {
    return array.map((element, idx, arr) => arr[(arr.length - 1) - idx]);
}

console.log(reverse3([5, 4, 3])); 
console.log(reverse3([1, 0, -1]));  
console.log(reverse3([2, 3, 1]));
```

>ES6 Version:
```javascript
function reverse3(array) {
    return array.map((element, idx, arr) => arr[(arr.length - 1) - idx]);
}

console.log(reverse3([5, 4, 3])); 
console.log(reverse3([1, 0, -1]));  
console.log(reverse3([2, 3, 1]));
Copy
Live Demo:
```

>Result:
```javascript
false
true
true
```

**73. Write a JavaScript program to find the larger value between the first or last and set all the other elements with that value. Display the new array.**
- Viết một chương trình JavaScript để tìm giá trị lớn hơn giữa đầu tiên hoặc cuối cùng và đặt tất cả các phần tử khác có giá trị đó. Hiển thị mảng mới.

>JavaScript Code:
```javascript
function all_max(nums) {
  var max_val = nums[0] > nums[2] ? nums[0] : nums[2];
  nums[0] = max_val;
  nums[1] = max_val;
  nums[2] = max_val;
  return nums;
}
console.log(all_max([20, 30, 40]));
console.log(all_max([-7, -9, 0]));
console.log(all_max([12, 10, 3]));
```

>ES6 Version:
```javascript
function all_max(nums) {
  const max_val = nums[0] > nums[2] ? nums[0] : nums[2];
  nums[0] = max_val;
  nums[1] = max_val;
  nums[2] = max_val;
  return nums;
}
console.log(all_max([20, 30, 40]));
console.log(all_max([-7, -9, 0]));
console.log(all_max([12, 10, 3]));
```

>Result:
```javascript
[40,40,40]
[0,0,0]
[12,12,12]
```

**74. Write a JavaScript program to create a new array taking the middle elements of the two arrays of integer and each length 3.**
- Viết một chương trình JavaScript để tạo một mảng mới lấy các phần tử trung gian của hai mảng số nguyên và mỗi chiều dài 3.

>JavaScript Code:
```javascript
function middle_elements(a, b) {
  var new_array = []
  new_array.push(a[1], b[1]);
  return new_array;
}
console.log(middle_elements([1, 2, 3], [1, 5, 6]));
console.log(middle_elements([3, 3, 3], [2, 8, 0]));
console.log(middle_elements([4, 2, 7], [2, 4, 5]));
```

>ES6 Version:
```javascript
function middle_elements(a, b) {
  const new_array = [];
  new_array.push(a[1], b[1]);

  return new_array;
}
console.log(middle_elements([1, 2, 3], [1, 5, 6]));
console.log(middle_elements([3, 3, 3], [2, 8, 0]));
console.log(middle_elements([4, 2, 7], [2, 4, 5]));
```

>Result:
```javascript
[2,5]
[3,8]
[2,4]
```

**75. Write a JavaScript program to create a new array taking the first and last elements from a given array of integers and length must be greater or equal to 1.**
- Viết một chương trình JavaScript để tạo một mảng mới lấy các phần tử đầu tiên và cuối cùng từ một mảng số nguyên và chiều dài cho trước phải lớn hơn hoặc bằng 1.

>JavaScript Code:
```javascript
function started(nums) {
  var array1 = [];
  array1.push(nums[0], nums[nums.length - 1]);

  return array1;
}
console.log(started([20, 20, 30]));
console.log(started([5, 2, 7, 8]));
console.log(started([17, 12, 34, 78]));
```

>ES6 Version:
```javascript
function started(nums) {
  const array1 = [];
  array1.push(nums[0], nums[nums.length - 1]);

  return array1;
}
console.log(started([20, 20, 30]));
console.log(started([5, 2, 7, 8]));
console.log(started([17, 12, 34, 78]));
```

>Result:
```javascript
[20,30]
[5,8]
[17,78]
```

**76. Write a JavaScript program to test if an array of integers of length 2 contains 1 or a 3.**
- Viết một chương trình JavaScript để kiểm tra nếu một mảng các số nguyên có độ dài 2 chứa 1 hoặc số 3.
- ```string.indexOf(searchValue[, fromIndex])```: 
  + The ```indexOf()``` method returns the position of the first occurrence of a specified value in a string(Phương thức indexOf () trả về vị trí của sự xuất hiện đầu tiên của một giá trị được chỉ định trong một chuỗi.).
  + This method returns -1 if the value to search for never occurs.
  + ```searchValue``` − Một chuỗi biểu diễn giá trị để tìm kiếm.
  + ```fromIndex``` − Vị trí trong chuỗi đang gọi để bắt đầu tìm kiếm. Nó có thể là bất kỳ giá trị integer nào giữa 0 và độ dài chuỗi. Giá trị mặc định là 0.

>JavaScript Code:
```javascript
function contins13(nums) {
  if (nums.indexOf(1) != -1 || nums.indexOf(3) != -1) {
    return true
  } else {
    return false
  }
}

console.log(contins13([1, 5]));
console.log(contins13([2, 3]));
console.log(contins13([7, 5]));
```

>ES6 Version:
```javascript
function contins13(nums) {
  if (nums.includes(1) || nums.includes(3)) {
    return true
  } else {
    return false
  }
}

console.log(contins13([1, 5]));
console.log(contins13([2, 3]));
console.log(contins13([7, 5]));
```

>Result:
```javascript
true
true
false
```

**77. Write a JavaScript program to test if an array of integers of length 2 does not contain 1 or a 3.**
- Viết một chương trình JavaScript để kiểm tra xem một dãy các số nguyên có độ dài 2 không chứa 1 hoặc số 3.
- ```indexOf()```: dùng cho mảng
>JavaScript Code:
```javascript
function is13(nums) {
  if (nums.indexOf(1) == -1 && nums.indexOf(3) == -1) {
    return true;
  } else {
    return false;
  }
}
console.log(is13([7, 8]));
console.log(is13([3, 2]));
console.log(is13([0, 1]));
```

>ES6 Version:
```javascript
function is13(nums) {
  if (!nums.includes(1) && !nums.includes(3)) {
    return true;
  } else {
    return false;
  }
}

console.log(is13([7, 8]));
console.log(is13([3, 2]));
console.log(is13([0, 1]));
```

>Result:
```javascript
true
false
false
```

**78. Write a JavaScript program to test if a given array of integers contains 30 and 40 twice. The array length should be 0, 1, or 2.**
- Viết một chương trình JavaScript để kiểm tra xem một mảng các số nguyên đã cho có chứa 30 và 40 hai lần. Chiều dài của mảng là 0, 1, hoặc 2.

>JavaScript Code:
```javascript
function twice3040(arra1) {
  let a = arra1[0],
    b = arra1[1];
  return (a === 30 && a === 30) || (b === 40 && b === 40);
}

console.log(twice3040([30, 30]));
console.log(twice3040([40, 40]));
console.log(twice3040([20, 20]));
console.log(twice3040([30]));
```

>ES6 Version:
```javascript
function twice3040(arra1) {
  let a = arra1[0];
  let b = arra1[1];
  return (a === 30 && a === 30) || (b === 40 && b === 40);
}

console.log(twice3040([30, 30]));
console.log(twice3040([40, 40]));
console.log(twice3040([20, 20]));
console.log(twice3040([30]));
```

>Result:
```javascript
true
true
false
true
```

**79. Write a JavaScript program to swap the first and last elements of a given array of integers. The array length should be at least 1.**
- Viết một chương trình JavaScript để hoán đổi các phần tử đầu tiên và cuối cùng của một mảng số nguyên. Chiều dài của mảng ít nhất phải là 1.

>JavaScript Code:
```javascript
function swap(arra) {
  [arra[0], arra[arra.length - 1]] = [arra[arra.length - 1], arra[0]];
  return arra;
}
console.log(swap([1, 2, 3, 4]));
console.log(swap([0, 2, 1]));
console.log(swap([3]));
```

>ES6 Version:
```javascript
function swap(arra) {
  [arra[0], arra[arra.length - 1]] = [arra[arra.length - 1], arra[0]];
  return arra;
}
console.log(swap([1, 2, 3, 4]));
console.log(swap([0, 2, 1]));
console.log(swap([3]));
```

>Result:
```javascript
[4,2,3,1]
[1,2,0]
[3]
```

**80. Write a JavaScript program to add two digits of a given positive integer of length two.**
- Viết một chương trình JavaScript để thêm hai chữ số của một số nguyên dương dương nhất định có chiều dài hai.

>JavaScript Code:
```javascript
function add_two_digits(n) {
  return n % 10 + Math.floor(n / 10);
}
console.log(add_two_digits(25))
console.log(add_two_digits(50))
```

>ES6 Version:
```javascript
function add_two_digits(n) {
  return n % 10 + Math.floor(n / 10);
}
console.log(add_two_digits(25))
console.log(add_two_digits(50))
```

>Result:
```javascript
7
5
```

**81. Write a JavaScript to add two positive integers without carry**
- Viết một JavaScript để thêm hai số nguyên dương mà không mang theo.

>JavaScript Code:
```javascript
function add_two_int_without_carrying(n1, n2) {
  var result = 0,
    x = 1;
  while (n1 > 0 && n2 > 0) {
    result += x * ((n1 + n2) % 10);
    n1 = Math.floor(n1 / 10);
    n2 = Math.floor(n2 / 10);
    x *= 10;
  }
  return result;
}
console.log(add_two_int_without_carrying(222, 911))
console.log(add_two_int_without_carrying(200, 900))
```

>ES6 Version:
```javascript
function add_two_int_without_carrying(n1, n2) {
  let result = 0;
  let x = 1;
  while (n1 > 0 && n2 > 0) {
    result += x * ((n1 + n2) % 10);
    n1 = Math.floor(n1 / 10);
    n2 = Math.floor(n2 / 10);
    x *= 10;
  }
  return result;
}
console.log(add_two_int_without_carrying(222, 911))
console.log(add_two_int_without_carrying(200, 900))
```

>Result:
```javascript
133
100
```

**82. Write a JavaScript to find the longest string from an given array of strings.**
- Viết một JavaScript để tìm chuỗi dài nhất từ một mảng các chuỗi.
- ```filter()```: The filter() method creates an array filled with all array elements that pass a test (provided as a function). Phương thức filter () tạo ra một mảng chứa đầy các phần tử mảng đi qua một bài kiểm tra (cung cấp như một hàm).
- ```filter()```:  does not execute the function for array elements without values.(Không thực thi function khi các phần tử array ko có giá trị)
- ```array.filter(function(currentValue, index, arr), thisValue)```: 
  + ```currentValue```: The value of the current element(Gía trị của phần tử hiện tại)
  + ```index```: The array index of the current element(Chỉ số mảng của phần tử hiện tại)
  + ```arr```: The array object the current element belongs to(Mảng đối tượng của phần tử hiện tại)
  + ```thisValue```: A value to be passed to the function to be used as its "this" value. If this parameter is empty, the value "undefined" will be passed as its "this" value(Một giá trị được chuyển đến hàm được sử dụng làm giá trị "này". Nếu tham số này rỗng, giá trị "không xác định" sẽ được chuyển thành giá trị "this")
- The ```max()``` method returns the number with the highest value.

>JavaScript Code:
```javascript
function longest_string(str_ara) {
  var max = str_ara[0].length;
  str_ara.map(v => max = Math.max(max, v.length));
  result = str_ara.filter(v => v.length == max);
  return result;
}
console.log(longest_string(['a', 'aa', 'aaa', 'aaaaa', 'aaaa']))
```

>ES6 Version:
```javascript
function longest_string(str_ara) {
  let max = str_ara[0].length;
  str_ara.map(v => max = Math.max(max, v.length));
  result = str_ara.filter(v => v.length == max);
  return result;
}
console.log(longest_string(['a', 'aa', 'aaa', 'aaaaa','aaaa']))
```

>Result:
```javascript
["aaaaa"]
```

**83. Write a JavaScript to replace each character of a given string by the next one in the English alphabet.**
- Viết mã JavaScript để thay thế mỗi ký tự của một chuỗi cho trước bằng một chữ cái tiếp theo trong bảng chữ cái tiếng Anh.
- ```charCodeAt```: The charCodeAt() method returns the Unicode of the character at the specified index in a string. (Phương thức charCodeAt () trả về Unicode của ký tự tại index được chỉ định trong một chuỗi.)
>JavaScript Code:
```javascript
function alphabet_char_Shift(str) {
  var all_chars = str.split("");
  for (var i = 0; i < all_chars.length; i++) {
    var n = all_chars[i].charCodeAt() - 'a'.charCodeAt();
    n = (n + 1) % 26;
    all_chars[i] = String.fromCharCode(n + 'a'.charCodeAt());
  }
  return all_chars.join("");
}
console.log(alphabet_char_Shift("abcdxyz"))
```

>ES6 Version:
```javascript
function alphabet_char_Shift(str) {
  const all_chars = str.split("");
  for (let i = 0; i < all_chars.length; i++) {
    let n = all_chars[i].charCodeAt() - 'a'.charCodeAt();
    n = (n + 1) % 26;
    all_chars[i] = String.fromCharCode(n + 'a'.charCodeAt());
  }
  return all_chars.join("");
}
console.log(alphabet_char_Shift("abcdxyz"))
```

>Result:
```javascript
bcdeyza
```

**84. Write a JavaScript code to divide an given array of positive integers into two parts. First element goes to first part, second element goes to second part, and third element goes to first part and so on. Now compute the sum of two parts and store into an array of size two.**
- Viết mã JavaScript để chia một mảng các số nguyên dương cho hai mảng. Phần tử thứ nhất đi đến phần thứ nhất, phần thứ hai đi đến phần thứ hai, và phần thứ ba đi đến phần đầu tiên và vân vân. Bây giờ tính tổng của hai phần và lưu trữ vào một mảng của kích thước hai.

>JavaScript Code:
```javascript
function alternate_Sums(arr) {
  var result = [0, 0];
  for (var i = 0; i < arr.length; i++) {
    if (i % 2) result[1] += arr[i];
    else
      result[0] += arr[i];
  }
  return result
}

console.log(alternate_Sums([1, 2, 3, 4, 5, 6]))
```

>ES6 Version:
```javascript
function alternate_Sums(arr) {
  const result = [0, 0];
  for (let i = 0; i < arr.length; i++) {
    if (i % 2) result[1] += arr[i];
    else
      result[0] += arr[i];
  }
  return result
}

console.log(alternate_Sums([1, 2, 3, 4, 5, 6]))
```

>Result:
```javascript
[9,12]
```

**85. Write a JavaScript program to find the types of a given array.**
- Viết một chương trình JavaScript để tìm các kiểu của mảng.
Types of angles:
• Acute angle: An angle between 0 and 90 degrees. - Góc cấp: Một góc từ 0 đến 90 độ.
• Right angle: An 90 degree angle. - Góc phải: Góc 90 độ.
• Obtuse angle: An angle between 90 and 180 degrees. - Góc nghiêng: góc 90 đến 180 độ.
• Straight angle: A 180 degree angle. Góc thẳng: - Góc 180 độ.


>JavaScript Code:
```javascript
function angle_Type(angle) {
  if (angle < 90) {
    return "Acute angle.";
  }
  if (angle === 90) {
    return "Right angle.";
  }
  if (angle < 180) {
    return "Obtuse angle.";
  }
  return "Straight angle.";
}

console.log(angle_Type(47))
console.log(angle_Type(90))
console.log(angle_Type(145))
console.log(angle_Type(180))
```

>ES6 Version:
```javascript
function angle_Type(angle) {
  if (angle < 90) {
    return "Acute angle.";
  }
  if (angle === 90) {
    return "Right angle.";
  }
  if (angle < 180) {
    return "Obtuse angle.";
  }
  return "Straight angle.";
}

console.log(angle_Type(47))
console.log(angle_Type(90))
console.log(angle_Type(145))
console.log(angle_Type(180))
```

>Result:
```javascript
Acute angle.
Right angle.
Obtuse angle.
Straight angle.
```

**86. Write a JavaScript program to check whether two arrays of integers and same length are similar or not. The arrays will be similar if one array can be obtained from another array by swapping at most one pair of elements.**
- Viết một chương trình JavaScript để kiểm tra xem hai mảng số nguyên và cùng độ dài có tương tự hay không. Các mảng sẽ giống nhau nếu một mảng có thể được lấy từ mảng khác bằng cách trao đổi nhiều nhất một cặp phần tử.

>JavaScript Code:
```javascript
function array_checking(arra1, arra2) {
  for (var i = 0; i < arra1.length; i++) {
    for (var j = i; j < arra1.length; j++) {
      var result = true,
        temp = arra1[i];
      arra1[i] = arra1[j];
      arra1[j] = temp;
      for (var k = 0; k < arra1.length; k++) {
        if (arra1[k] !== arra2[k]) {
          result = false;
          break;
        }
      }
      if (result) {
        return true;
      }
      arra1[j] = arra1[i];
      arra1[i] = temp;
    }
  }
  return false;
}
console.log(array_checking([10, 20, 30], [10, 20, 30]))
console.log(array_checking([10, 20, 30], [30, 10, 20]))
console.log(array_checking([10, 20, 30, 40], [10, 30, 20, 40]))
```

>ES6 Version:
```javascript
function array_checking(arra1, arra2) {
  for (let i = 0; i < arra1.length; i++) {
    for (let j = i; j < arra1.length; j++) {
      let result = true;
      const temp = arra1[i];
      arra1[i] = arra1[j];
      arra1[j] = temp;
      for (let k = 0; k < arra1.length; k++) {
        if (arra1[k] !== arra2[k]) {
          result = false;
          break;
        }
      }
      if (result) {
        return true;
      }
      arra1[j] = arra1[i];
      arra1[i] = temp;
    }
  }
  return false;
}
console.log(array_checking([10, 20, 30], [10, 20, 30]))
console.log(array_checking([10, 20, 30], [30, 10, 20]))
console.log(array_checking([10, 20, 30, 40], [10, 30, 20, 40]))
```

>Result:
```javascript
true
false
true
```

**87. Write a JavaScript program to check whether two given integers are similar or not, if a given divisor divides both integers and it does not divide either.**
- Viết một chương trình JavaScript để kiểm tra xem có hai số nguyên tương đương hay không, nếu một ước số chia cho cả hai số nguyên và nó không phân chia hai.

>JavaScript Code:
```javascript
function checking_numbers(x, y, divisor) {
  if (x % divisor === 0 && y % divisor === 0 || x % divisor !== 0 && y % divisor !==
    0) {
    return true;
  }
  return false;
}
console.log(checking_numbers(10, 25, 5))
console.log(checking_numbers(10, 20, 5))
console.log(checking_numbers(10, 20, 4))
```

>ES6 Version:
```javascript
function checking_numbers(x, y, divisor) {
  if (x % divisor === 0 && y % divisor === 0 || x % divisor !== 0 && y % divisor !==
    0) {
    return true;
  }
  return false;
}
console.log(checking_numbers(10, 25, 5))
console.log(checking_numbers(10, 20, 5))
console.log(checking_numbers(10, 20, 4))
```

>Result:
```javascript
true
true
false
```

**88. Write a JavaScript program to check whether it is possible to replace $ in a given expression x $ y = z with one of the four signs +, -, * or / to obtain a correct expression. For example x = 10, y = 30 and z = 300, we can replace $ with a multiple operator (*) to obtain x * y = z**
- Viết một chương trình JavaScript để kiểm tra xem có thể thay thế $ trong một biểu thức nhất định x $ y = z bằng một trong bốn dấu +, -, * hoặc / để có được một biểu thức chính xác. Ví dụ x = 10, y = 30 và z = 300, chúng ta có thể thay thế $ với một toán tử nhiều (*) để lấy x * y = z

>JavaScript Code:
```javascript
function check_arithmetic_Expression(x, y, z) {
  return x + y == z || x * y == z || x / y == z || x - y == z;
}
console.log(check_arithmetic_Expression(10, 25, 35))
console.log(check_arithmetic_Expression(10, 25, 250))
console.log(check_arithmetic_Expression(30, 25, 5))
console.log(check_arithmetic_Expression(100, 25, 4.0))
console.log(check_arithmetic_Expression(100, 25, 25))
```

>ES6 Version:
```javascript
function check_arithmetic_Expression(x, y, z) {
  return x + y == z || x * y == z || x / y == z || x - y == z;
}
console.log(check_arithmetic_Expression(10, 25, 35))
console.log(check_arithmetic_Expression(10, 25, 250))
console.log(check_arithmetic_Expression(30, 25, 5))
console.log(check_arithmetic_Expression(100, 25, 4.0))
console.log(check_arithmetic_Expression(100, 25, 25))
```

>Result:
```javascript
true
true
true
true
false
```

**89. Write a JavaScript program to find the kth greatest element of a given array of integers.**
- Viết một chương trình JavaScript để tìm ra phần tử lớn thứ k của một mảng số nguyên.

>JavaScript Code:
```javascript
function Kth_greatest_in_array(arr, k) {
  for (var i = 0; i < k; i++) {
    var max_index = i,
        tmp = arr[i];

    for (var j = i + 1; j < arr.length; j++) {
      if (arr[j] > arr[max_index]) {
        max_index = j;
      }
    }

    arr[i] = arr[max_index];
    arr[max_index] = tmp;
  }

  return arr[k - 1];
}

console.log(Kth_greatest_in_array([1, 2, 3, 4, 5], 3))
console.log(Kth_greatest_in_array([-10, -25, -47, -36, 0], 1))
```

>ES6 Version:
```javascript
function Kth_greatest_in_array(arr, k) {

  for (let i = 0; i < k; i++) {
    let max_index = i;
    const tmp = arr[i];

    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] > arr[max_index]) {
        max_index = j;
      }
    }

    arr[i] = arr[max_index];
    arr[max_index] = tmp;
  }

  return arr[k - 1];
}

console.log(Kth_greatest_in_array([1, 2, 3, 4, 5], 3))
console.log(Kth_greatest_in_array([-10, -25, -47, -36, 0], 1))
```

>Result:
```javascript
3
0
```

**90. Write a JavaScript program to find the maximum possible sum of some of its k consecutive numbers (numbers that follow each other in order.) of a given array of positive integers.**
- Viết một chương trình JavaScript để tìm tổng số tối đa có thể của một số số k liên tiếp của nó (số theo thứ tự theo thứ tự.) Của một mảng cho số nguyên dương.

>JavaScript Code:
```javascript
function array_max_consecutive_sum(nums, k) {
  let result = 0;
  let temp_sum = 0;
  for (var i = 0; i < k - 1; i++) {
    temp_sum += nums[i];
  }
  for (var i = k - 1; i < nums.length; i++) {
    temp_sum += nums[i];
    if (temp_sum > result) {
      result = temp_sum;
    }
    temp_sum -= nums[i - k + 1];
  }
  return result;
}

console.log(array_max_consecutive_sum([1, 2, 3, 14, 5], 2))
console.log(array_max_consecutive_sum([2, 3, 5, 1, 6], 3))
console.log(array_max_consecutive_sum([9, 3, 5, 1, 7], 2))
```

>ES6 Version:
```javascript
function array_max_consecutive_sum(nums, k) {
  let result = 0;
  let temp_sum = 0;
  for (var i = 0; i < k - 1; i++) {
    temp_sum += nums[i];
  }
  for (var i = k - 1; i < nums.length; i++) {
    temp_sum += nums[i];
    if (temp_sum > result) {
      result = temp_sum;
    }
    temp_sum -= nums[i - k + 1];
  }
  return result;
}

console.log(array_max_consecutive_sum([1, 2, 3, 14, 5], 2))
console.log(array_max_consecutive_sum([2, 3, 5, 1, 6], 3))
console.log(array_max_consecutive_sum([9, 3, 5, 1, 7], 2))
```

>Result:
```javascript
19
12
12
```

**91. Write a JavaScript program to find the maximal difference between any two adjacent elements of a given array of integers.**
- Viết một chương trình JavaScript để tìm sự khác biệt tối đa giữa hai phần tử liền kề của một mảng các số nguyên.

>JavaScript Code:
```javascript
function max_difference(arr) {
  var max = -1;
  var temp;
  for (var i = 0; i < arr.length - 1; i++) {
    temp = Math.abs(arr[i] - arr[i + 1]);
    max = Math.max(max, temp);
  }
  return max;
}
console.log(max_difference([1, 2, 3, 8, 9]))
console.log(max_difference([1, 2, 3, 18, 9]))
console.log(max_difference([13, 2, 3, 8, 9]))
```

>ES6 Version:
```javascript
function max_difference(arr) {
  let max = -1;
  let temp;
  for (let i = 0; i < arr.length - 1; i++) {
    temp = Math.abs(arr[i] - arr[i + 1]);
    max = Math.max(max, temp);
  }
  return max;
}

console.log(max_difference([1, 2, 3, 8, 9]))
console.log(max_difference([1, 2, 3, 18, 9]))
console.log(max_difference([13, 2, 3, 8, 9]))
```

>Result:
```javascript
5
15
11
```

**92. Write a JavaScript program to find the maximal difference among all possible pairs of a given array of integers.**
- Viết một chương trình JavaScript để tìm sự khác biệt tối đa giữa tất cả các cặp có thể của một mảng số nguyên.

>JavaScript Code:
```javascript
function array_max_diff(arr) {
  var max_result = 0;
  for (var i = 0; i < arr.length; i++) {
    for (var k = 0; k != i && k < arr.length; k++) {
      var diff = Math.abs(arr[i] - arr[k]);
      max_result = Math.max(max_result, diff);
    }
  }
  return max_result;
}
console.log(array_max_diff([1, 2, 3, 8, 9]))
console.log(array_max_diff([1, 2, 3, 18, 9]))
console.log(array_max_diff([13, 2, 3, 8, 9]))
```

>ES6 Version:
```javascript
function array_max_diff(arr) {
  let max_result = 0;
  for (let i = 0; i < arr.length; i++) {
    for (let k = 0; k != i && k < arr.length; k++) {
      const diff = Math.abs(arr[i] - arr[k]);
      max_result = Math.max(max_result, diff);
    }
  }
  return max_result;
}
console.log(array_max_diff([1, 2, 3, 8, 9]))
console.log(array_max_diff([1, 2, 3, 18, 9]))
console.log(array_max_diff([13, 2, 3, 8, 9]))
```

>Result:
```javascript
8
17
11
```

**93. Write a JavaScript program to find the number which appears most in a given array of integers.**
- Viết một chương trình JavaScript để tìm số xuất hiện nhiều nhất trong một mảng số nguyên.

>JavaScript Code:
```javascript
function array_element_mode(arr) {
  var ctr = [],
      ans = 0;
  for (var i = 0; i < 10; i++) {
    ctr.push(0);
  }
  for (var i = 0; i < arr.length; i++) {
    ctr[arr[i] - 1]++;
    if (ctr[arr[i] - 1] > ctr[ans]) {
      ans = arr[i] - 1;
    }
  }
  return ans + 1;
}
console.log(array_element_mode([1, 2, 3, 2, 2, 8, 1, 9]))
```

>ES6 Version:
```javascript
function array_element_mode(arr) {
  const ctr = [];
  let ans = 0;

  for (var i = 0; i < 10; i++) {
    ctr.push(0);
  }
  for (var i = 0; i < arr.length; i++) {
    ctr[arr[i] - 1]++;
    if (ctr[arr[i] - 1] > ctr[ans]) {
      ans = arr[i] - 1;
    }
  }
  return ans + 1;
}
console.log(array_element_mode([1, 2, 3, 2, 2, 8, 1, 9]))
```

>Result:
```javascript
2
```

**94. Write a JavaScript program to replace all the numbers with a specified number of a given array of integers.**
- Viết một chương trình JavaScript để thay thế tất cả các con số với một số lượng quy định của một mảng cho số nguyên.

>JavaScript Code:
```javascript
function array_element_replace(arr, old_value, new_value) {
  for (var i = 0; i < arr.length; i++) {
    if (arr[i] === old_value) {
      arr[i] = new_value;
    }
  }
  return arr;
}
num = [1, 2, 3, 2, 2, 8, 1, 9];
console.log("Original Array: " + num);
console.log(array_element_replace(num, 2, 5));
```

>ES6 Version:
```javascript
function array_element_replace(arr, old_value, new_value) {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === old_value) {
      arr[i] = new_value;
    }
  }
  return arr;
}
num = [1, 2, 3, 2, 2, 8, 1, 9];
console.log(`Original Array: ${num}`);
console.log(array_element_replace(num, 2, 5));
```

>Result:
```javascript
Original Array: 1,2,3,2,2,8,1,9
[1,5,3,5,5,8,1,9]
```

**95. Write a JavaScript program to compute the sum of absolute differences of consecutive numbers of a given array of integers.**
- Viết một chương trình JavaScript để tính tổng của sự khác biệt tuyệt đối của các số liên tiếp của một mảng các số nguyên đã cho.

>JavaScript Code:
```javascript
function sum_adjacent_difference(arr) {
  var result = 0;
  for (var i = 1; i < arr.length; i++) {
    result += Math.abs(arr[i] - arr[i - 1]);
  }
  return result;
}

console.log(sum_adjacent_difference([1, 2, 3, 2, -5]));
```

>ES6 Version:
```javascript
function sum_adjacent_difference(arr) {
  let result = 0;
  for (let i = 1; i < arr.length; i++) {
    result += Math.abs(arr[i] - arr[i - 1]);
  }
  return result;
}

console.log(sum_adjacent_difference([1, 2, 3, 2, -5]));
```

>Result:
```javascript
10
```
