# Ramp-up Project
This is meant to be a fairly open-ended project to get you more familiar with the technologies used in our client project this semester with Storr. Reach out to us if you have any questions or concerns :)

## Setup
- Clone this repo and make a new branch with your name
- Make two new directories under the root, `server` and `client`. We recommend splitting up the two because you will be installing different node modules and using different boilerplates.
- Install Node if you don't have it:
  - MacOS: `brew update` then `brew install node`
  - Windows: Follow [this guide](https://blog.teamtreehouse.com/install-node-js-npm-windows)
  - Linux: Download and install binary from the [Node website](https://nodejs.org/en/download/)
- Test your Node installation: Make sure the commands `node -v` and `npm -v` can run

## Server
First, let's create an Apollo Express server using GraphQL.

### Prerequisites:
- [TutorialsPoint](https://www.tutorialspoint.com/typescript/index.htm) has a good introductory tutorial of Typescript. Typescript is essentially a typed version of Javascript so we recommend going through Javascript tutorials if you aren't familiar with it first. Feel free to use go through as much of this tutorial as you need and to use it as a reference.
- Read *and* code through [this Medium article](https://blog.bitsrc.io/keep-your-promises-in-typescript-using-async-await-7bdc57041308) to understand how the async/await system works in Typescript. The Storr codebase has a lot of async/await so this will be useful later on.
- [This site](https://www.howtographql.com/basics/0-introduction/) has a good introduction to GraphQL (recommended to read through `Introduction` to `Big Picture: Architecture` at least)
- [The Apollo docs](https://www.apollographql.com/docs/apollo-server/) explains what Apollo Server is. Feel free to read through to get a general idea of the Apollo Server, although we would not recommend following the code since it is all in Javascript (not Typescript). `Essentials/Understanding schema concepts` talks more about GraphQL schemas.

### Code:
- Make sure you are in the `server` directory
- Follow [this Medium tutorial](https://medium.com/@th.guibert/basic-apollo-express-graphql-api-with-typescript-2ee021dea2c) to get a basic Hello World GraphQL Apollo server running
- This part is open-ended. Extend your GraphQL schema beyond the basic Hello World and create custom resolvers for your new queries and mutations to satisfy the criteria below. Feel free to use static data to back up your server, or use a database if you're feeling fancy.
- A great resource to auto-generate Typescript types based on a GraphQL schema is [graphql-codegen](https://graphql-code-generator.com/docs/getting-started/). Follow the steps `Installation` and then `Setup` to use it.
- Make sure that your code satisfies the following criteria:
  - Use `async` for your resolvers even if they are synchronous
  - Use `graphql-codegen`
  - Make sure your GraphQL schema:
    - Has at least 2 queries and at least 2 mutations (along with their resolvers)
    - Has at least 1 query and at least 1 mutation with argument(s)
    - Uses types with the `!` suffix&mdash;What does this mean?
    - Has at least 1 nested type, e.g.:
    ```
    type Car { ... }
    
    type Person {
      ...
      car: Car
    }
    ```
  - TODO: Add more criteria here
  
### Deliverables:
- Run your server locally and navigate to the GraphQL endpoint
  - If you followed the Medium tutorial above, this should be `http://localhost:3000/graphql`
- Demonstrate some GraphQL queries using the GraphQL Playground interface

## Client
Now that we have our server running, let's build a simple React Native app that uses the Apollo Client to interact with our server.

### Prerequisites:
- [Facebook's React Native tutorial](https://facebook.github.io/react-native/docs/getting-started) is great if you're a beginner to React/React Native. Give it a read or use it as a reference. Warning: this is in Javascript
- [This tutorial](https://www.howtographql.com/react-apollo/0-introduction/) guides you through building a Hackernews-like React app. Warning that it uses Javascript not Typescript (although the two are very similar) and that it is for React and not React Native (although the two are very similar). We would recommend using this as a reference.

### Code:
- Make sure you are in the `client` directory
- Follow the `Getting Started` section of [Facebook's React Native tutorial](https://facebook.github.io/react-native/docs/getting-started)
  - We recommend you use Expo for a fast setup. Follow the Expo instructions for how to test your Expo app on your iOS or Android phone. Make sure that after you run `expo init <Project-name>` that you select the *blank*, *typescript* configuration for your app.
- This part is open-ended. Create a React Native app that allows you to interact with all of your queries and mutations in your server. Make sure it satisfies the criteria below.
  - Sometime here you will need to set up an Apollo Client. Apollo Client is needed to make queries and mutations to your Apollo Server. Follow the steps in the [Apollo Docs](https://www.apollographql.com/docs/react/essentials/get-started/) to get started (warning: in Javascript but it is very similar to Typescript).
  - Sometime here you will need to use your Apollo Client to make queries and mutations. Read through `Essentials/Queries` and `Essentials/Mutations` in the Apollo Docs to familiarize yourself. Also, the [Using Apollo with Typescript](https://www.apollographql.com/docs/react/recipes/static-typing/) guide also in the Apollo Docs may be helpful with dealing with Typescript.
