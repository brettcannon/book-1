# Introduction

# Who is this book for?

This book is for most programmers. If you write software that fetches data from a server, or you write server code that provides data to others, this book is for you. It’s particularly relevant to frontend and backend web and mobile developers. If you don’t know modern JavaScript, we recommend [learning that first](bg.md#javascript), but it’s not necessary. For example, if you only know Ruby, you can likely follow the JavaScript server code in Chapter 11 well enough to learn the important concepts of a GraphQL server, most of which will apply to using the `graphql` gem in your Ruby server code.

This book will be especially poignant to these groups of people:

- Backend devs who work on REST APIs and write a lot of similar data-fetching code, or who maintain view-specific endpoints.
- Frontend devs of medium- or large-sized apps who either: A) don’t use a caching library, and manually keep track of what data has already been fetched from the server, or B) use a cache, and write a lot of code to fetch data over REST and put it in the cache (we’re looking at you, Reduxers 👀😄).

# Background

We have a [Background](bg.md) section that provides concise introductions to various background topics. You’re welcome to either look through them now or individually as you go along—at the beginning of a section, you’ll find a list of topics it assumes knowledge of, like the [Anywhere: HTTP](5.md#anywhere-http) section, which has two listed:

> Background: [HTTP](bg.md#http), [JSON](bg.md#json)

Here’s a full list of the topics:

* [JavaScript](bg.md#javascript)
* [JSON](bg.md#json)
* [Git](bg.md#git)
* [Node & npm & nvm](bg.md#node-&-npm-&-nvm)
* [HTTP](bg.md#http)
* [SPA](bg.md#spa)
* [SSR](bg.md#ssr)
* [Latency](bg.md#latency)
* [Webhooks](bg.md#webhooks)  
* [Authentication](bg.md#authentication)
  * [Tokens vs. sessions](bg.md#tokens-vs-sessions)
  * [localStorage vs. cookies](bg.md#localstorage-vs-cookies)  

Some, like *Git* and *Node*, are necessary for following along with the coding. Others, like *Tokens vs. sessions*, are nice to know, but not necessary.

# The book

While this book is great when read cover-to-cover, it’s organized as a reference text, so you can also use it to look up a specific topic. For instance, if you’re familiar with most GraphQL types but want to learn about Unions, you can look them up in the Table of Contents under Chapter 3: Type System—[Section 9: Unions](3.md#unions). Or if you’re already doing basic queries in your React app, and you want to implement infinite scrolling, you can look it up under Chapter 6: React—Section 5: Advanced querying—[Paginating](6.md#paginating).

[Chapter 1](1.md) introduces GraphQL and shows why it’s better than REST.

Chapters [2](2.md) and [3](3.md) explain the language itself and its type system.

[Chapter 4](4.md) goes in depth on how a GraphQL server responds to a query. It’s great for a full understanding of the technology, but you don’t *need* to know it unless you’re contributing to a GraphQL server library. So it’s totally fine to skip this—you’ll still understand everything if you go straight to [Chapter 11](11.md), the practical server-coding chapter.

[Chapter 5: Client Dev](5.md) is the first of the coding chapters, and introduces common concepts among client libraries. Then we have a chapter for each library:

- [Chapter 6: React](6.md)
- [Chapter 7: Vue](7.md)
- [Chapter 8: React Native](8.md)
- [Chapter 9: iOS](9.md)
- [Chapter 10: Android](10.md)

[Chapter 11](11.md) is our looooong server-coding chapter 🤓. All of the examples are in Node with the `apollo-server-express` library, but almost all of the concepts can be applied to [other languages’ GraphQL libraries](11.md).

# The code

We intersperse blocks of code throughout the text. When we add code to a file that we’ve shown previously, we often just display the additions and some context, with ellipses (…) in place of existing code. These additions will be clearest if you read the book with the code open in another window. Further, we believe people tend to learn better if they write things out themselves, so we encourage you to write out the code for each step, and get it working on your computer before moving on to the next step.

We recommend the Chrome browser and the [VS Code](https://code.visualstudio.com/) editor.

If you’re reading this in epub or mobi format on your phone, turning sideways into landscape mode will help reduce code snippet wrapping.

## Git

In Chapters 6–11, you’ll learn through writing an app, step-by-step. Each chapter has its own repository. Each step has a branch in that repo, for example branch `0` for the starter template, branch `1` for the code you write in the first step, etc. These branches contain the most up-to-date version of the code (and are updated through rebasing and force pushing). Snapshots of the steps are taken with tags for every release of the ebook. For instance, in the first version of the book (`the-graphql-guide-r1.pdf`, or r1), the React chapter code is at version `0.1.0`, so the code excerpts correspond exactly with tags `0_0.1.0` for step 0, `1_0.1.0` for step 1, etc. In the second revision of the book (`the-graphql-guide-r2.pdf`), if the code hasn’t changed, the tags will stay the same. In the third revision, if there are small changes to the code, the tags will be in the form `[step number]_0.1.1`.

So for example, if you’re on r1 (which is on `v0.1.0` of the code), and you skip the beginning of Chapter 6 and go straight to the [Listing reviews](6.md#listing-reviews) section, it says to start with step 9 (`9_0.1.0`). So we can look at the app in that state with these terminal commands:

```sh
git clone git@github.com:GraphQLGuide/guide.git
cd guide/
git checkout 9_0.1.0
npm install
npm start
```

> Check out the [git](bg.md#git) and [npm](bg.md#npm) background sections if you’re unfamiliar with these commands.

If we get stuck, we can look at the difference between step 9 and step 10 with GitHub’s compare feature:

`github.com/[repository]/compare/[tag 1]...[tag 2]`

which in our case would be:

[`github.com/GraphQLGuide/guide/compare/9_0.1.0...10_0.1.0`](https://github.com/GraphQLGuide/guide/compare/9_0.1.0...10_0.1.0)

We can also see the solution to the current step by checking out the next step:

```sh
git checkout 10_0.1.0
npm start
```

## Formatting

All the JavaScript code is [ES2016](bg.md#javascript) and formatted with [prettier](https://prettier.io/) with two [settings](https://prettier.io/docs/en/options.html):

`.prettierrc`

```
singleQuote: true
semi: false
```

Which means `'` instead of `"` for string literals and no unnecessary semicolons.

# Resources

If you run into issues, we recommend posting to Stack Overflow with the relevant tag, for instance [`react-apollo`](https://stackoverflow.com/questions/ask?tags=react-apollo) for Chapter 6. If you have the Full edition, you can also ask the community in the #support Slack channel or email the technical support address we gave you.

If the issue is with our code, please search the repository’s issues to see if it’s an existing bug, and if it’s new, submit it! 🙏🙌

[React repo issues](https://github.com/GraphQLGuide/guide/issues)

Another important resource is the docs! Here they are for each library:

- [Chapter 6 and 8: `react-apollo`](https://www.apollographql.com/docs/react/)
- [Chapter 7: `vue-apollo`](https://github.com/akryum/vue-apollo)
- [Chapter 9: Apollo iOS](https://www.apollographql.com/docs/ios/)
- [Chapter 10: `Apollo-Android`](https://github.com/apollographql/apollo-android)
- [Chapter 11: `apollo-server-express`](https://www.apollographql.com/docs/apollo-server/)

# Version

Book version `0.1.0`

Published May 7, 2018

```
graphql @ 0.13
react-apollo @ 2.1
react @ 16.3
```

As we write more of the book, we’ll send you new versions of it (using the email address of the GitHub account you connected when you purchased the book at [graphql.guide](https://graphql.guide)).
