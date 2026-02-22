
## Answers to Questions

### 1. What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll?

### 2. How do you create and insert a new element into the DOM?

### 3. What is Event Bubbling? And how does it work?

### 4. What is Event Delegation in JavaScript? Why is it useful?

### 5. What is the difference between preventDefault() and stopPropagation() methods?



1. What is the difference between getElementById, getElementsByClassName, and querySelector / querySelectorAll?

getElementById('id')  একটাই element return করে, id দিয়ে খোঁজে
getElementsByClassName('class')  ওই class এর সব element return করে (HTMLCollection)
querySelector('.class / #id')  প্রথম matching element return করে, CSS selector use করে
querySelectorAll('.class')  সব matching element return করে (NodeList)

2. How do you create and insert a new element into the DOM?

const div = document.createElement('div');
div.textContent = 'Hello';
 Insert
document.body.appendChild(div);
document.getElementById('container').appendChild(div);

3. What is Event Bubbling? And how does it work?

Event Bubbling মানে হলো  কোনো child element এ event fire হলে সেটা parent  grandparent  এভাবে উপরে উঠতে থাকে।
 বন্ধ করতে চাইলে
event.stopPropagation();
4. What is Event Delegation in JavaScript? Why is it useful?

Child এ আলাদা আলাদা event listener না দিয়ে parent এ একটা listener দেওয়াকে Event Delegation বলে।
document.getElementById('list').addEventListener('click', function(e) ){
  if (e.target.tagName === 'LI') {
    console.log(e.target.textContent);
  }
}
5. What is the difference between preventDefault() and stopPropagation() methods?

preventDefault() browser এর default behavior বন্ধ করে 
stopPropagation()  event কে parent এ bubble হতে বন্ধ করে
