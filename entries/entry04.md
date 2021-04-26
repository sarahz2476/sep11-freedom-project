# Entry 4
##### 04/25/2021

## Sources
At this point of time, I am learning my tool, Firebase, and have also started my first prototype. More sepecially I have been focusing on firebase Realtime database. While trying to understand realtime database, I used the the official Firebase guide and Youtube. As stated previously, the infomation on the guide is really dense and therefore I have been using Youtube to help me see the codes in action. The <a href = https://www.youtube.com/c/TheCodingTrain/featured> The Coding Train </a> channel's firebase videos have really helped me get a good grasp of firebase in general and saving data to realtime database. I have also started to make my first prototype and the dom lessons were a really big help. 

## Engineering Design Process
I am currently at the late part of stage 4 and in the middle of stage 5 of the Engineering Design Process: <b>Planning the most promising solution</b> and <b>Creating a prototype</b>. 

In my last blog entry, I stated that I focus on Firebase Authentication and was able to create a small <a href = "https://login2.sarahzhang3.repl.co"> login, signup, and log out </a> function. I have added firebase database to it. At the same time, I have recently coded my first prototype but it does not have any firebase functions yet. I am experimenting on firebase separately. 

I am planning to continued with learning more about Firebase and planning to incorporate some into my prototype. This way I can minimize errors which helps organize my codes better.
 
## Knowledge
The tool I am learning is <i>Firebase</i>. I have been working on Firebase Realtime Database. The Firebase Realtime Database is a cloud-hosted database. Data is stored as JSON and synchronized in realtime to every person who is connected. All those who share one Realtime Database instance will automatically receive updates with the newest data. Realtime Database  store and sync data so that data remains available even when app goes offline, and secure hosting for their user's application/project. To connect to realtime database, add ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-database.js"></script>``` and to Initialize Firebase realtime database,  add ```firebase.database();``` - this must be added. When I was doing it in the beginning with just ```const database = firebase.database();```, I keep getting a error message saying "database is not a function" and only after adding that to my code, did it solve the problem. I used my code from the login, signup, and log out and added:
```
var data = {
    email: email.value,
    password: password.value
}
 console.log(data);
  var ref = database.ref("accounts");
  ref.push(data);
```
In the code above, I want to save data of the email and password. Therefore in the data varaible I store in the email and password input value as data. After, I used 'ref' to create a "account" reference in my database. I then push that data into it. It is not much but it helped me understand more about Realtime database. 

I have created a MVP to help me manage this freedom project. In the MVP, I planned what my core function of my freedom project is and then I created a timeline to plan the weeks following up to June 1.

Here is the javascript code for my <a href = https://ide-6bbb60f064c04a0292e9d817cdb2daf9-8081.cs50.ws/index.html> prototype 1</a>:
```
var addtask = document.getElementById("add");
var taskContainer = document.getElementById("taskContainer");
var taskField = document.getElementById("taskField");

addtask.addEventListener('click', function(){
    var para = document.createElement('p');
    para.innerText = taskField.value;
    taskContainer.appendChild(para);
    taskField.value = "";
    para.addEventListener('click',function(){
        para.style.textDecoration = "line-through";
    })
    para.addEventListener('dblclick',function(){
        taskContainer.removeChild(para);
    })
})
```

## Skills 
The skills I used are <b>How to Learn</b> and <b>How to Google</b>.

I use the skill <b>How to Learn</b> when I am trying to understand Firebase realtime database. The whole process of learning firebase and incorporating it into my project is basically a LOYO (Learn On Your Own) process. I have to find videos up and google some codes that I really did not understand. I even google up some syntax error because I have no idea what I was doing wrong. It was hard to understand the guide because it had many technical terms. But I got better with the terms by searching it up.

I used the skill <b>How to Google</b>. As I mention, throughout the entire process, I had to search things up a lot. That includes terms, syntax error, and sometimes even code. I learn to use ⌘+F to find infomations I need with one key word or phrases. This helped me shorten my time spending on reading infomations that are irrelevant. 

[Previous](entry03.md) | [Next](entry05.md)

[Home](../README.md)
