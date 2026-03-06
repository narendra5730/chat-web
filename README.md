import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import { getFirestore } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";
import { getAuth } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js";
import { getStorage } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-storage.js";

const firebaseConfig = {
  apiKey: "AIzaSyB1euofMrg5K70P-9ngtpQbK6y0tq87Hh0",
  authDomain: "chat-web-15.firebaseapp.com",
  projectId: "chat-web-15",
  storageBucket: "chat-web-15.firebasestorage.app",
  messagingSenderId: "587838945922",
  appId: "1:587838945922:web:3b89299b6ef3e1a7ed129b",
  measurementId: "G-N6V1SYRZ7M"
};

const app = initializeApp(firebaseConfig);

const db = getFirestore(app);
const auth = getAuth(app);
const storage = getStorage(app);

export { db, auth, storage };
import { initializeApp } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-app.js";
import { getFirestore } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-firestore.js";
import { getAuth } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js";
import { getStorage } from "https://www.gstatic.com/firebasejs/10.12.0/firebase-storage.js";

const firebaseConfig = {
  apiKey: "AIzaSyB1euofMrg5K70P-9ngtpQbK6y0tq87Hh0",
  authDomain: "chat-web-15.firebaseapp.com",
  projectId: "chat-web-15",
  storageBucket: "chat-web-15.firebasestorage.app",
  messagingSenderId: "587838945922",
  appId: "1:587838945922:web:3b89299b6ef3e1a7ed129b",
  measurementId: "G-N6V1SYRZ7M"
};

const app = initializeApp(firebaseConfig);

const db = getFirestore(app);
const auth = getAuth(app);
const storage = getStorage(app);

export { db, auth, storage };
<!DOCTYPE html>
<html>
<head>
<title>Signup</title>
</head>

<body>

<h2>Create Account</h2>

<input type="email" id="email" placeholder="Email"><br><br>
<input type="password" id="password" placeholder="Password"><br><br>

<button onclick="signup()">Signup</button>

<script type="module">

import { auth } from "./firebase.js";
import { createUserWithEmailAndPassword }
from "https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js";

window.signup = function(){

let email = document.getElementById("email").value;
let password = document.getElementById("password").value;

createUserWithEmailAndPassword(auth,email,password)
.then(()=>{
alert("Account Created");
window.location="login.html";
})
.catch((e)=>{
alert(e.message);
})

}

</script>

</body>
</html>
<!DOCTYPE html>
<html>
<head>
<title>Login</title>
</head>

<body>

<h2>Login</h2>

<input type="email" id="email" placeholder="Email"><br><br>
<input type="password" id="password" placeholder="Password"><br><br>

<button onclick="login()">Login</button>

<script type="module">

import { auth } from "./firebase.js";
import { signInWithEmailAndPassword }
from "https://www.gstatic.com/firebasejs/10.12.0/firebase-auth.js";

window.login = function(){

let email=document.getElementById("email").value;
let password=document.getElementById("password").value;

signInWithEmailAndPassword(auth,email,password)
.then(()=>{
window.location="chat.html";
})
.catch((e)=>{
alert(e.message);
})

}

</script>

</body>
</html>
