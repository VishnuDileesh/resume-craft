<script>
  import { FirebaseApp, User } from "sveltefire";

  import firebase from "firebase/app";
  import "firebase/firestore";
  import "firebase/auth";

  let firebaseConfig = {
    apiKey: "AIzaSyD_pZr2ArWpEZS9HNS3wnN4YQpxyRlWrK4",
    authDomain: "resume-craft.firebaseapp.com",
    databaseURL: "https://resume-craft.firebaseio.com",
    projectId: "resume-craft",
    storageBucket: "resume-craft.appspot.com",
    messagingSenderId: "794936095350",
    appId: "1:794936095350:web:13cee2db43a88e7c51a557",
  };

  firebase.initializeApp(firebaseConfig);

  const auth = firebase.auth();

  const googleProvider = new firebase.auth.GoogleAuthProvider();

  function googleLogin() {
    auth.signInWithPopup(googleProvider);
  }

  // pages

  import Home from "./Home.svelte";
</script>

<style>
  :global(*) {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
    color: #11091a;
  }

  :global(html, body) {
    color: #11091a;
    font-family: "Poppins", sans-serif;
  }

  :global(a) {
    text-decoration: none;
  }

  :global(button) {
    padding: 1em 1.5em;
    border: none;
    background-color: white;
    border-radius: 0.5em;
    cursor: pointer;
  }
</style>

<svelte:head>
  <link
    href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500&display=swap"
    rel="stylesheet" />
</svelte:head>


<Home on:login={googleLogin} />

  <!-- <FirebaseApp {firebase}> -->
    <!-- <User let:user let:auth> -->
      <!-- <h1>Hello User {user.uid}</h1> -->
<!--  -->
      <!-- <button on:click={() => auth.signOut()}>Log out</button> -->
<!--  -->
      <!-- <div slot="signed-out"> -->
        <!-- <h1>Come on, Log in</h1> -->
<!--  -->
        <!-- [> <button on:click={() => auth.signInWithPopup(googleProvider)}>Login with <] -->
        <!-- [> Google</button> <] -->
      <!-- </div> -->
    <!-- </User> -->
  <!-- </FirebaseApp> -->
</main>
