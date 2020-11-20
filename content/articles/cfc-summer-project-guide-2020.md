---
title: Summer Project 2020 Guide
description: CFC project learnings for 2020
updatedAt: November 18, 2020
img: https://og-social-cards.vercel.app/**.%2Fsummer_project_2020**.png?theme=dark&md=1&fontSize=125px&images=https%3A%2F%2Fcodersforcauses.org%2Flogo%2Fcfc_logo_white_full.svg
alt: CFC Project Learnings
tags:
  - cfc
  - projects
author:
  name: All CFC Committee
  bio: We are the cool kids ;)
  img: /_nuxt/assets/content/committee.png
---

Thank you for choosing to help out in one of our charity projects 💜. We love and appreciate the fact that you have volunteered your time for a great cause.

You have an awesome opportunity to learn truly, what software development is about. How it is applied in the industry and what sort of tools and technologies you will be using. You will be backed by a team of experienced and talented individuals who are working as professional developers. So make sure to ask lots of questions!

Below we will discuss everything to do with Coders for Causes projects...

## Project Structure

### Project Timeline

**21 Dec - Welcome to the summer project**
- Project guide to give you a better idea about the project structure and how the club operate
- Announce member to project mapping
- Release project brief and planned tech stack

**23 Nov → 29 Nov - 1st Training Week**
- Get familiar with basic web language (HTML, CSS, Javascript)

**28 Nov - Project meeting & Meet n' greet**
- Meet the committee members and your project team for the first time
- Modern web development workshop presented by Drew and Frinze(TBC)
- Introduction to Javascript framework

**30 Nov → 4 Dec - 2nd Training Week**
- Continue exploring Javascript framework, if you have done simple app with framework, try to hook it up with free database services

**5 Dec - Project officially start**

### Project Setup

1. Prior to the start of the project our committee will meet with the client and clarify their requirement, we will then create Github issues which represent pieces of work that need to be done (all listed in the project repo). We will also setup the folder structure and place some template code, so you will at least have *something* to start

2. Our committee will confirm your Github account handle and add you as contributor to the project reposotories that you are allocated to. You will also be added to associated project channel in our Discord server

3. You will then download a copy of the code locally to your computer, create a new branch so you don't push unauthorised code to the master branch

4. You will spend some time to make changes and develop stuff. 

In the process of develop code you might want to
- create a check point to save work done so far → `git add` and `git commit`
- put the code you've been adding aside and see what's going on in other branch → `git stash` and `git checkout`
- destroy the code you added and start afresh → VScode extension can easily do that

5. When you finish you will ensure everything has been committed, push the local commits to remote, then you will make a Pull Request through Github which references the Github Issue it completes.

6. The Pull Request (PR) will go through careful review from project manager and/or tech lead. This is to make sure you're following the industry best pratice and the newly added code does not break any existing functionality. You will receive feedback if appropriate.

7. If all is good then it will be merged into the Master branch

8. Done! Thanks for your contribution, celebrate and have a beer 🍺

Don't worry if the above is confusing hopefully it will make sense over time.

## Expectations

You should refer to your team lead about this but in general here is what we expect from you

- Attend all planned meetings and/or weekly review in person or online
- Complete the task that are assigned to you. If you're stuck let people know, ask for help is not a shame
- Consistent work and learn
- Communicate with your group and the project manager
- Be respectful to your team mates and club members, we are all here to learn stuff and have fun
- Finally **your feedback is important to us**, to create the best experience for you and future students. So please call out if you disliked something or if you liked something.

## Meetings & Weekly Reviews

Stand-up meeting is common in tech company and we would like our participants to gain this collaboration experience through our project as well.

Our weekly meeting will occur **every Saturday 3pm-5pm from 5 Dec to 13 Feb** (during the holiday season we will call off some meeting and will put out announcement in Discord)

There are three main goals of weekly reviews.

1. Find out what everyone has done
2. Chance for people to ask questions and discuss solutions to problems
3. Figure out what everyone is doing next

