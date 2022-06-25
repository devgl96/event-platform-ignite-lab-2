# Ignite Lab 2

This event is building an application called 'event-platform'.

## Installation

- npm create vite@latest
- npm install
- npm i tailwindcss postcss autoprefixer -D
- npx tailwindcss init -p

## Cleaning the code

Remove all the files .css and .svg from main folder.

## What's CMS?

CMS is Content Management System. WordPress uses this concept but it comes with admin and frontend panels.
In this project, we'll use the Headless CMS because the data comes through an API REST or GraphQL.

### GraphQL

- Query = Search data
- Mutation = Create, update or delete data

### Over Fetching and Under Fetching

The first one happens when the request by the backend returns all the data but it is more than necessary.
The second one happens when the request by the backend returns less data than necessary.

### Apollo Client

- npm i @apollo/client graphql
- Cache

### It can be made like this

```ts
import { gql } from "@apollo/client";
import { useEffect } from "react";
import { client } from "./lib/apollo";

const GET_LESSONS_QUERY = gql`
  query {
    lessons {
      id
      title
    }
  }
`;

function App() {
  useEffect(() => {
    client
      .query({
        query: GET_LESSONS_QUERY,
      })
      .then((response) => {
        console.log(response.data);
      });
  }, []);
  return <h1 className="text-5xl font-bold text-violet-500">Hello World</h1>;
}

export default App;
```

Using a website to transform svg in jsx code (svg in jsx)[https://svg2jsx.com/]

Install phospor-react

- npm i phosphor-react

Install a library to date format

- npm i date-fns (we'll use this library)
- npm i dayjs

Put video in website
https://videojs.com/
https://vimejs.com/ (we'll use this library)
npm i @vime/core @vime/react

Install react-router-dom

- npm i react-router-dom

See more about 'react-hook-form'

Install a classnames lib

- npm i classnames

(Working with GraphQL Code Generator)[https://www.graphql-code-generator.com/]

- npm i @graphql-codegen/cli -D
- npm i @graphql-codegen/typescript @graphql-codegen/typescript-operations @graphql-codegen/typescript-react-apollo -D
- npm run codegen
