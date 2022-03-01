<template>
    <div>
        <Dashboard />
    </div>
</template>

<script>
import Dashboard from './components/Dashboard/Dashboard.vue';
import { initializeApp } from "firebase/app";
import { getAuth, signInWithEmailAndPassword } from "firebase/auth";
//import { getAuth, signInWithRedirect, GoogleAuthProvider } from "firebase/auth";
//const provider = new GoogleAuthProvider();


const firebaseConfig = {
  apiKey: "AIzaSyAOb8xXSzkCvwCmzHXO9aFp0DZqt0n41ZE",
  authDomain: "findingtool-4823f.firebaseapp.com",
  projectId: "findingtool-4823f",
  storageBucket: "findingtool-4823f.appspot.com",
  messagingSenderId: "365964728381",
  appId: "1:365964728381:web:acb7791d775e5634353254"
};

// Initialize Firebase
const app = initializeApp(firebaseConfig);
console.log({app})
//const auth = getAuth();
//console.log({auth: auth.currentUser})
//signInWithRedirect(auth, provider);
const auth = getAuth();
const email = "nraut@deqode.com"
const password = "Niklesh@123"
signInWithEmailAndPassword(auth, email, password)
  .then((userCredential) => {
    // Signed in
    const user = userCredential.user;
    console.log({user})
    // ...
  })
  .catch((error) => {
    const errorCode = error.code;
    const errorMessage = error.message;
    console.log({errorCode})
    console.log({errorMessage})
    // ..
  });
export default {
    name: 'App',
    components: {
        Dashboard,
    },
    mounted(){
      //console.log({app})
    }
};
</script>

<style>
#app {
    font-family: Avenir, Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
    margin-top: 60px;
}
</style>
