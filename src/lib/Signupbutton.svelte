<script>
  import firebase from "firebase/app";
  import "firebase/auth";

  export const firebaseConfig = {
    apiKey: "AIzaSyB--fOUZOfaiiHVRQ5mgzjdC0jiGe669lI",
    authDomain: "final-mobile-apps-59a14.firebaseapp.com",
    projectId: "final-mobile-apps-59a14",
    storageBucket: "final-mobile-apps-59a14.appspot.com",
    messagingSenderId: "592657491455",
    appId: "1:592657491455:web:03d27a57ab0d3bd25333ca",
    measurementId: "G-C3HFEPBMTP",
  };

  firebase.initializeApp(firebaseConfig);

  const signUp = async () => {
    const email = "example@example.com";
    const password = "password123";

    try {
      //await firebase.auth().createUserWithEmailAndPassword(email, password);
      // User signed up successfully
    } catch (error) {
      // Handle sign-up error
      console.log(error.message);
    }
  };
</script>

<main>
  <button on:click={signUp}> Submit </button>
</main>

<style>
  button {
    width: 320px;
    height: 35px;
    margin-top: 20px;
    border: none;
    background-color: #49c1a2;
    color: white;
    font-size: 18px;
  }
</style>
