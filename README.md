<!-- markdownlint-disable MD012 MD026 MD001 MD022 MD032 MD029 MD019 MD034 MD031 MD047 MD040 MD009 MD058 MD024  -->


<div>

 <img src="https://i.ibb.co.com/v6y6tfcf/nextjs.jpg" style="width:100%; height:auto;">

</div>

# NEXT JS

Next.js is a React framework that enables several extra features, including server-side rendering and generating static websites. It is built on top of Node.js, Webpack, and Babel, and it provides a simple and efficient way to create React applications with minimal configuration.
## Features of Next.js
- **Server-Side Rendering (SSR)**: Next.js allows you to render React components on the server side, which can improve performance and SEO.
- **Static Site Generation (SSG)**: Next.js can generate static HTML pages at build time, which can be served quickly to users.
- **API Routes**: Next.js allows you to create API endpoints within your application, making it easy to build full-stack applications.
- **File-Based Routing**: Next.js uses a file-based routing system, where the file structure of the `pages` directory determines the routes of the application.
- **Built-in CSS and Sass Support**: Next.js has built-in support for CSS and Sass, allowing you to style your components easily.
- **Image Optimization**: Next.js provides an Image component that automatically optimizes images for better performance.
- **Fast Refresh**: Next.js includes fast refresh for a better development experience, allowing you to see changes in real-time without losing component state.
- **TypeScript Support**: Next.js has built-in support for TypeScript, making it easy to use TypeScript in your projects.
- **Internationalization (i18n)**: Next.js provides built-in support for internationalized routing and localization.
- **Incremental Static Regeneration (ISR)**: Next.js allows you to update static content after the site has been built, enabling you to keep your static pages up-to-date without a full rebuild.