## CFC Web Application Stack

We will use a programming language with libraries and frameworks that other developers have made to make our lives easier. We don't want to have to write code that someone else has already written so that is why we use libraries and frameworks. 

In the following section we will briefly introduce the libraries, frameworks and tools that you will be using. You will get a better idea about what the individual part does and how they combine together to make an awesome web app. Enjoy

### HTML, CSS and Javascript
.
<nuxt-image file="html-css-javascript.png" alt="functionality of html css and javascript in illustration"/>

They are the fundamental building blocks of the internet. Underline **ALL** the modern websites. We don't normally write them explicitly in our source code anymore because it doesn't scale well for large application. Fortunately with help from web framework and some other tool such as bundler, we can easily translate our logic into these languages and voilà! A working website!

**Some important concepts for Javascript are**: asynchronous nature (async/awaits & promises), fetching data from an API, what is Node and how to run Javascript outside the browser

### Typescript

It's essentially Javascript with additional constraints/checking that helps to write safer and cleaner Javascript application. If you're doing Javascript, you're already doing Typescript (Typescript is a superset of Javascript).

### Yarn

Manage external dependencies in your workspace, think of something like pip for Python. You might heard of npm (Node Package Manager) before, Yarn is just an alternative that does the same thing for you.

### React & Vue

Front end framework. It provides pre-determined templates and syntax for developer to organise application logic, contents and assets. They are both Javascript-based.

Depends on the front end framework choice, you might come across these below support framework:

- Next.js - Additional opt in framework **for React**, good for server side rendering and generating static content.
- Nuxt.js - Additional opt in framework **for Vue**, known for making single page application, capable of doing server side render, serverless and static content generating.
- Reactstrap - Components UI library **for React**, adding Bootstrap to your React app to make UI layout easier.
- Vuetify - Components UI library/framework **for Vue**, import wide range of components for front end.

### Express

Back end framework. Standard for Javascript developer to quickly spin up a server.
This is how a backend web server works

1. Receive request from application
2. Talk to database via API (Application Programming Interface)
3. Serve content back to the user

### MongoDB

Document-oriented/NoSQL database.

### Git

Version control command/software. Helps to manage coding collaboration.

**IMPORTANT GIT CONCEPTS**<br />`add`, `commit`, `push`, `pull`, remote vs local, master/main, branching, staging, merging

### Jest, Mocha and Cypress

Testing framework. Jest and Mocha focus more on unit test while Cypress handles the intergration test.

### Other Dev Tools

ESLint - receive alert in code editor when something not quite right

Prettier - automatically format your code while editing, enforce consistent style in group code base

## Tools/Application Check List

- [Discord](http://discord.codersforcauses.org) - For team communication, our committee will add you to project-specific channel, please quickly introduce yourself as a courtesy
- [Github](https://github.com) - Our main coding collaboration platform. You can find project changes, branches, feature status and open issue in here.
- [Git](https://git-scm.com/) - Version control system. Tool to keep track of file changes and allows for a smooth multi-dev experience
<nuxt-image file="git-and-github.png" alt="git and github comparison"/>
- [Node](https://nodejs.org/en/) - Used for building web applications
- [VSCode](https://code.visualstudio.com/) - Or any other preferred code editor. Install extension to improve efficiency and productivity.
- [Yarn](https://yarnpkg.com/) - Package manager for Node application.

Check you installed the tools correctly

```bash
yarn -v
node -v
git --version
```

They should all return something, if not please reach out to our committee member

## Final Remarks

We hope you all have fun doing the project. Software is hard so don't feel bad if things don't make sense even after completing it. It takes years of practice and even then it might not be enough. We will barely glance over everything to do with modern software development so below is a map that details everything. It is an exciting field with a lively community behind it. we encourage you all to continue your journey in software by building more fun apps or joining our committee.

Cheers,<br>
David and all the other CFC committee members ❤︎

<nuxt-image file="roadmap.png" alt="frontend roadmap" />
