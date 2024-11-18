API Integration in Next.js: A Beginner’s Guide

What is an API?

	•	API stands for Application Programming Interface. It allows different software applications to communicate with each other.
	•	Example: Imagine ordering food in a restaurant. The waiter takes your order (API request) to the kitchen (server) and brings back the food (API response).

Why is API Integration Important in Next.js?

	•	Fetch data from external sources (e.g., weather data, stock prices, user details).
	•	Build dynamic applications that update content without refreshing the page.
	•	Enable communication between the frontend (React) and the backend (server).

Types of API Calls

	1.	GET: Fetch data from a server.
	•	Example: Get user information.
	2.	POST: Send data to a server.
	•	Example: Create a new account.
	3.	PUT/PATCH: Update existing data.
	•	Example: Update a user’s profile.
	4.	DELETE: Remove data.
	•	Example: Delete a user account.

How Next.js Simplifies API Integration

Next.js offers built-in support for:
	•	Server-side rendering (SSR): Fetch data at the server level before rendering the page.
	•	Static site generation (SSG): Fetch data during the build process for pre-rendering.
	•	API routes: Build your own backend APIs within a Next.js application.

Using Fetch for API Calls

1. Fetching Data on the Client Side

Example: Fetching Posts from a Public API

import { useState, useEffect } from 'react';

export default function Posts() {
  const [posts, setPosts] = useState([]);
  const [loading, setLoading] = useState(true);

  useEffect(() => {
    // Fetch data from a public API
    fetch('https://jsonplaceholder.typicode.com/posts')
      .then((response) => response.json()) // Convert response to JSON
      .then((data) => {
        setPosts(data); // Save data to state
        setLoading(false); // Stop loading
      })
      .catch((error) => console.error('Error fetching posts:', error));
  }, []);

  if (loading) return <p>Loading...</p>;

  return (
    <div>
      <h1>Posts</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

Use Case:
	•	Displaying blog posts, product lists, or any real-time data from an API.

2. Fetching Data Server-Side (SSR)

Example: Fetching Data with getServerSideProps

export async function getServerSideProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  const posts = await res.json();

  return {
    props: {
      posts,
    },
  };
}

export default function ServerSidePosts({ posts }) {
  return (
    <div>
      <h1>Posts (Server-Side Rendering)</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

Use Case:
	•	When data needs to be fetched dynamically for every request (e.g., user-specific data).

3. Fetching Data at Build Time (SSG)

Example: Fetching Data with getStaticProps

export async function getStaticProps() {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  const posts = await res.json();

  return {
    props: {
      posts,
    },
    revalidate: 10, // Re-fetch data every 10 seconds
  };
}

export default function StaticPosts({ posts }) {
  return (
    <div>
      <h1>Posts (Static Site Generation)</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

Use Case:
	•	Content that doesn’t change often (e.g., blog posts, FAQs).

API Routes in Next.js

What Are API Routes?

	•	Next.js lets you create custom API endpoints within your project.
	•	These are serverless functions that run in a Node.js environment.

Creating an API Route

	1.	Create a file inside the /pages/api folder.
	2.	The file name becomes the endpoint (e.g., hello.js -> /api/hello).

Example: Basic API Route

// File: /pages/api/hello.js
export default function handler(req, res) {
  res.status(200).json({ message: 'Hello, Next.js API!' });
}

Use Case:
	•	Building custom backends for your application (e.g., user authentication, data manipulation).

Example: API Route with Dynamic Data

// File: /pages/api/posts.js
export default function handler(req, res) {
  const posts = [
    { id: 1, title: 'First Post' },
    { id: 2, title: 'Second Post' },
  ];

  res.status(200).json(posts);
}

Fetching This Data in a Component

export default function CustomAPI() {
  const [posts, setPosts] = useState([]);

  useEffect(() => {
    fetch('/api/posts')
      .then((res) => res.json())
      .then((data) => setPosts(data))
      .catch((error) => console.error('Error fetching posts:', error));
  }, []);

  return (
    <div>
      <h1>Posts from Custom API</h1>
      <ul>
        {posts.map((post) => (
          <li key={post.id}>{post.title}</li>
        ))}
      </ul>
    </div>
  );
}

Use Case:
	•	Fetch data from your own backend services.

Error Handling in API Integration

Try-Catch for Fetch Requests

try {
  const res = await fetch('https://jsonplaceholder.typicode.com/posts');
  if (!res.ok) throw new Error('Failed to fetch data');
  const data = await res.json();
} catch (error) {
  console.error(error.message);
}

Error Handling in API Routes

export default function handler(req, res) {
  try {
    // Some logic
    res.status(200).json({ success: true });
  } catch (error) {
    res.status(500).json({ error: 'Something went wrong' });
  }
}

Tools for Simplifying API Integration

Axios

	•	A popular library for making HTTP requests.
	•	Example:

npm install axios

import axios from 'axios';

useEffect(() => {
  axios.get('https://jsonplaceholder.typicode.com/posts')
    .then((response) => setPosts(response.data))
    .catch((error) => console.error(error));
}, []);



SWR (React Hook for Data Fetching)

	•	Built by the Vercel team for seamless integration with Next.js.
	•	Automatically handles caching, revalidation, and error handling.

Example with SWR

import useSWR from 'swr';

const fetcher = (url) => fetch(url).then((res) => res.json());

export default function Posts() {
  const { data, error } = useSWR('https://jsonplaceholder.typicode.com/posts', fetcher);

  if (error) return <p>Failed to load posts</p>;
  if (!data) return <p>Loading...</p>;

  return (
    <ul>
      {data.map((post) => (
        <li key={post.id}>{post.title}</li>
      ))}
    </ul>
  );
}

Key Takeaways

	1.	Use fetch or libraries like axios for API calls.
	2.	Leverage Next.js features like getStaticProps and getServerSideProps for data fetching.
	3.	Use API routes for custom serverless backend logic.
	4.	Handle errors gracefully to improve user experience.

Would you like practice problems or further clarification?