## Getting Started with Next.js
To get started with Next.js, you can follow these steps:
1. **Install Node.js**: Make sure you have Node.js installed on your machine. You can download it from [nodejs.org](https://nodejs.org/).
2. **Create a New Next.js App**: You can create a new Next.js application using the following command:
```bash
     npx create-next-app@latest my-next-app
     cd my-next-app
```

You will be prompted for the following:
| Prompt | Recommended Response |
|--------|----------------------|
| What is your project named? | my-next-app |
| Would you like to use the recommended Next.js defaults? | No Customize Settings |
| Would you like to use **TypeScript** with this project? | Yes (recommended) |
| Which linter would you like to use? | Eslint |
| Would you like to use **React Compiler**? | Yes (recommended) |
| Would you like to use **Tailwind CSS**? | Yes (recommended) |
| Would you like to use `src/` directory with this project? | Yes (recommended) |
| Would you like to use **App Router** (recommended)? | Yes (recommended) |
| Would you like to customize the **import alias** (`@/*` by default)? | No (default) |
| Would you like to use turbo (recommended)? | Yes (recommended) |


3. **Run the Development Server**: Start the development server with the following command:
```bash
     npm run dev
```

4. **Understanding the Project Structure**:
If you chose the App Router and src directory, you will see a structure similar to:
```
my-app/
├── public/                 # Static assets (images, fonts, robots.txt)
├── src/                    # Main source code
│   ├── app/                # App Router (Routes, Layouts, Metadata)
│   │   ├── (auth)/         # Route Group (doesn't affect URL)
│   │   │   ├── login/
│   │   │   │   └── page.tsx
│   │   │   └── layout.tsx
│   │   ├── api/            # Route Handlers (Backend endpoints)
│   │   │   └── route.ts
│   │   ├── globals.css     # Global styles
│   │   ├── layout.tsx      # Root Layout (required)
│   │   └── page.tsx        # Homepage (/)
│   ├── components/         # Reusable UI components
│   │   ├── ui/             # Shadcn/UI or atomic components
│   │   └── forms/          # Feature-specific components
│   ├── hooks/              # Custom React hooks
│   ├── lib/                # Shared utilities & SDK configs (Prisma, Stripe)
│   ├── actions/            # Server Actions (form submissions, DB logic)
│   ├── types/              # TypeScript interfaces/definitions
│   └── proxy.ts       # Request-level logic (Auth, Redirects)
├── .env.local              # Environment variables
├── next.config.ts          # Next.js configuration
├── tailwind.config.ts      # Styling configuration
└── tsconfig.json           # TypeScript configuration
```

## 🔑 Key Concepts for Modern Apps
- **App Router**: The new routing system in Next.js that uses the `app/` directory to define routes, layouts, and metadata.
- **Server Components**: Components that are rendered on the server, allowing for improved performance and SEO.
- **Client Components**: Components that are rendered on the client side, enabling interactivity and state management.
- **Layouts**: Reusable components that define the structure of pages, allowing for consistent design across the application.
- **Route Handlers**: Functions that handle API requests, allowing you to create backend endpoints within your Next.js application.
- **Server Actions**: Functions that can be called from the client to perform server-side logic, such as form submissions and database operations.


## 🏗️ File Conventions inside `app/`
- **page.tsx**: The main component for a route. Each folder inside `app/` represents a route, and the `page.tsx` file defines the content for that route.
- **layout.tsx**: Defines the layout for a route and its sub-routes. Layouts can include headers, footers, and other common elements.
- **route.ts**: Defines API route handlers for backend endpoints. This file is used to create server-side logic for specific routes.
- **loading.tsx**: A component that is displayed while a route is loading. This can be used to show loading spinners or skeleton screens.
- **error.tsx**: A component that is displayed when an error occurs while rendering a route. This can be used to show error messages to users.
- **template.tsx**: A component that wraps around pages and layouts, allowing you to define common elements that should be present on all pages.
- **proxy.ts**: A component that handles request-level logic, such as authentication and redirects.



## API Routes
API routes in Next.js allow you to create backend endpoints within your application. You can define API routes by creating a `route.ts` file inside the `app/api/` directory. Here's an example of how to create a simple API route:
```typescript
// src/app/api/hello/route.ts
import { NextResponse } from 'next/server';
export async function GET() {
  return NextResponse.json({ message: 'Hello, Next.js API!' });
}
```
In this example, we define a GET endpoint that returns a JSON response with a message. You can create additional API routes by adding more folders and `route.ts` files inside the `app/api/` directory.

## SSR
Next.js supports Server-Side Rendering (SSR) by default. You can create server-rendered pages by exporting an `async` function named `getServerSideProps` from your page component. Here's an example:
```typescript
// src/app/ssr-example/page.tsx
import { GetServerSideProps } from 'next';
export const getServerSideProps: GetServerSideProps = async (context) => {
  // Fetch data from an API or database
  const data = await fetchData();
  return {
    props: {
      data,
    },
  };
};
const SSRExamplePage = ({ data }: { data: any }) => {
  return (
    <div>
      <h1>Server-Side Rendered Page</h1>
      <pre>{JSON.stringify(data, null, 2)}</pre>
    </div>
  );
};
export default SSRExamplePage;
```
In this example, the `getServerSideProps` function fetches data on the server side and passes it as props to the `SSRExamplePage` component.
In this example, the `getServerSideProps` function fetches data on the server side and passes it as props to the `SSRExamplePage` component.
**Key points:**
- **Request from Client**: The user requests a web page from the server.
- **Server-Side Processing**: The server executes the JavaScript code, fetches data if needed, and renders the complete HTML.
- **Sending Rendered HTML to Client**: The fully rendered HTML, along with necessary CSS and JavaScript, is sent to the browser.
- **Client-Side Hydration**: Once the HTML is received, JavaScript runs to enable interactive elements on the client.


## Client-side navigation in Next.js
**Link Component:**
Next.js provides a built-in `Link` component for client-side navigation between pages. This allows for faster transitions without full page reloads. Here's an example of how to use the `Link` component:
```typescript
// src/app/page.tsx
import Link from 'next/link';
const HomePage = () => {
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
      <Link href="/about">
        <a>Go to About Page</a>
      </Link>
    </div>
  );
};
export default HomePage;
```
In this example, clicking the "Go to About Page" link will navigate to the `/about` page using client-side navigation.

**Programmatic Navigation:**
You can also programmatically navigate between pages using the `router` object from `next/router`. Here's an example:
```typescript
// src/app/page.tsx
import { useRouter } from 'next/router';
const HomePage = () => {
  const router = useRouter();
  const handleClick = () => {
    router.push('/about');
  };
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
      <button onClick={handleClick}>Go to About Page</button>
    </div>
  );
};
export default HomePage;
```

## Next.js Routing System
Next.js provides a file-system–based routing architecture, meaning that routes are created automatically based on the directory and file structure within the project.

#### Directory-Based Routing
Every folder inside `app/` represents a route segment, and special files inside segments define how that segment behaves.

**Key Route Segment Files:**
| File Name      | Purpose                                      |
|----------------|----------------------------------------------|
| `page.tsx`      | Defines the main content of a route segment  |
| `layout.tsx`    | Defines the layout for a route segment       |
| `loading.tsx`   | Defines a loading state for a route segment  |
| `error.tsx`     | Defines an error boundary for a route segment|
| `not-found.tsx` | Defines a not-found page for a route segment |
| `template.tsx`   | Wraps pages and layouts for common elements    |
| `route.ts`     | Defines API route handlers for backend logic |
| `proxy.ts`     | Handles request-level logic (Auth, Redirects) |
| `global-error.ts` | Defines a global error boundary for the entire application |
| `default.tsx`  | Defines default exports for route segments    |



Dynamic routing in Next.js refers to the framework’s capability to generate route segments at runtime based on variable URL parameters. Instead of defining every path explicitly, you can create file-based route templates that match multiple URL patterns. This allows you to handle content with unique identifiers—such as blog posts, product pages, or user profiles—without manually creating a separate page file for each instance.
Below is a concise yet comprehensive breakdown of how it works:

**1. File-System Based Dynamic Segments:**
Next.js uses the file system as the primary API for routing. A dynamic segment is created by wrapping a filename or folder name in square brackets:

- `pages/posts/[id].js`
Matches any route shaped like `/posts/<id>`.

- In the App Router (Next.js 13+), dynamic segments exist within the `app/` directory:

    - `app/posts/[id]/page.js`
Matches any route shaped like `/posts/<id>`.
The value inside the brackets is treated as a parameter.
Example: For a URL `/posts/123`, the parameter `id` would have the value `123`.

**2. Accessing Dynamic Parameters:**
**Pages Router (`pages/`):**
- Parameters are available on the `context.params` object inside `getStaticProps`, `getServerSideProps`, and `getStaticPaths`.
- In the component, `useRouter()` provides `router.query`, which includes the param values.

```javascript
// pages/posts/[id].js
import { useRouter } from 'next/router';
const PostPage = () => {
  const router = useRouter();
  const { id } = router.query; // Access dynamic parameter
  return <div>Post ID: {id}</div>;
};
export default PostPage;
```
**App Router (`app/`):**
- Route handlers (server components) receive `params` via the params argument of the layout or page function:
```javascript
// app/posts/[id]/page.js
const PostPage = ({ params }) => {
  const { id } = params; // Access dynamic parameter
  return <div>Post ID: {id}</div>;
};
export default PostPage;
```
- Client components can access params using `useParams()` from `next/navigation`.
```javascript
import { useParams } from 'next/navigation';
const PostPage = () => {
  const params = useParams();
  const { id } = params; // Access dynamic parameter
  return <div>Post ID: {id}</div>;
};
export default PostPage;
```
**3. Pre-rendering with Dynamic Routes:**
- **Static Generation (SSG)**: Use `getStaticPaths` to specify which dynamic routes to pre-render at build time.
```javascript
// pages/posts/[id].js
export async function getStaticPaths() {
  const paths = [{ params: { id: '1' } }, { params: { id: '2' } }];
  return { paths, fallback: false };
}
```
- **Server-Side Rendering (SSR)**: Dynamic routes can also be rendered on each request using `getServerSideProps`.
```javascript
// pages/posts/[id].js
export async function getServerSideProps(context) {
  const { id } = context.params;
  // Fetch data based on id
  return { props: { id } };
}
```
**4. Nested Dynamic Routes:**
You can create nested dynamic routes by combining static and dynamic segments:
- `pages/users/[userId]/posts/[postId].js`
Matches routes like `/users/<userId>/posts/<postId>`.
- In the App Router:
    - `app/users/[userId]/posts/[postId]/page.js`
Matches routes like `/users/<userId>/posts/<postId>`.

**5. Catch-All Routes:**
Next.js supports catch-all routes using triple dots (`...`) in the filename:
- `pages/docs/[...slug].js`
Matches routes like `/docs/a/b/c`, where `slug` is an array of all segments.
- In the App Router:
    - `app/docs/[...slug]/page.js`
Matches routes like `/docs/a/b/c`, where `slug` is an array of all segments.
```javascript
// pages/docs/[...slug].js
import { useRouter } from 'next/router';
const DocsPage = () => {
  const router = useRouter();
  const { slug } = router.query; // slug is an array
  return <div>Slug: {slug.join('/')}</div>;
};
export default DocsPage;
```
**6. Optional Catch-All Routes:**
You can create optional catch-all routes by adding double square brackets:
- `pages/docs/[[...slug]].js`
Matches `/docs`, `/docs/a`, `/docs/a/b`, etc.
- In the App Router:
    - `app/docs/[[...slug]]/page.js`
```javascript
// pages/docs/[[...slug]].js
import { useRouter } from 'next/router';
const DocsPage = () => {
  const router = useRouter();
  const { slug } = router.query; // slug can be undefined or an array
  return <div>Slug: {slug ? slug.join('/') : 'home'}</div>;
};
export default DocsPage;
```


### Comparing App Router and Pages Router
| Feature                     | App Router (`app/` directory)               | Pages Router (`pages/` directory)          |
|-----------------------------|----------------------------------------------|---------------------------------------------|
| Routing Structure           | File-system based with layouts and templates | File-system based without layouts          |
| Data Fetching               | Server and Client Components                 | `getStaticProps`, `getServerSideProps`            |
| Layouts                     | Supported with `layout.tsx` files           | Not supported                               |
| Nested Routes               | Supported with nested folders               | Supported with nested folders               |
| Dynamic Routes              | Supported with `[param]` syntax             | Supported with `[param]` syntax             |
| API Routes                  | Defined in `app/api/` with `route.ts`      | | Defined in `pages/api/` with files         |
| Loading and Error States    | Supported with `loading.tsx` and `error.tsx | Not natively supported                      |
| Server Actions              | Supported                                  | Not supported                              |



URL Structure and Route Segments

Segments can be:
- Static: Fixed names like `about`, `contact`.
- Dynamic: Variable names in brackets like `[id]`, `[slug]`.
- Parallel segments: `@segment`.
- Catch-All: Using `[...]` to capture multiple segments.
- Optional Catch-All: Using `[[...]]` to capture zero or more segments.
- Route Groups: Using parentheses `(group)` to organize routes without affecting the URL.
- Intercepting Routes: Using `()` to create routes that can be accessed from multiple paths.

## Client vs Server Components
Next.js 13 introduced the concept of Server and Client Components to optimize rendering and improve performance. Here's a breakdown of the differences between the two:
| Feature               | Server Components                          | Client Components                         |
|-----------------------|--------------------------------------------|-------------------------------------------|
| Rendering Location    | Rendered on the server                     | Rendered on the client                    |
| Interactivity         | Not interactive, used for static content   | Interactive, can handle user events        |
| Data Fetching         | Can fetch data directly from the server    | Cannot fetch data directly, relies on props or hooks |
| State Management      | Cannot use React state or lifecycle methods| Can use React state and lifecycle methods |
| Bundle Size           | Not included in the client bundle          | Included in the client bundle               |
| Use Cases             | Layouts, static content, data fetching     | Forms, buttons, modals, interactive UI elements |

- By default, files in `app/` are React Server Components (RSC).
- Client components require `"use client"` at the top.
- Routing functions (`useRouter`, `usePathname`, `useSearchParams`) are client-side only.


## Data Fetching and Rendering
Next.js provides several methods for data fetching and rendering, allowing you to choose the best approach for your application's needs. Here are the main methods:
1. **Static Site Generation (SSG)**:
   - Use `getStaticProps` to fetch data at build time.
   - Ideal for pages that can be pre-rendered and do not require frequent updates.
- Example:
```typescript
   // pages/index.tsx
   export async function getStaticProps() {
     const data = await fetchData();
     return { props: { data } };
   }
   const HomePage = ({ data }) => {
     return <div>{data}</div>;
   };
   export default HomePage;
```
2. **Server-Side Rendering (SSR)**:
   - Use `getServerSideProps` to fetch data on each request.
   - Suitable for pages that require up-to-date data on every load.
- Example:
```typescript
     // pages/index.tsx
     export async function getServerSideProps() {
       const data = await fetchData();
       return { props: { data } };
     }
     const HomePage = ({ data }) => {
       return <div>{data}</div>;
     };
     export default HomePage;
```
3. **Client-Side Fetching**:
   - Use React hooks like `useEffect` to fetch data on the client side.
   - Useful for interactive pages where data needs to be fetched after the initial render.
- Example:
```typescript
     // pages/index.tsx
     import { useEffect, useState } from 'react';
     const HomePage = () => {
       const [data, setData] = useState(null);
       useEffect(() => {
         async function fetchData() {
           const response = await fetch('/api/data');
           const result = await response.json();
           setData(result);
         }
         fetchData();
       }, []);
       return <div>{data}</div>;
     };
     export default HomePage;
```
4. **Incremental Static Regeneration (ISR)**:
   - Use `revalidate` in `getStaticProps` to update static pages after a specified interval.
   - Allows you to keep static content fresh without rebuilding the entire site.
- Example:
```typescript
     // pages/index.tsx
     export async function getStaticProps() {
       const data = await fetchData();
       return {
         props: { data },
         revalidate: 60, // Revalidate every 60 seconds
       };
     }
     const HomePage = ({ data }) => {
       return <div>{data}</div>;
     };
     export default HomePage;
```
5. **Server Actions**:
   - Functions that can be called from the client to perform server-side logic, such as form submissions and database operations.
- Example:
```typescript
     // src/app/contact/page.tsx
     'use server';
     export async function submitForm(data: FormData) {
       // Handle form submission on the server
     }
     const ContactPage = () => {
       return (
         <form action={submitForm}>
           {/* Form fields */}
         </form>
       );
     };
     export default ContactPage;
```
