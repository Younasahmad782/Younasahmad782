// Your web app's Firebase configuration
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "YOUR_PROJECT_ID.firebaseapp.com",
    projectId: "YOUR_PROJECT_ID",
    storageBucket: "YOUR_PROJECT_ID.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};

// Initialize Firebase
firebase.initializeApp(firebaseConfig);

// Get a reference to the auth service
const auth = firebase.auth();

// Sign-Up
document.getElementById('signup-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const email = document.getElementById('signup-email').value;
    const password = document.getElementById('signup-password').value;
    
    auth.createUserWithEmailAndPassword(email, password)
        .then((userCredential) => {
            // Signed up
            console.log('Sign-Up successful:', userCredential.user);
        })
        .catch((error) => {
            console.error('Error during Sign-Up:', error);
        });
});

// Login
document.getElementById('login-form').addEventListener('submit', (e) => {
    e.preventDefault();
    const email = document.getElementById('login-email').value;
    const password = document.getElementById('login-password').value;
    
    auth.signInWithEmailAndPassword(email, password)
        .then((userCredential) => {
            // Logged in
            console.log('Login successful:', userCredential.user);
        })
        .catch((error) => {
            console.error('Error during Login:', error);
        });
});

// Sample product data
const products = [
    { name: 'Cricket Bat', price: 'PKR 5000' },
    { name: 'Football', price: 'PKR 1500' },
    { name: 'Tennis Racket', price: 'PKR 3000' }
];

// Display products
const productList = document.getElementById('product-list');
products.forEach(product => {
    const productItem = document.createElement('div');
    productItem.innerHTML = `<strong>${product.name}</strong>: ${product.price}`;
    productList.appendChild(productItem);
});
![download (4)](https://github.com/Younasahmad782/Younasahmad782/assets/170994196/161b8720-0255-4d3f-afca-2bdb011f5be2)
