# Entry 3
##### 02/21/2021


## Sources
In this point of time, I am learning my tool, Firebase. I have been using both Repl.it and IDE to help to test out different code. However, I think I will mainly use Repl.it to code. While trying to understand my code, I used <a href = "https://firebase.google.com/docs/web/setup?authuser=0"> the official Firebase guide </a> and Youtube. The official Firebase guide definitely provide a more accurate idea of Firebase however the information is also really dense and therefore it can be hard to understand. Because of this reason I would also use Youtube, which was a big help. There also an official <a href= "https://www.youtube.com/channel/UCP4bf6IHJJQehibu6ai__cg"> Firebase youtube channel </a> and their video,<a href = "https://www.youtube.com/watch?v=O17OWyx08Cg"> Introducing Firebase </a>, really help me grasp a good understanding of what Firebase is and what it does. Videos like <a href = "https://www.youtube.com/watch?v=q5J5ho7YUhA">Firebase - Back to the Basics</a> and <a href = "https://www.youtube.com/watch?v=JrHT1iqSrAQ"> 9.1: What is Firebase? (Database as a Service) - Programming with Text </a> were great assist in helping me understand Firebase.


## Engineering Design Process
I am currently at the late part of stage 4 and early part of stage 5 of the Engineering Design Process: <b>Planning the most promising solution</b> and <b>Creating a prototype</b>. 

In my last blog entry, I indicated that my most promising solution to my problem was making a planner and I also plan what I want my planner to be like. After learning more about my tools, there are still some areas that are uncertain but I had a more precise picture of how I wanted my planner to be like. At the same time, I have recently try to code little pieces of my project and starting to create my first prototype. It is not much. I also had try some code as I went over the Firebase guide. 

I plan to separately code different areas of my project and then gather them together. This way, I can focus more on one aspect of my prototype which can also help me become more skill at using Firebase and coding. 


## Knowledge
The tool I am learning is <i>Firebase</i>. Firebase is a Google application that provide its users with all the tools they need to build, improve and grow their projects/apps. Firebase is a backend as a service (Baas). It is a server that tracks, stores, and save datas for the application. Firebase include Analytics that provides insight on app usage and user engagement, Authentication to know and track the user identity, Realtime Database to store and sync data so that data remains available even when  app goes offline, and secure hosting for their user's application/project.

To get started with Firebase, you need to create a Firebase project to your application before your use any Firebase services. After that you can add your web app to the project and register it. Then you add Firebase SDKs and initialize Firebase to your perferred editor. For me personally I import it from CDN. My core Firebase SDK was ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-app.js"></script>```. This SDK is alway require and must be listed first. To include Firebase service, you need specific SDKs. There are specfic SDKs for specfic Firebase product (i.e if you want to include analytics to your project, you would need to add ```script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-analytics.js"></script>```). Here is a list of specfic Firebase product and their SDKs:<br>
- Analytics: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-analytics.js"></script>```<br>
- Authentication:	```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-auth.js"></script>```<br>
- Cloud Firestore: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-firestore.js"></script>```<br>
- Cloud Functions for Firebase Client SDK: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-functions.js"></script>```<br>
- Cloud Messaging: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-messaging.js"></script>``` <br> For an optimal experience using Cloud Messaging, also add the Firebase SDK for Analytics.<br>
- Cloud Storage: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-storage.js"></script>```<br>
- Performance Monitoring(beta release):	```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-performance.js"></script>```<br>
- Realtime Database: ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-database.js"></script>```<br>
- Remote Config(beta release): ```<script src="https://www.gstatic.com/firebasejs/8.2.8/firebase-remote-config.js"></script>``` <br> For an optimal experience using - Remote Config, also add the Firebase SDK for Analytics.<br>
To initial your Firebase you input your Firebase configuration and then input ```firebase.initializeApp(firebaseConfig);```. The format should look like this:
```
// This is the Firebase configuration
const firebaseConfig = {
  apiKey: "AIzaSyBa_jNZ2OVqeyk46DJoqI4F6YL2ghsh-aA",
  authDomain: "authlogin-d2601.firebaseapp.com",
  projectId: "authlogin-d2601",
  storageBucket: "authlogin-d2601.appspot.com",
  messagingSenderId: "597575677697",
  appId: "1:597575677697:web:9553ec0c76c27e6999cd00"
};
// This Initialize Firebase
firebase.initializeApp(firebaseConfig);
firebase.auth();

// This is the exact code from my recent project
```
In the beginning, I had a confusing time with setting up and importing Firebase SDKs into my application project because I used SDKs from module bundlers which has a completely different code. I also try to set up Firebase CLI reference (this was not what I wanted). I kept using``` npm install -g firebase-tools``` and then trying to logging into Firebase using ``` firebase login```. I was constantly getting errors and it frustrated me so much. Only after a detailed inspection did I realize that I was setting Firebase the wrong way.

