# Ramp-up Project
This is meant to be a fairly open-ended project to get you more familiar with the technologies used in our client project this semester with Storr. Reach out to us if you have any questions or concerns :)

[WARNING] Some resources are in JavaScript. Keep in mind that we will be writing code in Typescript, which is a typed version of JavaScript (we will have warnings along the way, don't worry).

## Code Health
Before we dive into the project, we want to talk about code health. Since your code for the semester will eventually be pushed into the actual Storr codebase, it needs to be maintainable and clean. Here are a few things to keep in mind:
- Maintain a *consistent coding style*. Storr uses [this style guide](https://github.com/airbnb/javascript) (includes a part for React as well), so make sure to follow it as you code. We also recommend configuring your editor to indent with two spaces, to have a ruler for tracking line height, and to have linting for Typescript. 
- Organize your code into directories based on function and use imports/exports to access code in different directories. We're not going to enforce a certain structure, but you could Google resources like [this React Native guide](https://medium.com/the-andela-way/how-to-structure-a-react-native-app-for-scale-a29194cd33fc) structuring guide to figure out how to structure your code.
- Make your code modular and avoid repetition. Each function should be relatively short and serve one main purpose, and there should be minimal repeated code between any of your functions. 

* Tip: If you use VSCode, install the plugin `Prettier` and enable the option to `Lint on Save`.

## Goal
By the end of this project, you will create a Apollo Express server to interact with GraphQL and a React Native frontend!

## Setup
1. Clone this repo.

2. Make two new directories under the root, `server` and `client`. We recommend splitting up the two because you will be installing different node modules and using different boilerplates. Push the two directories to the master branch.

3. Install Node if you don't have it:
  - MacOS: `brew update` then `brew install node`
  - Windows: Follow [this guide](https://blog.teamtreehouse.com/install-node-js-npm-windows)
  - Linux: Download and install binary from the [Node website](https://nodejs.org/en/download/)
  
4. Test your Node installation: Make sure the commands `node -v` and `npm -v` can run.

## Server
First, let's create an Apollo Express server using GraphQL.

### Prerequisites:
- [TutorialsPoint](https://www.tutorialspoint.com/typescript/index.htm) has a good introductory tutorial of Typescript. Feel free to use go through as much of this tutorial as you need and to use it as a reference.
- Read *and* code through [this Medium article](https://blog.bitsrc.io/keep-your-promises-in-typescript-using-async-await-7bdc57041308) to understand how the async/await system works in Typescript. The Storr codebase has a lot of async/await so this will be useful later on.
- [This site](https://www.howtographql.com/basics/0-introduction/) has a good introduction to GraphQL (recommended to read through `Introduction` to `Core Concepts` at least).
- [The Apollo docs](https://www.apollographql.com/docs/apollo-server/) explains what Apollo Server is. Feel free to read through to get a general idea of the Apollo Server, although we would not recommend following the code since it is all in Javascript (not Typescript). `Essentials/Understanding schema concepts` talks more about GraphQL schemas.

### Code:
1. Make sure you are in the `server` directory. Make a new branch called `server` and complete the following steps on that branch.

2. Follow [this Medium tutorial](https://medium.com/@th.guibert/basic-apollo-express-graphql-api-with-typescript-2ee021dea2c) to get a basic Hello World GraphQL Apollo server running.

3. This part is open-ended. Extend your GraphQL schema beyond the basic Hello World and create custom resolvers for your new queries and mutations to satisfy the criteria below. Feel free to use static data to back up your server, or use a database if you're feeling fancy.

4. A great resource to auto-generate Typescript types based on a GraphQL schema is [graphql-codegen](https://graphql-code-generator.com/docs/getting-started/). Follow the steps `Installation` and then `Setup` to use it.

5. Make sure that your code satisfies the following criteria:
  - Use `async` for your resolvers even if they are synchronous.
  - Use `graphql-codegen`.
  - Make sure your GraphQL schema:
    - Has at least 2 queries and at least 2 mutations (along with their resolvers).
    - Has at least 1 query and at least 1 mutation with argument(s).
    - Has at least 3 different field types (e.g. `String`, etc).
    - Uses types both with and without the `!` suffix&mdash;What does this mean? E.g.
    ```
    type Person {
      name: String!
    }
    ```
    vs
    ```
    type Person {
      name: String
    }
    ```
    - Has at least 1 nested type, e.g.
    ```
    type Car { ... }
    
    type Person {
      ...
      car: Car
    }
    ```
  
### Deliverables:
- Run your server locally and navigate to the GraphQL endpoint.
  - If you followed the Medium tutorial above, this should be `http://localhost:3000/graphql`.
- Demonstrate some GraphQL queries using the GraphQL Playground interface.
- Once you are finished, make a pull request for your branch with a brief description of your GraphQL schema.

## Client
Now that we have our server running, let's build a simple React Native app that uses the Apollo Client to interact with our server.

### Prerequisites:
- [Facebook's React Native tutorial](https://facebook.github.io/react-native/docs/getting-started) is great if you're a beginner to React/React Native. Give it a read or use it as a reference. Warning: this is in Javascript.
- [This tutorial](https://www.howtographql.com/react-apollo/0-introduction/) guides you through building a Hackernews-like React (not React Native) app in JavaScript. We would recommend using this as a reference.
- [This page](https://facebook.github.io/react-native/blog/2018/05/07/using-typescript-with-react-native) in Facebook's blog is useful for learning the basics of React Native in *Typescript*, not Javascript.

### Code:
1. Make sure you are in the `client` directory. Make a new branch called `client` and complete the following steps on that branch.

2. Follow the `Getting Started` section of [Facebook's React Native tutorial](https://facebook.github.io/react-native/docs/getting-started). We recommend you use **Expo** for a fast setup. Follow the Expo instructions for how to test your Expo app on your iOS or Android phone. Make sure that after you run `expo init <Project-name>` that you select the *blank*, *typescript* configuration for your app.

3. This part is open-ended. Create a React Native app that allows you to interact with all of your queries and mutations in your server. Make sure it satisfies the criteria below.
  - Sometime here you will need to set up an Apollo Client. Apollo Client is needed to make queries and mutations to your Apollo Server. Follow the steps in the [Apollo Docs](https://www.apollographql.com/docs/react/essentials/get-started/) to get started (warning: in Javascript).
  - Sometime here you will need to use your Apollo Client to make queries and mutations. Read through `Essentials/Queries` and `Essentials/Mutations` in the Apollo Docs to familiarize yourself. Also, the [Using Apollo with Typescript](https://www.apollographql.com/docs/react/recipes/static-typing/) guide also in the Apollo Docs may be helpful with dealing with Typescript.
  - Sometime here you will also need to allow your app to transition between screens (it's in the criteria). Read through the steps in this [React Native guide](https://reactnavigation.org/docs/en/getting-started.html) to learn about how to do this navigation using `react-native-navigation` (warning: in Javascript). [This guide](https://dev.to/andreasbergqvist/react-navigation-with-typescript-29ka) can help you translate to Typescript.
  - If you need any types from your server, import them from your server rather than repeating them here.

4. Make sure that your code satisfies the following criteria:
- Interact with all of the queries and mutations in your GraphQL server. Try to use as many React Native components as you can (`Text`, `TextInput`, `Button`, `FlatView`, etc).
- Has at least two screens with navigation using `react-native-navigation`.

### Deliverables:
- Show us your app on your phone or an emulator if you chose to go down the native route rather than Expo! Use the playground to show that your app is actually modifying data in the server.
- Once you are finished, make a pull request for your branch with a brief description of your app.

## Finally
1. Push your branch and make a pull request with a succinct description of your project.
2. We will have you guys demo your projects at our next meeting! Have fun :)

To reiterate on the criteria:

**Server**
- Use `async` for your resolvers even if they are synchronous
- Use `graphql-codegen`
- Make sure your GraphQL schema:
    - Has at least 2 queries and at least 2 mutations (along with their resolvers).
    - Has at least 1 query and at least 1 mutation with argument(s).
    - Has at least 3 different field types (e.g. `String`, etc)
    - Uses types both with and without the `!` suffix
    - Has at least 1 nested type

**Client**
- Interact with all of the queries and mutations in your GraphQL server. Try to use as many React Native components as you can (`Text`, `TextInput`, `Button`, `FlatView`, etc).
- Has at least two screens with navigation using `react-native-navigation`.

## Troubleshooting

```
$ graphql-codegen init
internal/modules/cjs/loader.js:582
    throw err;
    ^

Error: Cannot find module 'graphql'
```

Sometimes the command doesn't work on CLI. Try adding a new script command in `package.json` and run `npm run generate` instead.

```
{
  "scripts": {
    "generate": "graphql-codegen"
  }
}
```

