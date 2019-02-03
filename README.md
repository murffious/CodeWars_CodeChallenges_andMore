# CodeWars_CodeChallenges_andMore

CodeFights
Grider Class
Bootcamp ones


Feb 2 - 2019
https://www.codewars.com/kata/equal-sides-of-an-array/train/javascript
function findEvenIndex(arr)
{
  // iterator
  let i = 0;
  // track results of sums and comparisons
  let leftSideSum = 0;
  let rightSideSum = 0;
  let tempLeftSideArr = [];
  let tempRightSideArr = [];
  let indexMatches = [];
  let noMatch = false;
  // helper function
  const reducer = (accumulator, currentValue) => accumulator + currentValue;

  // just loop over the given array 
  while(i < arr.length){

  // make a copy of each side of the array with a pivot index 
  tempLeftSideArr  = arr.slice(0, i)
  tempRightSideArr = arr.slice(i+1)
  
  // sum each copy of each side with reduce and if empty array return 0 
  leftSideSum  =  tempLeftSideArr  == 0 ? 0 : tempLeftSideArr.reduce(reducer);
  rightSideSum =  tempRightSideArr == 0 ? 0 : tempRightSideArr.reduce(reducer);
  
  // compare the 2 sums and push index into matches arr if match
  rightSideSum === leftSideSum ? indexMatches.push(i): null;
    
    i++
  }  
    
 if(indexMatches.length < 1){
  // return -1 as directed if there are NO matches in matches arr
   return -1;
 }
   // return the minimum value in the index matches arr
   return Math.min(...indexMatches)
}


5 kyu
384
Replace reg ex test match 
// --- Directions
// Given a string, return the character that is most
// commonly used in the string.
// --- Examples
// maxChar("abcccccccd") === "c"
// maxChar("apple 1231111") === "1"

function maxChar(str) {
  const charMap = {};
  let max = 0;
  let maxChar = '';

  for (let char of str) {
    if (charMap[char]) {
      charMap[char]++;
    } else {
      charMap[char] = 1;
    }
  }

  for (let char in charMap) {
    if (charMap[char] > max) {
      max = charMap[char];
      maxChar = char;
    }
  }

  return maxChar;
}

module.exports = maxChar;



Completed (71)

7 kyu
ES2015: Build an object which can't be modified
JavaScript:

const stone = {
  feature: 'earth',
  style: {
    color: 'black'
  }
  
}


console.log(stone)
// To do so, we use this function.
function deepFreeze(obj) {

  // Retrieve the property names defined on obj
  var propNames = Object.getOwnPropertyNames(obj);

  // Freeze properties before freezing self
  propNames.forEach(function(name) {
    var prop = obj[name];

    // Freeze prop if it is an object
    if (typeof prop == 'object' && prop !== null)
      deepFreeze(prop);
  });

  // Freeze self (no-op if already frozen)
  return Object.freeze(obj);
}

deepFreeze(stone);
3 months agoRefactorDiscuss
8 kyu
Beginner Series #1 School Paperwork
JavaScript:

function paperwork(n, m) {
if (n <= 0) {
return 0
}
else if(m <=0 ) {
  return 0
}
else if (n && m > 0) {
  return n* m 
  }
  
}
3 months agoRefactorDiscuss
8 kyu
Are arrow functions odd?
JavaScript:

function odds(values){
  // arrow it
  return values.filter( value => {
   return value % 2 != 0 
  });
}
3 months agoRefactorDiscuss
7 kyu
Building Strings From a Hash
JavaScript:

function solution(pairs){
    var str = '';
    for (var p in pairs) {
        if (pairs.hasOwnProperty(p)) {
            str += p + ' = ' + pairs[p] + ','
        }
    }
     return str.slice(0, str.length - 1)
  }
3 months agoRefactorDiscuss
8 kyu
Calculate average
JavaScript:

function find_average(array) {
  function getSum(a, b) {
    return (a + b)  ;
}
  var avg = array.reduce(getSum)
  return avg / array.length
}
3 months agoRefactorDiscuss
7 kyu
Reversed Strings
JavaScript:

