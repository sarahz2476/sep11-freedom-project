# Entry 2
##### 12/01/2020

Today, I tinkered with my tools to permanently determine which tools I will use for my freedom project. In the end I chose to use [Firebase](https://console.firebase.google.com/u/1/). 

I was quite determine in using Firebase and so I did a lot of research on it. I used youtube videos - "[Creating a website in HTML/JS that stores data in Firebase](https://www.youtube.com/watch?v=-UOkri_WNWQ&t=315s)" and "[Creating a Firebase Project](https://www.youtube.com/watch?v=6juww5Lmvgo)" - to help:

1) undertsand this tool better

2) setting up this tool 

3) tinkering and using this tool for an demo

In the beginning, I was still really confused with what Firebase is and what it does. Only after watching a [youtube video about it](https://www.youtube.com/watch?v=O17OWyx08Cg), was I able to understand that Firebase is a like server for an application. It literally tracks, stores, and save datas for the application. At first I thought that the tools we had to use were all new coding languages. Anyways, after spending 4 hours on tinkering Firebase, I grasped some ideas about it.

I was already determined to choose Firebase before I even started to tinker with Firebase. I believr that if I wanted to do a planner, Firebase is a must. Throughout the Engineering Design Process, I have been planning the most promising solution. I have already brainstormed solutions to my problem and right now I chose to use Firebase as a tool to help with create a organized planner. My Freedom project will be on making a planner. My planner will be unique because I will create a month, week, day sections. And in each section, the user can view what they need to do, need to go, etc. The month view, will include a calender that will show events, appointments, etc. The week section includes events on that week and the events will be color coded. The day section will show a todo list and any appointments/events that the user will have on that day. But my first priority is to make the day section before jumping into the other two sections. 

So today I actually made 5 demos and only the [5th demo](https://demo5.sarahzhang3.repl.co) worked. Basically, in my demo I wanted to set up my Firebase tool onto my repl.it. So I had to go to [Firebase Console](https://console.firebase.google.com/u/1/), created a new project and add Firebase JS SDKs and scripts to my code which connects my demo to Firebase. I then created codes so that user can input their name and age on my repl.it and the information will transfer from my demo to the Firebase realtime database, which needs Firebase JS SDKs and needs to be enable. My codes includes:

*The look of the project*
``` 
  <body>
    <h1>Demo User Database</h1>
    <input type= "text" placeholder="Name" id ="namefield"><br>
    <input type= "text" placeholder="Age" id ="agefield"><br>
    <button onclick = "writeData()">Submit</button>
    <p id= "data"></p>
 ```
*Some Firebase JS SDKs and scripts I had to include to make it work*
```
    <script src="script.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.1.1/firebase-app.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.1.1/firebase-auth.js"></script>
    <script src="https://www.gstatic.com/firebasejs/8.1.1/firebase-database.js"></script>
  <script>
  // Your web app's Firebase configuration
  var firebaseConfig = {
    apiKey: "AIzaSyDOF7M3zILcxPpP0iFCis1MXoepaUseXZA",
    authDomain: "demo5-ea2bf.firebaseapp.com",
    databaseURL: "https://demo5-ea2bf.firebaseio.com/",
    projectId: "demo5-ea2bf",
    storageBucket: "demo5-ea2bf.appspot.com",
    messagingSenderId: "810087239268",
    appId: "1:810087239268:web:e7f38ae72d9fe47530d971"
  };
  // Initialize Firebase
  firebase.initializeApp(firebaseConfig);
 ```
*The function that saves and transfer user's data to the Realtime database*
```
  function writeData(){
    firebase.database().ref("User").set ({
      name:document.getElementById("namefield").value,
      age:document.getElementById("agefield").value
      });
      getData();
  }
 ```
*The function that displays the data so the user can see*
```
  function getData(){
   firebase.database().ref("/").once('value', function(snapshot) {
     snapshot.forEach(function(usersnapshot)
     {
       var userKey = usersnapshot.key;
       var userData = usersnapshot.val();
       document.getElementById("data").innerHTML = userData['name'] + ", " + userData['age'];
     })
   })
 }
 getData()
</script>
```

Skills I learn from this experience was debugging and embracing my failures. I had a lot of problem in tinkering the tool, as you can see since I made 5 demos. Many time, it was because of syntax errors. I had to look through the long codes and find out which error I had to change. Thank god, the console tells us about the error. It get more frustrating each time I fail, however, I was able to grasp more knowledge about the tool because the more mistakes and failures I made, the more I search up and took advantage of guides that I found and was provided. In the end, I succeeded with tinkering my tools and gain knowledge about Firebase. 
  

[Previous](entry01.md) | [Next](entry03.md)

[Home](../README.md)
