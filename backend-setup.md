---
title: Backend setup
layout: home
nav_order: 1
---

# Backend Setup

This guide will walk you through the process of setting up your Firebase project for use with Chatty Webviews. Our repository makes use of Firebase's Cloud Function, Authentication, Firestore Database, and Storage services to support over-the-air updates.

## Firebase Project Setup

1. **Create a Firebase Account**: If you haven't already, you will need to create a Firebase account. Firebase offers free and paid plans, but for the purposes of setting up Chatty Webviews, the free plan should suffice.

2. **Create a New Project**: Once you have your Firebase account, navigate to the Firebase Console and create a new project. You can name this project whatever you'd like. Make sure that Google Analytics is disabled to streamline the project creation process.

3. **Enable Required Services**: Chatty Webviews requires three Firebase services - Authentication, Firestore Database, and Storage. Each service can be enabled from the Firebase Console.

   - *Authentication*: Navigate to the 'Authentication' tab and click on 'Get Started'. Enable the 'Email/Password' sign-in method.
   - *Firestore Database*: Navigate to the 'Firestore Database' tab and click 'Create database'. Choose 'Start in production mode' and then 'Next'. Select your Cloud Firestore location from the dropdown menu and then 'Enable'.
   - *Storage*: Navigate to the 'Storage' tab and click 'Get started'. Follow the on-screen instructions to set up Cloud Storage.

4. **Clone ChattyWebviews backend repository** - [chatty-webviews-backend](https://github.com/ChattyWebviews/chatty-webviews-backend) .

5. **Deploy Cloud Functions**: Once the required services are enabled, it's time to deploy the Cloud Functions. You can do this by running the following command in your terminal: `firebase deploy --only functions`. This command will deploy all the Firebase functions associated with your project.

Before running the command, ensure you have Firebase CLI installed on your machine. If not, you can install it by running `npm install -g firebase-tools` in your terminal. Also, make sure you are authenticated to Firebase in your CLI. If not, run `firebase login` and follow the prompt.

That's it! Your Firebase backend should now be set up and ready for use with Chatty Webviews CLI. The mobile SDK will call the Cloud Function to check for new application updates and fetch download URLs for new application versions.

Please refer to the [Firebase Documentation](https://firebase.google.com/docs) for further information and troubleshooting. If you encounter issues specific to Chatty Webviews, please create an issue on our GitHub repository.