function solution(str) {
    // Step 1. Use the split() method to return a new array
    var splitString = str.split(""); // var splitString = "hello".split("");
    // ["h", "e", "l", "l", "o"]
 
    // Step 2. Use the reverse() method to reverse the new created array
    var reverseArray = splitString.reverse(); // var reverseArray = ["h", "e", "l", "l", "o"].reverse();
    // ["o", "l", "l", "e", "h"]
 
    // Step 3. Use the join() method to join all elements of the array into a string
    var joinArray = reverseArray.join(""); // var joinArray = ["o", "l", "l", "e", "h"].join("");
    // "olleh"
    
    //Step 4. Return the reversed string
    return joinArray; // "olleh"
}
4 months agoRefactorDiscuss
7 kyu
Find the smallest integer in the array
JavaScript:

class SmallestIntegerFinder {
  findSmallestInt(args) {
    return Math.min(...args)
  }
}
4 months agoRefactorDiscuss
7 kyu
Remove the minimum
JavaScript:

function removeSmallest(numbers) {
 var minn = Math.min(...numbers)
 var imin = numbers.indexOf(minn)
 var minRemoved = []   
   var other = numbers.map((e,i)=>{
      if ( (e == minn && i != imin) || e != minn ) {
         minRemoved.push(e)
      }
    })
     return minRemoved 
}
4 months agoRefactorDiscuss
6 kyu
Your order, please
JavaScript:

function order(words){
  // ...
  var lines = words.split(" ");
  
  var orders = lines.slice()
 
  for (var i = 0; i < lines.length; i++) {
      if (lines[i].includes("1")) {
          orders[0] = lines[i].slice()
      }
      else if (lines[i].includes("2")) {
          orders[1] = lines[i].slice() 
      }
       else if (lines[i].includes("3")) {
          orders[2] = lines[i].slice() 
      }
       else if (lines[i].includes("4")) {
          orders[3] = lines[i].slice() 
      }
       else if (lines[i].includes("5")) {
          orders[4] = lines[i].slice() 
      }
       else if (lines[i].includes("6")) {
          orders[5] = lines[i].slice() 
      }
       else if (lines[i].includes("7")) {
          orders[6] = lines[i].slice() 
      }
       else if (lines[i].includes("8")) {
          orders[7] = lines[i].slice() 
      }
       else if (lines[i].includes("9")) {
          orders[8] = lines[i].slice() 
      }
     
  }
     return orders.join(' ')
  
}
4 months agoRefactorDiscuss
7 kyu
Possiblities Array
JavaScript:

function isAllPossibilities(x){

if ( x.length == 0) {
  return false 
}
else if ( x.length === 1 && x[0] === 0 ) {
         return true
     } 

var count = 0 
var sorted = x.sort(function(a, b){return a-b}) 
   
   if (sorted[0] < 0) {
     return false
   }
   if (sorted[0] != 0) {
      return false
   }
   
for (var i = 0; i< sorted.length - 2;) {
    if ((sorted[i + 1] - sorted[i]) ==1) {
            count+=1 
            i++
         }
    else {
        i++
      }
    }
   
    if (count == sorted.length -2){
     return true
    }
    else {
     return false
    }
}
4 months agoRefactorDiscuss
6 kyu
Is a number prime?
JavaScript:


function isPrime(num) {
  //TODO
  if (num == 0 || num == 1 || num == -1) {
    return false
  }
  else if (num ==2 || num == 3 || num == 5) {
    return true
  }
  else if (num % 2 == 0 || num % 3 == 0 || num % 5 == 0){
   return false
  }
  else if (num % 2 != 0 || num % 3 != 0) {
    return true
  }
  
}
4 months agoRefactorDiscuss
6 kyu
Sort the odd
JavaScript:

function sortArray(array) {
  var arr = [];
  for (var i = 0; i < array.length; i++) {
  if (array[i] == 1 || array[i] % 2 != 0) {
      arr.push(array[i])
  }
  }
  var sorted = arr.sort(function(a, b){return a-b})
  for (var i = 0; i < array.length;) {  
    for(var j = 0; j < sorted.length;){
      if (array[i] == 1 || array[i] % 2 !=0) {
       array[i]   = sorted[j]
       j++
        i++ 
      }
      else if (array[i] % 2 ==0){
          array[i] = array[i]
          i++
      }
    }
    return array
  }
}
4 months agoRefactorDiscuss
6 kyu
If you can read this...
JavaScript:

