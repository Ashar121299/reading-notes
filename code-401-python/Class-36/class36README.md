## What is SWR

### What is SWR?

SWR stands for stale-while-revalidate, a HTTP cache invalidation strategy popularized by HTTP RFC 5861. It basically means that it performs data fetching in 3 steps:

- Returns cached data first (stale)
- Sends the fetch request (revalidate)
- Returns the up-to-date data

SWR is created by Vercel and one of its advantages is that it is a fast and lightweight package. It is a layer built on top of Fetch API and therefore provides 
additional features on top of just data fetching. These features include caching, pagination, auto revalidation and more.

### Why use SWR?

1. Built-in Cache + Real-Time Experience

When we use Fetch or Axios for data fetching in React, we usually need to show the user some loading message or spinner while data is being fetched. Using SWR’s 
strategy, the user sees the cached (stale) data first and requests are automatically being cached. Components will always be constantly updated with the most recent 
data, ensuring UI will always be fast and reactive.

2. Auto Revalidation

SWR ensures that the user sees the most up-to-date data. So even with multiple tabs or windows, the data is always fresh and in sync when the window/tab is refocused.

![image](https://blog.openreplay.com/a3042d7185623fdfbf7192e6ea76904e/img1.gif)

3. Pagination
One of the most useful features of SWR is that it supports pagination and infinite loading of data.

4. More Features + Benefits of SWR
There are many more reasons why you should use SWR in your React apps. Some of them are:

- Local mutation
- Dependent fetching
- Smart error retry
- Supports fetching from both REST and GraphQL APIs
- Typescript and React Native ready

### Open Source Session Replay

OpenReplay is an open-source, session replay suite that lets you see what users do on your web app, helping you troubleshoot issues faster. OpenReplay is self-hosted
for full control over your data.

![image](https://blog.openreplay.com/static/0a3dcbea2c3ddf66242e78ffd2a65233/412e4/banner-blog.png)

## SWR Docs

### Overview

import useSWR from 'swr'

function Profile() {
  const { data, error, isLoading } = useSWR('/api/user', fetcher)

  if (error) return <div>failed to load</div>
  if (isLoading) return <div>loading...</div>
  return <div>hello {data.name}!</div>
}

In this example, the useSWR hook accepts a key string and a fetcher function. key is a unique identifier of the data (normally the API URL) and will be passed to
fetcher. fetcher can be any asynchronous function which returns the data, you can use the native fetch or tools like Axios.

The hook returns 2 values: data and error, based on the status of the request.

### Features

With just one single line of code, you can simplify the logic of data fetching in your project, and also have all these amazing features out-of-the-box:

- Fast, lightweight and reusable data fetching
- Built-in cache and request deduplication
- Real-time experience
- Transport and protocol agnostic
- SSR / ISR / SSG support
- TypeScript ready


SWR has you covered in all aspects of speed, correctness, and stability to help you build better experiences:

- Fast page navigation
- Polling on interval
- Data dependency
- Revalidation on focus
- Revalidation on network recovery
- Local mutation (Optimistic UI)
- Smart error retry
- Pagination and scroll position recovery
- React Suspense
- React Native