Recently I focus on Firebase Authentication and was able to create the <a href = "https://login2.sarahzhang3.repl.co"> login, signup, and log out aspect </a> of my first protoype. Here are some code snippets: 
```
// HTML
<title>Firebase Auth Practice</title>
  <!-- The core Firebase JS SDK is always required and must be listed first -->
<script src="https://www.gstatic.com/firebasejs/8.2.9/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/8.2.9/firebase-auth.js"></script>
	<link href="style.css" rel="stylesheet" type="text/css" />
</head>

<body class="m_div">
	<script src="script.js"></script>

	<h1> Account </h1>
	<div id="accCont" >
    <div id="header"></div>

		<input type = "email" placeholder= "Email" id= "email"/>
    <input type = "password" placeholder= "Password" id= "password"/>

    <button onclick= "signUp()" id = "signUp"> Sign Up </button>
    <button onclick= "signIn()" id = "signIn"> Sign In </button>
    <button onclick="signOut()" id = "signOut"> Sign Out </button>

    </div>
  </body>
 
 // js [the js code are literally all function for the buttons]
 const firebaseConfig = {
  apiKey: "AIzaSyBa_jNZ2OVqeyk46DJoqI4F6YL2ghsh-aA",
  authDomain: "authlogin-d2601.firebaseapp.com",
  projectId: "authlogin-d2601",
  storageBucket: "authlogin-d2601.appspot.com",
  messagingSenderId: "597575677697",
  appId: "1:597575677697:web:9553ec0c76c27e6999cd00"
};

firebase.initializeApp(firebaseConfig);
firebase.auth();

const auth = firebase.auth();


function signUp() {

  var email = document.getElementById("email");
  var password = document.getElementById("password");

  const promise = auth.createUserWithEmailAndPassword(email.value, password.value); // At first I tried to put this on two different code but I kept getting console error
  promise.catch(e => alert(e.message)); // the .catch is something I learn. Basically if there is an error it will alert the user 
  alert("Signed Up");
};
function signIn() {

  var email = document.getElementById("email");
  var password = document.getElementById("password");

  const promise = auth.signInWithEmailAndPassword(email.value, password.value);
  promise.catch(e => alert(e.message));

  alert("You have signed In ");

};

function signOut() {

  auth.signOut();
  alert("Signed Out")
}

auth.onAuthStateChanged(function (user) {

  if (user) {

    var email = user.email;
    alert("Active User " + email);

    //Take user to a different or home page

    //is signed in

  } else {

    alert("No Active User");
    //no user is signed in
  }

});
```
The full version is <a href = "https://repl.it/@SarahZhang3/login2#style.css">here</a>.

## Skills 
The skills I used are <b>having a Growth Mindset</b> and <b>paying Attention to Details</b>.

I use the skill <b>Growth Mindset</b> when I constantly feel tired and frustrated with understanding Firebase. When the application I spend 3 hours working on doesn't work and I can't find the error in my code after checking it for 5 times, I get a headache (literally). The guide had so much information, it was hard to soak everything up. During these moment, I wanted to I question myself and start to worry if I can actually make an application with Firebase. However, in the end I always solve the error and encourage myself that these errors are ways to help me improve my codes in areas that I have diffculties in. I have learn to have a growth mindset by perserving and embracing my failure to improve my coding and worker harder and better. 

I used the skill <b>Attention to Details</b> almost constantly while developing a basic foundation of Firebase. As I mentioned before, Firebase has specific SDKs for specfic Firebase products and there are different codes to initials and set up Firebase. One wrong code can stop your application from using the Firebase product you want. I have to pay attention to which code snippets I need to copy from the guides as the guide product code for all kind of editors. Creating my project, I constantly get syntax errors. I have to constantly recheck my code to figure out these errors and coorect it.

[Previous](entry02.md) | [Next](entry04.md)

[Home](../README.md)