function to_nato(words) {
	
 var test1 = words.split('')
 console.log(test1)
 var nato = [];
 
 for (var i=0; i < test1.length; i++) {
 
  switch (test1[i].toLowerCase()) {
        case "a": nato.push("Alfa") 
        break;
        case "b": nato.push("Bravo") 
        break;
        case "c": nato.push("Charlie") 
        break;
        case "d": nato.push("Delta") 
        break;
        case "e": nato.push("Echo") 
        break;
        case "f": nato.push("Foxtrot") 
        break;
        case "g": nato.push("Golf") 
        break;
        case "h": nato.push("Hotel") 
        break;
        case "i": nato.push("India") 
        break;
        case "j": nato.push("Juliett") 
        break;
        case "k": nato.push("Kilo") 
        break;
        case "l": nato.push("Lima") 
        break;
        case "m": nato.push("Mike") 
        break;
        case "n": nato.push("November") 
        break;
        case "o": nato.push("Oscar") 
        break;
        case "p": nato.push("Papa") 
        break;
        case "q": nato.push("Quebec") 
        break;
        case "r": nato.push("Romeo") 
        break;
        case "s": nato.push("Sierra") 
        break;
        case "t": nato.push("Tango") 
        break;
        case "u": nato.push("Uniform") 
        break;
        case "v": nato.push("Victor") 
        break;
        case "w": nato.push("Whiskey") 
        break;
        case "x": nato.push("Xray") 
        break;
        case "y": nato.push("Yankee") 
        break;
        case "z": nato.push("Zulu") 
        break;
        case " ": 
        break;
        case ".": nato.push(".") 
        break;
        case "!": nato.push("!")
        break;
        case "?": nato.push("?")
        break;
    }
    
    }
    console.log(nato.join(' '))
    return nato.join(" ")
}
4 months agoRefactorDiscuss
6 kyu
Count the smiley faces!
JavaScript:

//return the total number of smiling faces in the array
function countSmileys(arr) {
var count = 0; 
for (var i = 0; i < arr.length; i++){

switch (arr[i]) {
  case ':)':
  case ':D' : 
  case ';-D': 
  case ':~)':
  case ';~)':
  case ';D':
  case ':-D':
  case ';)':
  case ';~)':
  case ';~D':
  case ';-)':
  case ':~D': 
  case ':-)':
    count++
    break;
    }
    
  }
  return count
}
4 months agoRefactorDiscuss
6 kyu
Delete occurrences of an element if it occurs more than n times
JavaScript:


function deleteNth(arr,x){
  
var obj = { };
var arr1 = [];
for (var i = 0, j = arr.length; i < j; i++) {
   obj[arr[i]] = (obj[arr[i]] || 0) + 1;
    if (obj[arr[i]] <= x) {
      arr1.push(arr[i])
    }
}

    return arr1
}
4 months agoRefactorDiscuss
7 kyu
Powers of 3
JavaScript:

function largestPower(n){
var i = 0;
if (n > 3) {
 while (Math.pow(3, i) < n) {
      i++
    }
  return i-1

 } 
 else if (n ===1){
 return -1 
 }
 else {
 return 0
 }

  
}
4 months agoRefactorDiscuss
8 kyu
Collatz Conjecture (3n+1)
JavaScript:

var hotpo = function(n){
    if(n == 0) return 0; //Optional Handler to n = 0
//     I want to do those operations as long n != 1 

var count = 0;
while (n != 1) {
    if(n % 2 === 0 )  n = n / 2 
    else { n = 3*n + 1 }
    console.log(n, count)
    count++

    }
       
   
    return count



}
4 months agoRefactorDiscuss
7 kyu
Validate credit card expiry date
JavaScript:

