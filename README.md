# Sparks Portfolio Project

## 📋 Table of Contents

1. [Overview](#overview) 🌐
2. [Technologies Used](#technologies) ⚙️
3. [Features](#features) 🚀
4. [Live Site](#live) 📦
5. [Contact](#contact) 📫
6. [Database Schema](#database-schema) 📊
7. [Screenshots](#screenshots) 📸
8. [Sparks - AI Post Examples](#ai-post-examples) 🤖
9. [Acknowledgments](#acknowledgments) 🙌
10. [Setup](#setup) ⚙️

## <a name="overview">🌐 Overview </a>

Sparks is a full stack social media web app that is designed to help users discover as well as create new ideas for all things creative with the help of AI. 

## <a name="features">🚀 Features</a>

- Fully CRUD , creates, reads, updates, deletes all types of posts such as regular ones, comments and even AI generated ones.
- AI-powered post generation with various categories and the ability to edit/delete if you are the author, AI image generation also included. 
  - Categories:
    - Movies and Novels (includes AI generated images if the User desires, optional)
    - Artworks, Fashion , Photography , (These are all AI generated images)
    - Haikus , Quote, Joke , Aphorism
  prompts used are saved and can be viewed when the sparks logo of the post is clicked!
- User-to-user Messaging system: powered by Pusher(Web Sockets) for realtime updates, ability to leave messages on read, ability to see when a user is online in chat. 
- Image Storage System: Cloud image storage powered by the cloud , allows all profile images, as well as profile posts and even AI generated images to be saved for future usage in a secure S3 bucket privately where only the developer can access them. Cache system included with local storage so images do not have to be fetched every single time.
- User profile management: Onboarding, Profile Edit 
- Activity feed - showing recent activity from other users to keep you engaged! Comes with pagination
- Infinite Scroll: incorporates an infinite scroll feature, providing users with a seamless browsing experience. With infinite scroll, users can effortlessly explore a continuous feed of content without the hassle of traditional pagination. 
- Home Page Feed Filtering - Allow users to filter out the type of posts they would like to see. 
- Like comment and share functionality: Allows the liking of posts, no user can like a post more than once, users can unlike posts as well, everything is reflected in database, posts can have children posts (comments, which can be liked as well, authors can delete their comments as well) and they are all recursively structured where every comment has a parent ID, therefore comments can have comments of their own, providing a twitter-like comment structure, all powered by a SQL dynamic structure, users can share posts directly to other users in their inboxes by clicking the share button which will send a message with the posts' link. When a parent post is deleted all children post is recursively deleted as well!
- Search functionality, search for user profiles as well as posts by keywords
- Notification System: updates when user recieves new message or activity
- Profile Page: Profile page for users with posts they have made, comments they have made and posts they have liked, as well as the ability to message users from there or even edit your bio, and image if it is your profile. 
- Database System: all changes are saved within the database so you can pick back up where you left off. 
- Fully Responsive for all screens, phones, tablets and desktops. 
- Global State System: using app context the app has a global state which helps with real-time functionalities for layout components. 
- Form Validation: Uses Zod Forms to put into place form validations where as users can only submit certain inputs depending on what is allowed.
- Liverages the latest of Next.js by using server actions and API routes, API routes include, openAIChat, openAIImage, and S3

## <a name="live"> 📦 Live Deployment </a>
The webapp is live and hosted by vercel https://sparkify.vercel.app


## <a name="database-schema"> 📊 Data Base Schema </a>
<img src="public/assets/DataBaseSchema.png" alt="Screenshot of SqlSchema" >

###  📊 Database Relationships
- User and Post Relationship:
One-to-Many relationship: A user can create multiple posts, but each post is associated with one user.

- Post and User (author) Relationship:
Many-to-One relationship: Many posts can be associated with one user (the author).

- Post and Post (parent-child) Relationship:
Recursive relationship: A post can have multiple child posts, creating a hierarchical structure.

- Chat and User (sender and receiver) Relationship:
Many-to-Many relationship: A user can be both the sender and receiver in multiple chats.

## <a name="screenshots"> 📸 Screenshots </a>

User interface and different functionalities of Sparks.


# <a name="ai-post-examples">🤖 Sparks Examples [AI Posts] </a>
Below are some examples of generated Sparks



## 🚀 Future Improvements
### Performance Optimization

- Optimizing performance is my top priority. I aim to minimize unnecessary re-renders on the client and reduce function executions, both on the server and client sides. Contributions in this area will greatly enhance the overall user experience.

- Currently, large API requests to OpenAI, such as those for movies and novels, may lead to server function timeouts. This limitation is due to Vercel's free-tier hosting plan, which imposes a 10-second limit on server functions. Collaborative efforts to address this issue are essential for ensuring smooth interactions with external APIs.

## Project Status

All features should be fully funtional, please if you have any concerns or encounter any bugs, feel free to raise an issue or contact me.

### Future Feature Idea for Contributions

This project is open source and contributors are welcomed
Future updates may be focused on these new features that I have in mind:

### 1. Followers List and Feed

Introduce a followers list and feed, providing users with a personalized stream of content from accounts they follow.

### 2. Group Chats

Explore the implementation of group chats, fostering community interactions and group discussions.

### 3. Switch from Clerk to Next auth

Switch to a more independent form of auth, build from the ground up and allow vistors to browse posts even when not logged in

## <a name="acknowledgments">  🙌 Acknowledgments</a>
Shout out to https://loading.io/ for all the icons provided
Shout out to https://unsplash.com/ for all the pictures that were not AI generated or user submitted
Shout out to adrianhajdin on Github for tutorials on Next.js






