** I'm not going to actively maintain this repo anymore (since Feb 2017), but feel free to fork the project or create PRs **

Possible future improvements:
* Separate the repository to front & back repositories from the current monolithic approach
* Add state container such as [Redux](https://redux.js.org)
* Refactor both server & client side code
* Add front end specific tests with e.g. (Jest)[https://facebook.github.io/jest/], [enzyme](http://airbnb.io/enzyme/)
* Get rid of mutable stuff
* Change `bcrypt-nodejs` (legacy which is not maintained anymore) to [node.bcrypt.js](https://github.com/kelektiv/node.bcrypt.js)
* Considering using CSS-in-JS, e.g. [styled-components](https://styled-components.com)
* Optimization
  * More advanced webpack config
  * Prerendering
  * Code splitting
  
[![Build Status](https://travis-ci.org/avrj/slack-clone.svg?branch=master)](https://travis-ci.org/avrj/slack-clone) [![codecov](https://codecov.io/gh/avrj/slack-clone/branch/master/graph/badge.svg?token=ettfcfGuOA)](https://codecov.io/gh/avrj/slack-clone)

# Slack clone - A real time chat service
Demo: https://zh47.herokuapp.com

Stack:
- React
- Socket.io
- Express
- Node.js
- MongoDB

I didn't use any state container (like Redux) yet, but it might be useful in the future to avoid passing data between components.

## User stories
- Users can choose a nickname
- Users can join chatrooms of their own choosing
- Users can send messages to other users

## Features
- Mobile-friendly UI (Material-UI)
- Stores messages on the server (only messages from channels are saved at the moment, but it's quite easy to extend it to support private messages also)
- Supports multiple logged clients at the same time from one user (e.g. desktop & mobile clients)
- Authentication is made with Passport.js which makes other sign up methods easy to implement (e.g. Facebook OAuth)
- Highlights unread conversations
- Keeps list of online users in real time

## Install & run
The server includes webpack-dev-middleware & webpack-hot-middleware to show code changes on browser without refreshing

```
yarn
yarn start
```

## Testing (Mocha & Chai)
Most of the real time and routes api are covered in the tests.

```
yarn test
```

## Coverage report (Istanbul)
Coverage report can be generated by running
```
yarn coverage
```

## Linting (ESlint)
```
yarn lint
```
to fix most of the warnings automatically:
```
yarn lint:fix
```