function checkExpiryValid (date) {

// Incoming date
var d =  date.replace(/\W/g, '').split('')
 if (d.length != 6) {
 d.splice(2, 0, 2, 0);
 }
 var incYear = d.slice(2).join('')
 var incMonth = d.slice(0, 2).join('')
 
 
//  Current Date 
 var now = new Date ()
var currentYear = now.getFullYear().toString();
 var currentMonth = now.getMonth()
 currentMonth = (currentMonth+1)
 
 console.log(currentYear, currentMonth)
console.log(incYear, incMonth)
console.log(incYear >= currentYear && incMonth >= currentMonth)
// compare both
if (Number(incYear) === Number(currentYear)) {
      if (Number(incMonth) >= Number(currentMonth)) {
         return true
      }
}
 if (Number(incYear) > Number(currentYear)){
return true
}
 else {
   return false
 }
 
}
4 months agoRefactorDiscuss
7 kyu
Product of Array Items
JavaScript:

/**
 * Returns product of all numbers in a numeric array.
 * Returns null if param is null or array is empty.
 * @param {Array} values - The array containing the items.
 */
function product(values) {

if (values === null || values.length === 0) {
  return null
}
else {
function getProduct(total, num) {
    return total * num;
}

 return values.reduce(getProduct)
 }
}
4 months agoRefactorDiscuss
7 kyu
Two Oldest Ages
JavaScript:

// return the two oldest/oldest ages within the array of ages passed in.
function twoOldestAges(ages){
   var nums = ages.sort(function(a, b){return a-b})
   var oldest = [];
       oldest.push(nums[nums.length -2])
       oldest.push(nums[nums.length -1])
   return oldest
}
4 months agoRefactorDiscuss
7 kyu
Find the vowels
JavaScript:

function vowelIndices(word){
  var vowels = /[AEIOUaeiou]/
  var letters = []
   var words = word.split('')
   for (let i = 0; i < words.length; i++) {
       if ((/^[aeiouy]$/i).test(words[i])) {
          letters.push(i + 1)
       }
   }; 
  return letters
}
4 months agoRefactorDiscuss
8 kyu
BASIC: Making Six Toast.
JavaScript:

function sixToast(num) {
 
   
  if (num >= 6) {
    return num -6
  }
  
  else if (num < 6) {
    return 6- num      
  }

}
4 months agoRefactorDiscuss
function sixToast(num) {
   
  if (num >= 6) {
    return num -6
  }
  
  else if (num < 6) {
    return 6- num      
  }
}
4 months agoRefactor
8 kyu
Basic variable assignment
PHP:

$a = "code";
$b = "wa.rs";
$name = $a . $b;
5 months agoRefactorDiscuss
8 kyu
Sum Arrays
JavaScript:

// Sum Numbers
function sum (numbers) {
    "use strict";
    if(numbers.length < 1) {
    return 0
    }
    
    function getSum(total, num) {
    return total + num;
    }

    return numbers.reduce(getSum)
};
5 months agoRefactorDiscuss
7 kyu
Partial Word Searching
JavaScript:

function wordSearch(query, seq){
   let filled = [];
   console.log(seq, query)
  for (let i = 0; i < seq.length; i++) {
     if (seq[i].toLowerCase().includes(query.toLowerCase())) {
           filled.push(seq[i]) 
          }
     
   }
   if (filled[0] == null) {
      filled[0] = "Empty"
      return filled
   } else {
   
   return filled 
}
}
7 months agoRefactorDiscuss
7 kyu
Jaden Casing Strings
JavaScript:

String.prototype.toJadenCase = function () {
   let jaden = this.split(' ')
   
   for (let i = 0; i < jaden.length; i++) {
     jaden[i] = jaden[i].charAt(0).toUpperCase() + jaden[i].substr(1);
   }
   console.log(jaden)
   return jaden.join(" ")
};
7 months agoRefactorDiscuss
7 kyu
Alphabet war
JavaScript:

