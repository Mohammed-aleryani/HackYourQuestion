![Hack Your Questions](https://i.imgur.com/3P3IXIp.jpg "Hack Your Questions")
# Class 42 - Team A final project

# Hack Your Questions (HYQ): A Collaborative Learning Blog

Welcome to Hack Your Questions (HYQ), a dynamic blog built by a group of four talented students and three dedicated mentors as Product Owner, Tech Lead, and Dev Ops. Leveraging the power of the MERN stack and adhering to agile methodologies, HYQ offers a unique platform for the Hack Your Future community to engage in collaborative learning, share knowledge, and seek answers to their burning questions.

## Key Features

1. **Seamless User Experience:** HYQ boasts a user-friendly interface, ensuring smooth navigation for all users, whether they are posting questions, providing answers, or reporting inappropriate content.

2. **Secure User Authentication:** With robust user authentication mechanisms, users can create accounts, log in securely, and enjoy personalized interactions on the platform.

3. **Ask & Answer Questions:** Users can freely post questions related to the Hack Your Future curriculum or programming in general. Likewise, they can actively contribute by providing answers to queries posed by their peers.

4. **Edit & Delete Control:** Empowering users with complete ownership, HYQ allows them to edit or delete their own questions and answers, maintaining the integrity of their contributions.

5. **Maintaining a Positive Environment:** Through a powerful reporting functionality, the community can collaboratively police inappropriate or offensive content. Reported questions and answers are conveniently aggregated in the admin panel.

6. **Efficient Admin Panel:** The admin panel streamlines moderation tasks, providing administrators with a clear overview of reported posts, along with the owner's email and the number of times a post has been reported.

7. **Transparent Communication:** Admins can effortlessly connect with post owners via email to address concerns or provide guidance, nurturing a supportive community atmosphere.

8. **Responsible Post Management:** Admins have the discretion to delete reported questions and answers if they violate community guidelines, promoting a healthy and respectful online environment.

9. **Resilient Data Handling:** Even if a user decides to delete their account, their questions and answers remain in the database under a "deleted user" identifier, ensuring data continuity while respecting user preferences.

10. **Cascading Deletion:** When a question is removed, all associated answers are automatically deleted, keeping the platform tidy and organized.

## The Path Ahead

As the team behind HYQ, we take immense pride in presenting a secure, collaborative, and educational blog platform. Our next steps involve deploying the application to a reliable server, enabling wider accessibility for the Hack Your Future community. Additionally, we will conduct thorough security testing to safeguard user data and ensure a seamless user experience.

In conclusion, Hack Your Questions (HYQ) stands as a testament to the power of teamwork, agile development, and the MERN stack. We extend our heartfelt gratitude to HackYourFuture for providing the platform to nurture our skills and collaborate on this exceptional project.

Thank you for joining us on this journey of collaborative learning and problem-solving. Together, we can empower individuals to grow and succeed in the world of programming and beyond. Happy hacking!


[Click here for the Demo version](https://c42-team-a.herokuapp.com/)

## 1. Setup

First, to setup all the directories run the following in the main directory:

`npm install`

`npm run setup`

The first command will install `cypress` and some small libraries needed for running the rest of the commands. The second will go into the `client` and `server` directories and set those up to be ran.

In the `client` and `server` directory there are two `.env.example` files. Create a copy and rename that to `.env`. Then follow the instructions in those files to fill in the right values.

To run the app in dev mode you can run the following command in the main directory:

`npm run dev`

## 2. Code structure

```
client
├── public
└── src
|   └── __tests__
|   └── __testUtils__
|   └── components
|   └── hooks
|   └── pages
|       └── __tests__
|       └── components
|   └── util
|   index.jsx
cypress
|   └── fixtures
|   └── integration
|   └── plugins
|   └── support
server
└── src
    └── __tests__
    └── __testUtils__
    └── controllers
    └── db
    └── models
    └── routes
    └── util
    index.js
```

### 2.1 Client structure

- `public` || public facing client code
- `__tests__` || any `jest` tests for specific components will be in a `__tests__` folder on the same level
- `__testUtils__` || any code that is only being used in the tests is put in the `__testUtils__` folder to separate that away from the rest of the code
- `components` || all of our shared components that are used over multiple pages
- `hooks` || all of our custom hooks
- `pages` || the page components of our app, any routing will go between these components
- `pages/components` || components used specifically on those pages
- `util` || any utility functions that can be used anywhere on the client side
- `index.jsx` || the start point of the client

### 2.2 Cypress structure

- `fixtures` || any data/files that `cypress` needs can be placed here
- `integration` || all of our tests are in here, separated in folders based on the pages in our app
- `plugins` || any plugins for our `cypress` configuration can be placed here
- `support` || custom commands and other support files for `cypress` can be placed here

### 2.3 Server structure

- `__tests__` || any `jest` tests for the api endpoints as that is our testing strategy for the backend
- `__testUtils__` || any code that is only being used in the tests is put in the `__testUtils__` folder to separate that away from the rest of the code
- `controllers` || all of our controller functions that interact with the database
- `db` || all of our configuration for the database
- `models` || all of our `mongoose` models will be placed here
- `routes` || code to match up the API with our controllers
- `util` || any utility functions that can be used anywhere on the server side
- `index.js` || the start point of the server

## 3. Stack / external libraries

The base stack of the app is a MERN stack (Mongoose, Express, React, Node). Next to that we make use of the following extras:

### 3.1 Configuration libraries

- `dotenv` || To load the .env variables into the process environment. See [docs](https://www.npmjs.com/package/dotenv)
- `webpack` / `html-webpack-plugin` || To bundle our React app and create a static app to host. See [docs](https://webpack.js.org/)
- `husky` || To run our tests and linter before committing. See [docs](https://typicode.github.io/husky/#/)
- `eslint` || To check our code. We have different configurations for frontend and backend. You can check out the configuration in the `.eslintrc.(c)js` files in the respective `client` and `server` folders. See [docs](https://eslint.org/)
- `prettier` || To automatically format our code. See [docs](https://prettier.io/)
- `concurrently` || To run commands in parallel. See [docs](https://github.com/open-cli-tools/concurrently#readme)

For more information on how these work together including the automatic deployment to heroku, have a look at our detailed [DEV](./DEV.md) file.

### 3.2 Client-side libraries

- `@testing-library/*` || We use React Testing Library to write all of our tests. See [docs](https://testing-library.com/docs/react-testing-library/intro/)
- `jest` || To run our tests and coverage. See [docs](https://jestjs.io/)
- `jest-fetch-mock` || To mock out the backend for our testing purposes. See [docs](https://github.com/jefflau/jest-fetch-mock#readme)
- `prop-types` || To type-check our components. See [docs](https://github.com/facebook/prop-types)
- `React Bootstrap` || To add React components with built-in Bootstrap style. See [docs](https://react-bootstrap.github.io/docs/getting-started/introduction)
- `React quill` || To add rich text editor. See [docs](https://www.npmjs.com/package/react-quill)
- `React share` || To add social media share buttons and share counts for React [docs](https://www.npmjs.com/package/react-share)

### 3.3 Server-side libraries

- `nodemon` || To automatically restart the server when in development mode. See [docs](https://nodemon.io/)
- `jest` || To run our tests and coverage. See [docs](https://jestjs.io/)
- `supertest` || To more easily test our endpoints. See [docs](https://github.com/visionmedia/supertest#readme)
- `mongodb-memory-server` || To mock out our database in our backend tests. See [docs](https://github.com/nodkz/mongodb-memory-server)
- `cors` || To open up our API. See [docs](https://github.com/expressjs/cors#readme)
- `mongoose` || To add schemas to our database. See [docs](https://mongoosejs.com/)
- `NODEMAILER` || To send email sending. See [docs](https://nodemailer.com/about/)
