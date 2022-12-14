# Tadashi

![Tadashi](/client/public/images/open-graph.jpg)

## Table of contents

1. [Introduction](#introduction)
2. [Live Website](#LiveWebsite)
3. [How to setup?](#setup)

   1. [Clone the repo to your system.](#step1)
   2. [Install all the packages on client and server folder.](#step2)
   3. [Create environment variables on both folders according to .env.example files.](#step3)
   4. [Start the servers.](#step4)

4. [Screenshots](#Screenshots)
   1. [Home](#Home)
   2. [Tools](#Tools)
   3. [Post Downloader](#Post-Downloader)
   4. [Reels Downloader](#Reels-Downloader)
   5. [Profile](#Profile)
   6. [User Profile](#User-Profile)
   7. [Faqs](#Faqs)
   8. [Contact](#Contact)
5. [Tech Stack](#tech-stack)
6. [Feedback](#feedback)

## Introduction

Tadashi is an online web-app that allows you to download Instagram photos and videos.

## Live Website<a id="LiveWebsite"></a>

https://tadashi.vercel.app/

## How to setup?<a id="setup"></a>

### Clone the repo to your system.<a id="step1"></a>

```bash

git clone https://github.com/theviralboy/tadashi
```

### Install all the packages on client and server folders.<a id="step2"></a>

for client folder

```bash

cd client
npm i # or yarn install
```

for server folder

```bash

cd server
npm i # or yarn install
```

### Create environment variables on both folders according to .env.example.<a id="step3"></a>

1. Create **.env.local** file for client and **.env** for server according to **.env.example**.
2. Go to Instagram.com.
3. Open Developer Tools by pressing **Ctrl + Shift + I** or **F11** key.
4. Follow these steps for get your Instagram cookies.
   ![Steps for get your Instagram cookies](/screenshots/setup/get-cookie.png)
5. Paste the cookie inside **.env** file in **server** folder.

### Start the servers.<a id="step4"></a>

for client folder

```bash
cd client
npm start # or yarn start
```

for server folder

```bash
cd server
npm run dev # or yarn run dev
```

## API Reference

**http://localhost:5000/** is the base for the API for example.

#### Get instagram post

```http
  http://localhost:5000/p/${postId}
```

| Parameter | Type     | Description                        |
| :-------- | :------- | :--------------------------------- |
| `postId`  | `string` | Instagram post id eg:`CYa0_SRtUrf` |

#### Preview

```javascript
{
        id: 8798701427, //post id
        caption: "", // post caption
        shortcode: "", //post shortcode
        likes: 4, // likes number
        comments: 9, // comments number
        isVideo: false, //is video or not
        timestamp: 160987896, // timestamp of post
        duration: null, // duration of video only appears on video post
        hasAudio: null, // does video have audio only appears on video post
        views: null, // number of views on video only appears on video post
        plays: null, // number of plays on video only appears on video post
        thumbnail: "", // base64 of thumbnail image
        isCarousel: false, // is carousel post or not
        carouselCount: 0, // number of carousel media only appears on carousel post
        singleMedia: {
          thumbnail: "", // base64 of thumbnail image,
          isVideo: false, // is video or not
          duration: null, // duration of video
          hasAudio: null, // has audio or not
          resources: [
            // array or posts in different resolution
            {
              src: "", // cdn link of post
              width: "", // width in px
              height: "", // height in px
            },
          ],
          videoResources: [
            {
              src: "", // cdn link of post
              width: "", // width in px
              height: "", // height in px
            },
          ],
        },
        carouselMedia: [
          {
            id: 276376524, // post id
            thumbnail: "", // base64 of thumbnail image
            isVideo: false, // is video of not
            duration: null, // duration of video only appears on video post
            resources: [
              // array or posts in different resolution
              {
                src: "", // cdn link of post
                width: "", // width in px
                height: "", // height in px
              },
            ],
            videoResources: [
              {
                src: "", // cdn link of post
                width: "", // width in px
                height: "", // height in px
              },
            ],
          },
        ],
        user: {
          id: 1697987987, // user id
          username: "", // username of user
          fullName: "", // full name of user
          isVerified: "", // is user verified or not
          isPrivate: false, // is user profile private or not
          profilePic: "", // base64 code of user profile
        },
      }
```

#### Get instagram user data

```http
  http://localhost:5000/user/${username}
```

| Parameter  | Type     | Description                                    |
| :--------- | :------- | :--------------------------------------------- |
| `username` | `string` | Instagram profile username eg:`sahilverma.dev` |

#### Preview

```javascript
{
    id: 40825814016,
    bio: "Freelance Front End Developer.\nDM or mail me for freelance projects.\nEmail: sahil.verma.webdev@gmail.com",
    username: "sahilverma.dev",
    profilePic: {
      thumbnail: "", // gives base64 code of user profile image
      link: "", // gives cdn url of user profile image
    },
    category: "Web Developer", // category of user
    fullName: "Sahil Verma", // full name of user
    isPrivate: false, // is user profile private or not?
    isVerified: false, // is user profile verified or not?
    followers: 104, // followers of profile
    following: 27, // following of following users
    posts: {
      total: 27, // total number of posts
      data: [  // array of maximum 12 posts of profile
        {
          id: 2914183618471276612, // post id
          shortcode: "ChxQo-dPjBE", // post shortcode
          thumbnail: "", // base64 code of post image
          location: null, // geo location of post
          caption: {
            main: "", // caption of post
            accessible: null, // accessible caption of post
          },
          comments: 2, // number of comments
          isVideo: false, // is post video or not
          likes: 6, // number of likes
          isCollection: true, // is collection post or not
          resolution: [ // array of resolutions of post
            {
              src: "", //cdn image url
              config_width: "", // image width in px
              config_height: "", // image height in px
            },
          ],
        },
      ],
    },
  }
```

## Screenshots<a id="Screenshots"></a>

### Home<a id="Home"></a>

![Home](/screenshots/home.png)

### Tools<a id="Tools"></a>

![Tools ](/screenshots/tools.png)

### Post Downloader<a id="Post-Downloader"></a>

![Post Downloader ](/screenshots/post-download.png)

### Reel Downloader<a id="Reels-Downloader"></a>

![Reel Downloader](/screenshots/reel-download.png)

### Profile<a id="Profile"></a>

![Profile](/screenshots/profile.png)

### User Profile<a id="User-Profile"></a>

![User Profile](/screenshots/user-profile.png)

### FAQ<a id="Faqs"></a>

![FAQ ](/screenshots/faq.png)

### Contact<a id="Contact"></a>

![Contact ](/screenshots/contact.png)

## Tech Stack<a id="tech-stack"></a>

React JS, Next JS, TailwindCSS, Firebase 9, Node JS, Express,

## Feedback<a id="feedback"></a>

If you have any feedback, please reach out to us at sahilverma.webdev@gmail.com