function alphabetWar(fight){
  var rightSideScore = 0
  var leftSideScore = 0
  var varFight = fight.split('')
  for (var i = 0; i < varFight.length; i++){
    console.log(fight)
    if (varFight[i] === 'w') {
    leftSideScore += 4
  }
  else if (varFight[i] === 'p'){
    leftSideScore += 3
  }
  else if (varFight[i] === 'b'){
    leftSideScore += 2
  }
  else if (varFight[i] === 's'){
    leftSideScore += 1
  }
  else if (varFight[i] === 'm'){
    rightSideScore += 4
  }
  else if (varFight[i] === 'q'){
    rightSideScore += 3
  }
  else if (varFight[i] === 'd'){
    rightSideScore += 2
  }
  else if (varFight[i] === 'z'){
    rightSideScore += 1
  }
  else {
    null
  }
  }
  if (rightSideScore > leftSideScore){
    return "Right side wins!"
  }
  else if (leftSideScore > rightSideScore){
    return "Left side wins!"
  }
  else {
    return "Let's fight again!" 
  }
}
7 months agoRefactorDiscuss
7 kyu
Isograms
JavaScript:

function isIsogram(str){

  // Turn all letters of the string to lower case and split it into an array. 

  var letters = str.toLowerCase().split('');
  var checkLetters = [];
  
  /* Check to see if the letter appears in the checkLetters array.
     If the letter is not already in the array it will push the letter into it. */

  letters.forEach(function(letter) {
    if(checkLetters.indexOf(letter) === -1) {
      checkLetters.push(letter);
    }
  });

  /* Now we have two arrays. If the letters array has non-duplicate letters then 
     it will be the same length as the checkLetters array. If not, the checkLetters array
     will be shorter. */

  /* Return true or false depending on whether the lengths of both arrays are equal */
    
  return letters.length === checkLetters.length ? true : false;

}
7 months agoRefactorDiscuss
7 kyu
Get the Middle Character
JavaScript:

function getMiddle(s)
{
 
 if (s.length % 2 === 0) {
 return s.charAt([((s.length/2) -1)]) + s.charAt([((s.length/2))]) 
 }
 else if(s.length % 2 !== 0) {
   return s.charAt([s.length/2])
 }
}
7 months agoRefactorDiscuss
7 kyu
Vowel Count
JavaScript:

function getCount(str) {
  var vowelsCount = 0;


let vowels = str.match(/[aeiouAEIOU]/g)
console.log(vowels)
if (vowels == null) {
return 0
}
// let arr = str.split('')
 //  for (let i = 0; i < arr.length; i++) {
 //  if (arr[i] === 
 //  }
  
  return vowels.length
}
7 months agoRefactorDiscuss
6 kyu
Multiples of 3 or 5
JavaScript:

function solution(number){
  console.log(number)
  if (number <= 3) {
    return 0
  }
  else {
var arr = []
  for (let count =3 ; count < number; count+=3) {
   arr.push(count)
  }
var newArr = []
for (let count =5 ; count < number; count+=5) {
   newArr.push(count)
  }

function getSum(total, num) {
    return total + num;
}
 var final = newArr.concat(arr).filter(function(elem, i, array) {
        return newArr.concat(arr).indexOf(elem) === i;
})


 return final.reduce(getSum)
}
}
7 months agoRefactorDiscuss
6 kyu
Find the unique number
JavaScript:

function findUniq(arr) {
  
let sorted = arr.sort('')  
  
    if (sorted[0] === sorted[1]) {
      return sorted[sorted.length-1]
    }
    else {
      return sorted[0]
    }
  
}
7 months agoRefactorDiscuss
7 kyu
Find the middle element
JavaScript:

var gimme = function (inputArray) {
  // Implement this function
  for (var i = 0; i < inputArray.length; i++) {
  if (inputArray[i] !== Math.min(...inputArray) && inputArray[i] !== Math.max(...inputArray) )
  {
  return inputArray.indexOf(inputArray[i])
  
  }
 
 }
};
7 months agoRefactorDiscuss
5 kyu
Regex Password Validation
JavaScript:

function validate(password) {
console.log(password)
  return /^(?=.*?[A-Z])(?=.*?[a-z])(?=.*?[0-9])[A-Za-z0-9]{6,}$/.test(password);
  
}
7 months agoRefactorDiscuss
7 kyu
Disemvowel Trolls
JavaScript:

function disemvowel(str) {
var matched = str.match(/[^aeiouAEIOU]/g).join("");
  return matched;
}
7 months agoRefactorDiscuss
5 kyu
Moving Zeros To The End
JavaScript:

var moveZeros = function (arr) {
  for(var i = arr.length - 1; i >= 0; i--) {
    if(arr[i] === 0) {
      arr.splice(i, 1);
      arr.push(0);
    }
  }
  return arr;
}
7 months agoRefactorDiscuss
7 kyu
Generate HTML links
JavaScript:


function generateMenu (menuItems) {
  var outputString = "";
  for (var i = 0; i < menuItems.length; i++){
    var anchorString = "<a href=\"" + menuItems[i].url + "\">" + menuItems[i].text + "</a>";
    console.log(anchorString)
    outputString += anchorString;
  }
  return outputString;
}
7 months agoRefactorDiscuss
7 kyu
Cost of my ride
JavaScript:

function insurance(age, size, numofdays){
 var sum = 0;
  if (age < 25) {
    sum += (10 * numofdays);
  }
  if (numofdays < 0) {
    return 0;
  }
  switch(size) {
  case "economy":
    break;
  case "medium":
    sum += (10 * numofdays);
    break;
  default:
    sum += (15 * numofdays);
  }
  sum += (50 * numofdays);
  return sum;
}
7 months agoRefactorDiscuss
8 kyu
Find the first non-consecutive number
JavaScript:

function firstNonConsecutive (arr) {
 var count = arr[0]
 for (let i = 0; i < arr.length; i++) {
 
 if (arr[i] !== count++) {
  return arr[i]
 }
 
 
 }
return null 
}
7 months agoRefactorDiscuss
5 kyu
Where my anagrams at?
JavaScript:

function anagrams(word, words) {
return words.filter((w) => {
return w.split('').sort().join('') === word.split('').sort().join('')
})

}
7 months agoRefactorDiscuss
6 kyu
Who likes it?
JavaScript:

function likes(names) {
  // TODO
  switch (names.length) {
   case 0 : 
     return "no one likes this";
      break;
   case 1 :
     return names[0] + " likes this";
      break;
  case 2 :
    return names[0] +    " and " + names[1] + " like this";
    break;
  case 3 :
   return names[0] + ", " + names[1] +   " and " + names[2] + " like this";
    break;
  default :
   return names[0] + ", " + names[1] + " and " + (names.length-2) + " others like this";
    break;
  
  }
}
7 months agoRefactorDiscuss
8 kyu
String cleaning
JavaScript:

function stringClean(s){
 newStr = s.replace(/\d*/g, '')
 return newStr
}
7 months agoRefactorDiscuss
8 kyu
Filter out the geese
JavaScript:

function gooseFilter (birds) {
  var geese = ["African", "Roman Tufted", "Toulouse", "Pilgrim", "Steinbacher"];
 return birds.filter(function(e){
  return geese.indexOf(e) <0
})
  // return an array containing all of the strings in the input array except those that match strings in geese
};
7 months agoRefactorDiscuss
6 kyu
Dubstep
JavaScript:

function songDecoder(song){
  // ...split filter join
   // ...split filter join
 var newOne = song.split("WUB").filter(function(e){
   return e !== "";
 })
 return newOne.join(" ")
}
7 months agoRefactorDiscuss
7 kyu
Complementary DNA
JavaScript:

function DNAStrand(dna){
  var newDNA = dna.split('')
  for (var i = 0; i < newDNA.length; i++) {
    if (newDNA[i] === 'A') {
      newDNA.splice(i, 1, 'T')
    }
   else if (newDNA[i] === 'T') {
      newDNA.splice(i, 1, 'A')
    }
    else if (newDNA[i] === 'C') {
      newDNA.splice(i, 1, 'G')
    }
    else if (newDNA[i] === 'G') {
      newDNA.splice(i, 1, 'C')
    }
    
  }
  return newDNA.join('')
}
7 months agoRefactorDiscuss
Loading more items...

© 2018 Codewars
About
API
Blog
Privacy
Terms
Contact
Poweredby_qualified
