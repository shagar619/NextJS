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

## Server-Side Rendering (SSR) in Next.js
**SSR (Server-Side Rendering)** is a rendering strategy in which a page’s **HTML** is generated **on the server** at request time. When a user requests a route, Next.js executes server-side logic (data fetching, authentication, computation, etc.), renders the React components on the server, and returns fully populated HTML to the browser.

**This enables:**
- Faster initial page load (especially for SEO-critical pages)
- Better SEO due to fully prepared HTML
- Dynamic data on each request
- Secure server-only data access at render time

SSR is one of the core rendering modes in Next.js, alongside static generation (SSG), ISR, and client-side rendering (CSR).

**SSR Works (Conceptual Flow):**

1. User requests a route (example: `/dashboard`).
2. Next.js server receives the request.
3. Server executes data-fetching logic

  - API calls
  - Database queries
  - Session validation
  - Business rules, transformations

4. Next.js renders the React component tree on the server, producing HTML.
5. HTML is sent to the browser.
6. Browser hydrates the HTML with React client-side JavaScript.

This ensures content is available before hydration, resulting in better user experience and improved search engine reachability.

**SSR in the App Router (`app/` directory):**
In the App Router, SSR is the default.

Every server component is automatically rendered on the server at request time unless cached.

**SSR Page Example (App Router):**
```typescript
// app/users/page.js
export default async function UsersPage() {
  const res = await fetch("https://api.example.com/users", {
    cache: "no-store"     // ensures SSR - fetches on every request
  });
  const users = await res.json();

  return (
    <div>
      <h1>Active Users</h1>
      <ul>
        {users.map(user => (
          <li key={user.id}>{user.name} — {user.email}</li>
        ))}
      </ul>
    </div>
  );
}
```

**Next.js automatically uses SSR when:**

- A route contains dynamic data fetching with cache: **"no-store"**.
- A route uses searchParams that are not static.
- A route uses cookies or headers (`cookies()`, `headers()`).
- A route calls non-cacheable server functions.

**Use Cases for SSR:**
Appropriate When:
- Content changes frequently (financial dashboards, ticket availability)
- SEO-critical dynamic content (news websites)
- Personalized pages (logged-in dashboards)
- Multi-tenant content (user-specific pages)
- Access-controlled pages (admin panels)

Not Appropriate When:

- Data does not change frequently (prefer static generation)
- No SEO impact and performance matters (prefer CSR)
- High-traffic pages with unnecessary server load (SSR is more expensive)





## Client-Side Rendering (CSR) in Next.js
CSR (Client-Side Rendering) is a rendering strategy in which the browser, not the server, is responsible for generating the UI. The server sends a minimal HTML shell, JavaScript loads on the client, the React app initializes, fetches data, and renders the UI entirely in the browser.

CSR behaves similarly to traditional single-page applications (SPAs) built with React, Vue, or Angular.

In Next.js, CSR is typically used when:

- SEO is not a priority
- The UI depends heavily on real-time interactivity
- Content is personalized on the client side
- You want to offload render-time computation from the server to the client
- Certain data should not run on the server

CSR is often used in combination with SSR, SSG, or ISR, giving Next.js its hybrid rendering capabilities.

**CSR Works (Conceptual Flow):**

1. User loads a page, receiving a minimal HTML shell and bundled JavaScript.
2. The browser downloads the JS bundle.
3. React hydrates the DOM.
4. React executes client-side code, including data-fetching logic.
5. UI is rendered with fetched data directly in the browser.
Subsequent navigation use client-side routing (via next/link and the Next.js Router), avoiding full page reloads.

Thus, CSR delivers a dynamic SPA-like experience.

**How CSR Is Implemented in Next.js:**
- Client Components: Any component marked with `"use client"` at the top is treated as a Client Component. These components run entirely on the client side.
Example:
```typescript
// src/app/page.tsx
"use client";  // Marks this as a Client Component
import { useState, useEffect } from 'react';
const ClientComponent = () => {
  const [data, setData] = useState(null);
  useEffect(() => {
    async function fetchData() {
      const response = await fetch('/api/data');
      const result = await response.json();
      setData(result);
    }
    fetchData();
  }, []);
  return <div>{data ? JSON.stringify(data) : 'Loading...'}</div>;
};
export default ClientComponent;
```
in the App Router, or when data is fetched inside React components in the Pages Router (not via SSR or SSG functions).

**CSR in the App Router (`app/` directory):**
Creating a CSR Component:
```typescript
// app/dashboard/page.js
"use client";

import { useEffect, useState } from "react";

export default function DashboardPage() {
  const [items, setItems] = useState([]);

  useEffect(() => {
    fetch("/api/items")
      .then(res => res.json())
      .then(data => setItems(data));
  }, []);

  return (
    <div>
      <h1>Your Items</h1>
      {items.map(i => (
        <p key={i.id}>{i.name}</p>
      ))}
    </div>
  );
}
```

Characteristics:

- Entire page is rendered in the browser.
- Data fetching only happens on the client via useEffect or similar hooks.
- No data is fetched on the server.
- No SEO benefit because initial HTML is empty until JavaScript executes.

CSR in the Pages Router (pages/ directory):
In the Pages Router, CSR is typically implemented by fetching data inside React components using hooks like `useEffect`.
Example:
```typescript
// pages/dashboard.tsx
import { useEffect, useState } from 'react';
const DashboardPage = () => {
  const [items, setItems] = useState([]);
  useEffect(() => {
    fetch('/api/items')
      .then(res => res.json())
      .then(data => setItems(data));
  }, []);
  return (
    <div>
      <h1>Your Items</h1>
      {items.map(i => (
        <p key={i.id}>{i.name}</p>
      ))}
    </div>
  );
};
export default DashboardPage;
```

**Why CSR here?**

- Frequent data updates
- Real-time UI
- Zero SEO requirements
- Avoids unnecessary server-side rendering cost

**When CSR is the Right Choice:**

1. Highly Interactive Applications

  - Dashboards with client-driven graphs
  - Real-time chats
  - Collaborative editors
  - Trading or monitoring consoles

2. Authenticated or Role-Based UI

  - Complex client-side gated content
  - Token-based API calls made in the browser

3. Applications With Minimal SEO Requirements

  - Admin panels
  - Internal tools
  - SaaS dashboards
  - User-specific analytics

4. Performance Offloading

  - Reduces server-side load when thousands of users fetch UI separately

**Benefits and Tradeoffs of CSR:**

**Benefits**

  - Rich, dynamic, SPA-like user experience
  - Reduced load on the server
  - Real-time updates without reloads
  - Good for applications where SEO is irrelevant

**Tradeoffs**

  - Slower initial paint due to JS execution (time-to-interactive)
  - Initial HTML may be empty → poor SEO
  - Heavier browser work → may affect low-powered devices
  - Requires more client-side JavaScript


**CSR vs SSR vs SSG (Quick Comparison):**
| Aspect               | Client-Side Rendering (CSR)               | Server-Side Rendering (SSR)               | Static Site Generation (SSG)              |
|----------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|
| Initial HTML         | Empty or minimal                          | Fully rendered                            | Fully rendered                            |
| SEO                  | Poor                                      | Good                                      | Good                                      |
| Performance          | Slower initial load                       | Faster initial load                       | Fastest initial load                      |
| Server Load          | Minimal                                   | High                                      | None                                      |
| Use Case             | Interactive apps, dashboards              | Dynamic content, real-time updates        | Blogs, documentation, marketing sites     |


**Hybrid Rendering (CSR + SSR):**
Next.js allows combining CSR and SSR within the same application. You can use SSR for SEO-critical pages and CSR for highly interactive sections, achieving the best of both worlds.
Example:
```typescript
// app/dashboard/page.js
export default async function Dashboard() {
  const profile = await fetchProfile(); // SSR

  return (
    <>
      <Header user={profile} />
      <LiveMetrics />      // CSR client component
    </>
  );
}

// app/dashboard/LiveMetrics.js
"use client";
import { useEffect, useState } from "react";

export default function LiveMetrics() {
  const [data, setData] = useState([]);

  useEffect(() => {
    const interval = setInterval(async () => {
      const res = await fetch("/api/metrics");
      const json = await res.json();
      setData(json);
    }, 2000);

    return () => clearInterval(interval);
  }, []);

  return <MetricsGraph data={data} />;
}
```



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


## Data Fetching and Rendering in Next.js
Next.js is a hybrid React framework, enabling multiple rendering and data-fetching strategies. It allows developers to choose how and when data is fetched and how the HTML is generated for each route or component.

The core categories are:

1. Server-Side Rendering (SSR)
2. Static Site Generation (SSG)
3. Incremental Static Regeneration (ISR)
4. Client-Side Rendering (CSR)
5. React Server Components (RSC) rendering (App Router)
6. Route Handlers and API Routes

Next.js selects rendering behavior based on:

- Where data is fetched (server or client)
- Whether caching is enabled
- Whether the route is static or dynamic
- Whether the component runs in a server or client environment

This hybrid model allows maximum flexibility in building scalable, fast applications.

#### Data Fetching and Rendering in the App Router (`app/` directory)

**Default Behavior: Server Components & Server Rendering**

In the App Router:

- Components are Server Components by default.
- Data fetching is naturally server-side.
- HTML is generated on the server and streamed to the client.
- Client components must be explicitly marked with `"use client"`.

This means SSR is the default unless caching tells Next.js otherwise.

#### Rendering Types in the App Router

**1. Static Rendering (SSG)**

Static pages are generated at build time or during background regeneration.

Next.js automatically statically renders a route when:

- All data uses `fetch()` without `no-store`
- No dynamic functions (`cookies()`, `headers()`, `useSearchParams`)
- No dynamic segment without explicit revalidation

Example:
```typescript
// app/blog/page.tsx
export default async function BlogPage() {
  const res = await fetch('https://api.example.com/posts', {
    cache: 'force-cache' // default behavior
  });
  const posts = await res.json();
  return (
    <div>
      {posts.map(post => (
        <h2 key={post.id}>{post.title}</h2>
      ))}
    </div>
  );
}
```
If the API response is cacheable, this page becomes static.

*Revalidation (ISR)*

You can revalidate static data:
```typescript
const res = await fetch('https://api.example.com/posts', {
  next: { revalidate: 60 } // Revalidate every 60 seconds
});
```

**2. Dynamic Rendering (SSR)**

Triggered when:

- `fetch()` uses cache: `"no-store"`
- Dynamic functions are used:

  - `cookies()`
  - `headers()`
  - `useParams()` or dynamic routes
- Route has dynamic configuration

Example:
```typescript
// app/dashboard/page.tsx
export default async function DashboardPage() {
  const res = await fetch('https://api.example.com/user-data', {
    cache: 'no-store' // forces SSR
  });
  const data = await res.json();
  return <div>Welcome, {data.name}</div>;
}
```
This page is rendered on each request.

**3. CSR (Client-Side Rendering)**

CSR occurs when a component includes `"use client"` and fetches data via React hooks.

Example:
```typescript
// app/profile/page.tsx
"use client";
import { useEffect, useState } from 'react';
export default function ProfilePage() {
  const [profile, setProfile] = useState(null);
  useEffect(() => {
    fetch('/api/profile')
      .then(res => res.json())
      .then(data => setProfile(data));
  }, []);
  return <div>{profile ? `Hello, ${profile.name}` : 'Loading...'}</div>;
}
```
This component fetches data on the client side after hydration.

#### Data Fetching Patterns in the App Router

**1. Fetch inside Server Components (Preferred)**

```typescript
// app/products/page.tsx
export default async function ProductsPage() {
  const res = await fetch('https://api.example.com/products');
  const products = await res.json();
  return (
    <div>
      {products.map(p => (
        <h2 key={p.id}>{p.name}</h2>
      ))}
    </div>
  );
}
```
This fetch runs on the server during rendering.

**2. Fetch in Route Handlers (`app/api/.../route.js`)**

```typescript
// app/api/products/route.ts
import { NextResponse } from 'next/server';
export async function GET() {
  const res = await fetch('https://api.example.com/products');
  const products = await res.json();
  return NextResponse.json(products);
}
```
This creates an API endpoint for client components to consume.

**3. Streaming with Suspense**
Next.js supports streaming HTML with React Suspense for better performance.
```typescript
// app/dashboard/page.tsx
import { Suspense } from 'react';
export default function DashboardPage() {
  return (
    <div>
      <h1>Dashboard</h1>
      <Suspense fallback={<div>Loading stats...</div>}>
        <StatsComponent />
      </Suspense>
    </div>
  );
}
async function StatsComponent() {
  const res = await fetch('https://api.example.com/stats', { cache: 'no-store' });
  const stats = await res.json();
  return <div>{/* render stats */}</div>;
}
```
This allows parts of the page to load independently.

#### Data Fetching and Rendering in the Pages Router (`pages/`)

**1. `getStaticProps` (SSG)**
```typescript
// pages/blog.js
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/posts');
  const posts = await res.json();
  return { props: { posts } };
}
export default function BlogPage({ posts }) {
  return (
    <div>
      {posts.map(post => (
        <h2 key={post.id}>{post.title}</h2>
      ))}
    </div>
  );
}
```
This pre-renders the page at build time.
**2. `getServerSideProps` (SSR)**
```typescript
// pages/dashboard.js
export async function getServerSideProps() {
  const res = await fetch('https://api.example.com/user-data');
  const data = await res.json();
  return { props: { data } };
}
export default function DashboardPage({ data }) {
  return <div>Welcome, {data.name}</div>;
}
```
This renders the page on each request.
**3. Client-Side Fetching (CSR)**
```typescript
// pages/profile.js
import { useEffect, useState } from 'react';
export default function ProfilePage() {
  const [profile, setProfile] = useState(null);
  useEffect(() => {
    fetch('/api/profile')
      .then(res => res.json())
      .then(data => setProfile(data));
  }, []);
  return <div>{profile ? `Hello, ${profile.name}` : 'Loading...'}</div>;
}
```
This fetches data on the client after the page loads.

#### Professional Rendering Patterns

**1. Hybrid Rendering**
Combine SSR and CSR for optimal performance and interactivity.
```typescript
// app/dashboard/page.tsx
export default async function Dashboard() {
  const profile = await fetchProfile(); // SSR
  return (
    <>
      <Header user={profile} />
      <LiveMetrics />      // CSR client component
    </>
  );
}
// app/dashboard/LiveMetrics.js
"use client";
import { useEffect, useState } from "react";
export default function LiveMetrics() {
  const [data, setData] = useState([]);
  useEffect(() => {
    const interval = setInterval(async () => {
      const res = await fetch("/api/metrics");
      const json = await res.json();
      setData(json);
    }, 2000);
    return () => clearInterval(interval);
  }, []);
  return <MetricsGraph data={data} />;
}
```
This approach uses SSR for initial load and CSR for real-time updates.



## Difference Between `getServerSideProps` and `getStaticProps` in Next.js

`getServerSideProps` and `getStaticProps` are both functions used for data fetching in Next.js, but they differ in how and when the data is fetched:
| Aspect                     | getServerSideProps                         | getStaticProps                            |
|----------------------------|--------------------------------------------|-------------------------------------------|
| When Data is Fetched       | On every request to the page               | At build time (static generation)         |
| Use Case                   | Dynamic data that changes frequently       | Static data that doesn't change often      |
| Performance Impact         | Slower initial load due to server rendering| Faster initial load due to pre-rendered HTML |
| Caching                    | No caching, always fresh data              | Can be cached and revalidated                        |
| SEO                        | Good for SEO as HTML is generated on server| Good for SEO as HTML is pre-rendered          |


**1. `getServerSideProps`: Server-Side Rendering (SSR)**

Execution Timing:
- Runs on every request.
- Executes only on the server, never on the client.
- Used when data must always be fresh.

When to Use

Use SSR when:

- The page content changes on every request.
- You need access to user-specific information (cookies, sessions, auth tokens).
- Data is highly dynamic (e.g., stock prices, dashboards, personalized feeds).


Performance:

- Slower than static generation because the server must compute the page for each request.
- Good for real-time or personalized content.
- Not suitable for extremely high-traffic pages unless optimized.

Example:
```typescript
// pages/dashboard.tsx
export async function getServerSideProps(context) {
  const res = await fetch('https://api.example.com/user-data');
  const data = await res.json();
  return { props: { data } };
}
export default function DashboardPage({ data }) {
  return <div>Welcome, {data.name}</div>;
}
```

**2. `getStaticProps`: Static Site Generation (SSG)**

Execution Timing:
- Runs at build time.
- Generates static HTML files that can be served quickly.
- Used when data does not change often.

When to Use SSG when:
- The page content is static or changes infrequently.
- You want the fastest possible load times.

Performance:
- Fastest initial load since HTML is pre-rendered.
- Can be cached globally via CDNs.
- Suitable for blogs, documentation, marketing pages.

Example:
```typescript
// pages/blog.js
export async function getStaticProps() {
  const res = await fetch('https://api.example.com/posts');
  const posts = await res.json();
  return { props: { posts } };
}
export default function BlogPage({ posts }) {
  return (
    <div>
      {posts.map(post => (
        <h2 key={post.id}>{post.title}</h2>
      ))}
    </div>
  );
}
```

## Image Component and Image Optimization in Next.js

Next.js provides a built-in `Image` component that automatically optimizes images for better performance. The `next/image` component offers features like lazy loading, responsive images, and automatic resizing.

It provides advanced features such as:
- Automatic image optimization
- Responsive images with `srcSet`
- Lazy loading by default
- Support for various image formats (JPEG, PNG, WebP, AVIF)
- Automatic resizing
- Built-in caching
- Device-size adaptation
- Layout control
Example Usage:
```typescript
// src/app/page.tsx
import Image from 'next/image';
const HomePage = () => {
  return (
    <div>
      <h1>Welcome to Next.js!</h1>
      <Image
        src="/images/my-image.jpg" // Path to your image
        alt="My Image"
        width={600}                // Desired width
        height={400}               // Desired height
        quality={75}               // Image quality (1-100)
      />
    </div>
  );
};
export default HomePage;
```

#### Key Features of the Next.js Image Component

1. **Automatic Optimization**: Images are automatically optimized on-demand, reducing file size without sacrificing quality.
Example for responsive use:
```typescript
<Image
  src="/images/photo.jpg"
  alt="A photo"
  width={800}
  height={600}
  sizes="(max-width: 600px) 100vw, 800px" // Responsive sizes
/>
```
2. **Lazy Loading**: Images are lazy-loaded by default, meaning they only load when they enter the viewport, improving initial page load times.
3. **Responsive Images**: The `Image` component generates multiple versions of an image for different screen sizes and resolutions, serving the most appropriate one based on the device.
4. **Built-in Caching**: Optimized images are cached for faster subsequent loads.

**Remote Images Support:**
Next.js allows you to optimize images from remote sources by configuring the `next.config.js` file:
```javascript
// next.config.js
module.exports = {
  images: {
    domains: ['example.com'], // Add your remote image domains here
  },
};
```
Then you can use remote images like this:
```typescript
<Image
  src="https://example.com/path/to/image.jpg"
  alt="Remote Image"
  width={800}
  height={600}
/>
```
**Common Image Component Props:**
| Prop        | Description                                      |
|-------------|--------------------------------------------------|
| `src`       | The path or URL of the image                     |
| `alt`       | Alternative text for accessibility               |
| `width`     | Desired width of the image                       |
| `height`    | Desired height of the image                      |
| `quality`   | Image quality (1-100)                            |
| `sizes`     | Responsive sizes for different view ports         |
| `priority`  | Load image with higher priority                  |




## Working with Custom Server Middleware in Next.js

Next.js provides a built-in Middleware system that allows you to run custom code before a request is completed. This executes on the Edge Runtime, enabling extremely fast, low-latency operations such as:

- Authentication and access control
- Redirects and rewrites
- Request logging
- User agent detection
- Geo-based routing
- Request/response transformation

This middleware runs between the user’s request and the route handler/page.

Middleware is a function that executes:

- Before rendering page or API responses
- On the edge, not in Node.js
- For every request that matches its config
- With read-only access to the request body and headers

It allows you to modify:

- Request (`req`)
- Response (`res`) through rewrites, redirects, or NextResponse utilities

Middleware file must be named:
```
middleware.ts
```

Or,
```
middleware.js
```

Basic Middleware Example:
```typescript
// middleware.ts
import { NextResponse } from "next/server";

export function middleware(request) {
  console.log("Middleware executed for:", request.url);

  return NextResponse.next();
}
```




## Advanced Routing & Middleware Capabilities in Next.js

Next.js provides powerful routing customization through Middleware, which runs before a request is completed. It allows you to intercept requests and modify behavior such as authentication checks, rewrites, redirects, and access control.

**1. Enterprise-Grade Middleware Template (Production Ready)**

```typescript
// middleware.ts
import { NextResponse } from 'next/server';
import type { NextRequest } from 'next/server';
import { verifyJWT } from './src/lib/auth/verifyJWT';
import { routeConfig } from './src/config/route-config';

export async function middleware(req: NextRequest) {
  const { pathname } = req.nextUrl;
  const token = req.cookies.get('token')?.value;

  // Public Routes Skip Authentication
  if (routeConfig.publicRoutes.some(route => pathname.startsWith(route))) {
    return NextResponse.next();
  }

  // No token => redirect to login
  if (!token) {
    return NextResponse.redirect(new URL('/login', req.url));
  }

  // Validate Token
  const decoded = await verifyJWT(token).catch(() => null);
  if (!decoded) {
    return NextResponse.redirect(new URL('/login', req.url));
  }

  const userRole = decoded.role;

  // RBAC Enforcement
  for (const { pattern, allowedRoles } of routeConfig.roleBasedRoutes) {
    if (pathname.startsWith(pattern)) {
      if (!allowedRoles.includes(userRole)) {
        return NextResponse.redirect(new URL('/403', req.url));
      }
    }
  }

  // Add security headers
  const response = NextResponse.next();
  response.headers.set('X-Frame-Options', 'DENY');
  response.headers.set('X-Content-Type-Options', 'nosniff');

  return response;
}

export const config = {
  matcher: [
    '/((?!_next|favicon.ico|public|static).*)', // Protect everything except static
  ],
};
```

**2. JWT Authentication Helpers (`verifyJWT.ts`)**

```typescript
// src/lib/auth/verifyJWT.ts
import jwt from 'jsonwebtoken';

export async function verifyJWT(token: string) {
  return jwt.verify(token, process.env.JWT_SECRET as string);
}
```

**3. Centralized Route Configuration (Highly Recommended)**

```typescript
// src/config/route-config.ts
export const routeConfig = {
  publicRoutes: ['/', '/login', '/signup', '/api/public'],

  roleBasedRoutes: [
    {
      pattern: '/admin',
      allowedRoles: ['admin'],
    },
    {
      pattern: '/editor',
      allowedRoles: ['admin', 'editor'],
    },
    {
      pattern: '/dashboard',
      allowedRoles: ['admin', 'editor', 'user'],
    },
  ],
};
```
> This keeps routing logic clean and easily maintainable.

**4. Production Folder Structure for Large-Scale App**

```arduino
src/
  app/
    (public)/
    dashboard/
    admin/
    editor/
    api/
  components/
  hooks/
  lib/
    auth/
      verifyJWT.ts
      hash.ts
    db/
    logger/
  middlewares/
  config/
    route-config.ts
  utils/
  types/
middleware.ts
.env
```

> This matches enterprise expectations and keeps boundaries clear.

**5. App Router Layout-Based Guards (Alternative to Middleware)**

Example: dashboard layout with auth guard
```tsx
// src/app/dashboard/layout.tsx
import { redirect } from 'next/navigation';
import { getAuthSession } from '@/lib/auth/session';

export default async function DashboardLayout({ children }) {
  const session = await getAuthSession();

  if (!session) {
    redirect('/login');
  }

  return <>{children}</>;
}
```

When to use layout guards

- Server-rendered pages needing auth
- Per-section guarding instead of global middleware
- Access to server components context

When NOT to use layout guards

- For API route protection
- For role-based permission enforcement
- To secure static assets
- When requiring uniform global protection


**6. Error Pages: 403 & 500 & 404 Templates**

403 Page
```tsx
// src/app/403/page.tsx
export default function ForbiddenPage() {
  return (
    <div>
      <h1>403 - Forbidden</h1>
      <p>You do not have permission to access this page.</p>
    </div>
  );
}
```

500 Page
```tsx
// src/app/500/page.tsx
export default function ServerError() {
  return <h1>500 - Server Error</h1>;
}
```

404 Page
```tsx
// src/app/not-found.tsx
export default function NotFoundPage() {
  return <h1>404 - Page Not Found</h1>;
}
```

**7. Using Rewrites, Redirects, and Headers via Middleware**

Rewrite Example (Proxy backend)
```typescript
if (pathname.startsWith('/api/users')) {
  const url = req.nextUrl.clone();
  url.pathname = '/api/internal/users';
  return NextResponse.rewrite(url);
}
```

Redirect Example
```typescript
if (pathname === '/old-dashboard') {
  return NextResponse.redirect(new URL('/dashboard', req.url));
}
```

Add Headers
```typescript
response.headers.set('X-App-Env', process.env.NODE_ENV);
```

**8. Optional: Integration with NextAuth Middleware**

If using NextAuth, use:
```typescript
export { default } from 'next-auth/middleware';

export const config = {
  matcher: ['/dashboard/:path*', '/admin/:path*'],
};
```

**9. Full Production-Ready Middleware Blueprint**

Combining everything:
```typescript
// middleware.ts
import { NextResponse } from 'next/server';
import type { NextRequest } from 'next/server';
import { verifyJWT } from './src/lib/auth/verifyJWT';
import { routeConfig } from './src/config/route-config';

export async function middleware(req: NextRequest) {
  const { pathname } = req.nextUrl;
  const token = req.cookies.get('token')?.value;

  // Allow public routes
  if (routeConfig.publicRoutes.some(route => pathname.startsWith(route))) {
    return NextResponse.next();
  }

  // Redirect if not logged in
  if (!token) {
    return NextResponse.redirect(new URL('/login', req.url));
  }

  let decoded;
  try {
    decoded = await verifyJWT(token);
  } catch {
    return NextResponse.redirect(new URL('/login', req.url));
  }

  const role = decoded.role;

  // RBAC enforcement
  for (const route of routeConfig.roleBasedRoutes) {
    if (pathname.startsWith(route.pattern)) {
      if (!route.allowedRoles.includes(role)) {
        return NextResponse.redirect(new URL('/403', req.url));
      }
    }
  }

  // Example rewrite
  if (pathname.startsWith('/proxy/api')) {
    const url = req.nextUrl.clone();
    url.pathname = '/api/internal/proxy';
    return NextResponse.rewrite(url);
  }

  const res = NextResponse.next();

  // Example headers
  res.headers.set('X-Security-Policy', 'active');
  res.headers.set('X-Frame-Options', 'DENY');

  return res;
}

export const config = {
  matcher: ['/((?!_next|static|public).*)'],
};
```



## `proxy.ts` in Next.js

A `proxy.ts` file is not a built-in Next.js file, but it is a commonly used custom utility module developers create to forward or proxy API requests from the Next.js application to external services, backends, or microservices.

It serves as a centralized layer to:

-  CORS issues
- hide backend service URLs
- unify API endpoints
- secure private APIs
- inject middleware logic (headers, auth tokens)
- rewrite or route API paths
- enable server-side communication without exposing secrets to the client

In professional Next.js codebases, a `proxy.ts` file typically handles routing logic in one of these environments:

1. Custom Node.js server (Next.js custom server mode)
2. Next.js Route Handlers (`app/api/.../route.ts`)
3. API Routes (`pages/api/*.ts`)
4. Next.js Middleware (`middleware.ts`)
5. External proxy layer (Nginx, Vercel Edge Functions)

The file name `proxy.ts` is a convention, not a requirement, but it signals that its job is to forward traffic.

Example:
```typescript
import { NextRequest, NextResponse } from "next/server";
import { getDefaultDashboardRoute, getRouteOwner, isAuthRoute, UserRole } from "./lib/auth-utils";
import jwt, { JwtPayload } from "jsonwebtoken";
import { deleteCookie, getCookie } from "./services/auth/tokenHandlers";



// This function can be marked `async` if using `await` inside
export async function proxy(request: NextRequest) {

     const pathname = request.nextUrl.pathname;

     // const accessToken = request.cookies.get("accessToken")?.value || null;

     const accessToken = await getCookie("accessToken") || null;

     let userRole: UserRole | null = null;

     if (accessToken) {
          const verifiedToken: JwtPayload | string = jwt.verify(accessToken, process.env.JWT_SECRET as string);

          if (typeof verifiedToken === "string") {
               await deleteCookie("accessToken");
               await deleteCookie("refreshToken");
               return NextResponse.redirect(new URL('/login', request.url));
          }

          userRole = verifiedToken.role;
     }

     const routeOwner = getRouteOwner(pathname);
     //path = /doctor/appointments => "DOCTOR"
     //path = /my-profile => "COMMON"
     //path = /login => null

     const isAuth = isAuthRoute(pathname);

     // Rule 1 : User is logged in and trying to access auth route. Redirect to default dashboard

     if (accessToken && isAuth) {
          return NextResponse.redirect(new URL(getDefaultDashboardRoute(userRole as UserRole),request.url));
     }

     // Rule 2 : User is trying to access open public route
     if (routeOwner === null) {
          return NextResponse.next();
     }

     // Rule 1 & 2 for open public routes and auth routes handled, now handle protected routes

     // Rule 3 : User is not logged in and trying to access protected route
     if (!accessToken) {
          const loginUrl = new URL('/login', request.url);
          loginUrl.searchParams.set('redirect', pathname);
          return NextResponse.redirect(loginUrl);
     }

     // Rule 4 : User is trying to access common protected route
     if (routeOwner === "COMMON") {
          return NextResponse.next();
     }

     // Rule 5 : User is trying to access role based protected route
     if (routeOwner === "ADMIN" || routeOwner === "DOCTOR" || routeOwner === "PATIENT") {
          if (userRole !== routeOwner) {
               // Redirect to default dashboard
               return NextResponse.redirect(new URL(getDefaultDashboardRoute(userRole as UserRole), request.url));
          }
     }

     return NextResponse.next();
}


export const config = {
     matcher: [
     /*
     * Match all request paths except for the ones starting with:
     * - api (API routes)
     * - _next/static (static files)
     * - _next/image (image optimization files)
     * - favicon.ico, sitemap.xml, robots.txt (metadata files)
     */
     '/((?!api|_next/static|_next/image|favicon.ico|sitemap.xml|robots.txt|.well-known).*)',
],
}
```



## Docker Image in Next.js?

A Docker image in Next.js is a pre-packaged, immutable blueprint that contains:

1. The Next.js application code
2. All required dependencies (Node.js runtime, libraries, packages)
3. Your application’s environment configuration
4. The build output (`.next` folder)
5. Any system-level components needed to run the app

Once created, this image can be executed as a Docker container anywhere—locally, in CI/CD, or on cloud platforms—ensuring consistent behavior across all environments.


## Environment Variables in Next.js
Environment variables allow you to store configuration values outside your codebase, typically used for:

- API keys
- Database connection URLs
- Third-party credentials
- Feature flags
- Runtime configuration

Next.js automatically loads environment variables from specific `.env*` files and injects them into the Node.js runtime (server) or browser (client), depending on how you name them.

**Next.js supports multiple environment files:**
- `.env` - Default environment file
- `.env.local` - Local environment file (not committed to version control)
- `.env.[environment]` - Environment-specific files (e.g., `.env.production`)
- `.env.[environment].local` - Local environment-specific files (e.g., `.env.production.local`)
- `.env.test` - For test environments

#### Naming Rules (Server vs Client)

**1. Server-Only Environment Variables**
Variables WITHOUT the `NEXT_PUBLIC_` prefix are only available on the server:

Examples:
```
DATABASE_URL="postgres://user:password@localhost:5432/mydb"
API_SECRET_KEY="supersecretkey"
```

These variables are never sent to the browser and are SAFE to store sensitive data.

They can be used in:

- Server components (`app/`)
- Route Handlers (`route.js`)
- API Routes (`pages/api/*`)
- `getServerSideProps`
- `getStaticProps`
- Middleware (Edge Runtime)

Usage example:
```typescript
// app/api/data/route.ts
export async function GET() {
  const dbUrl = process.env.DATABASE_URL;
  // Use dbUrl to connect to the database
}
```

**2. Client-Accessible Environment Variables**
Variables WITH the `NEXT_PUBLIC_` prefix are exposed to both server and client:
Examples:
```
NEXT_PUBLIC_API_BASE_URL="https://api.example.com"
NEXT_PUBLIC_ANALYTICS_ID="UA-12345678-1"
```
These variables are included in the client-side bundle and can be accessed in:
- Client components (`"use client"`)
- Pages (`pages/`)
- Client-side JavaScript example:
```typescript
// app/page.tsx
"use client";
export default function HomePage() {
  const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL;
  return <div>API Base URL: {apiUrl}</div>;
}
```


**Environment Variables in the App Router (`app/`)**

**1. Server Components**
In Server Components, you can access both server-only and client-accessible environment variables using `process.env.VARIABLE_NAME`.
Example:
```typescript
// app/api/data/route.ts
export async function GET() {
  const secretKey = process.env.API_SECRET_KEY; // Server-only
  const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL; // Client-accessible
  // Use the variables as needed
}
```

**2. Client Components**
In Client Components (marked with `"use client"`), you can only access client-accessible environment variables prefixed with `NEXT_PUBLIC_`.
Example:
```typescript
// app/page.tsx
"use client";
export default function HomePage() {
  const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL; // Accessible
  const secretKey = process.env.API_SECRET_KEY; // Undefined in client
  return <div>API Base URL: {apiUrl}</div>;
}
```


#### Environment Variables in the Pages Router (`pages/`)

**1. `getServerSideProps`**
In `getServerSideProps`, you can access both server-only and client-accessible environment variables using `process.env.VARIABLE_NAME`.
Example:
```typescript
// pages/index.tsx
export default function HomePage() {
  return <div>API Base URL: {process.env.NEXT_PUBLIC_API_BASE_URL}</div>;
}

export async function getServerSideProps() {
  const secretKey = process.env.API_SECRET_KEY; // Server-only
  const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL; // Client-accessible
  return {
    props: {
      secretKey,
      apiUrl,
    },
  };
}
```

**2. `getStaticProps`**
In `getStaticProps`, you can access both server-only and client-accessible environment variables using `process.env.VARIABLE_NAME`.
Example:
```typescript
// pages/index.tsx
export default function HomePage() {
  return <div>API Base URL: {process.env.NEXT_PUBLIC_API_BASE_URL}</div>;
}

export async function getStaticProps() {
  const secretKey = process.env.API_SECRET_KEY; // Server-only
  const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL; // Client-accessible
  return {
    props: {
      secretKey,
      apiUrl,
    },
  };
}
```


#### Accessing Environment Variables

You can access environment variables using `process.env.VARIABLE_NAME` syntax.
Example:
```typescript
const apiUrl = process.env.NEXT_PUBLIC_API_BASE_URL;
const secretKey = process.env.API_SECRET_KEY; // Server-only
```

**Best Practices**
- Use `.env.local` for sensitive data and local overrides.
- Never commit sensitive information to version control.
- Use `NEXT_PUBLIC_` prefix only for non-sensitive data needed on the client.
- Validate the presence of required environment variables at startup to avoid runtime errors.
```typescript
if (!process.env.DATABASE_URL) {
  throw new Error("DATABASE_URL is not defined");
}
```
- Document required environment variables for your team in the README or a separate configuration file.






## Meta Tags and Titles
Meta tags and titles are essential elements of web pages that provide metadata about the HTML document. They are used by browsers, search engines, and social media platforms to understand the content and context of a page.
In Next.js, you can manage meta tags and titles using the built-in `Head` component from `next/head` in the Pages Router or the `metadata` export in the App Router.

**1. Using `Head` Component (Pages Router)**
In the Pages Router (`pages/` directory), you can use the `Head` component to set meta tags and titles for individual pages.
Example:
```typescript
// pages/index.tsx
import Head from 'next/head';
export default function HomePage() {
  return (
    <>
      <Head>
        <title>Home Page - My Next.js App</title>
        <meta name="description" content="This is the home page of my Next.js application." />
        <meta name="keywords" content="nextjs, react, seo, meta tags" />
        <meta name="author" content="Your Name" />
      </Head>
      <div>
        <h1>Welcome to My Next.js App</h1>
      </div>
    </>
  );
}
```
**2. Using `metadata` Export (App Router)**
In the App Router (`app/` directory), you can define meta tags and titles using the `metadata` export in your page or layout files.
Example:
```typescript
// app/page.tsx
export const metadata = {
  title: 'Home Page - My Next.js App',
  description: 'This is the home page of my Next.js application.',
  keywords: 'nextjs, react, seo, meta tags'
};
export default function HomePage() {
  return (
    <div>
      <h1>Welcome to My Next.js App</h1>
    </div>
  );
}
```
**3. Dynamic Meta Tags**
You can also create dynamic meta tags based on data fetched for the page.
Example:
```typescript
// app/posts/[id]/page.tsx
export async function generateMetadata({ params }) {
  const post = await fetchPostById(params.id);
  return {
    title: post.title,
    description: post.excerpt,
  };
}
export default async function PostPage({ params }) {
  const post = await fetchPostById(params.id);
  return (
    <div>
      <h1>{post.title}</h1>
      <p>{post.content}</p>
    </div>
  );
}
```
**4. Open Graph and Twitter Cards**
You can add Open Graph and Twitter Card meta tags for better social media sharing.
Example:
```typescript
// pages/index.tsx
import Head from 'next/head';
export default function HomePage() {
  return (
    <>
      <Head>
        <title>Home Page - My Next.js App</title>
        <meta property="og:title" content="Home Page - My Next.js App" />
        <meta property="og:description" content="This is the home page of my Next.js application." />
        <meta property="og:image" content="/images/og-image.jpg" />
        <meta name="twitter:card" content="summary_large_image" />
      </Head>
      <div>
        <h1>Welcome to My Next.js App</h1>
      </div>
    </>
  );
}
```
**5. Best Practices**
- Use unique titles and descriptions for each page to improve SEO.
- Keep titles concise (50-60 characters) and descriptions informative (150-160 characters).
- Use relevant keywords in meta tags to enhance search engine visibility.
- Include Open Graph and Twitter Card tags for better social media integration.
Example:
```typescript
// app/page.tsx
export const metadata = {
  title: 'Home Page - My Next.js App',
  description: 'This is the home page of my Next.js application.',
  openGraph: {
    title: 'Home Page - My Next.js App',
    description: 'This is the home page of my Next.js application.',
    images: ['/images/og-image.jpg'],
  },
  twitter: {
    card: 'summary_large_image',
  },
};
export default function HomePage() {
  return (
    <div>
      <h1>Welcome to My Next.js App</h1>
    </div>
  );
}
```


## Uses of `create-next-app`

`create-next-app` is a command-line tool provided by Next.js to quickly set up a new Next.js project with a predefined structure and configuration. It simplifies the initial setup process, allowing developers to start building their applications without worrying about the boilerplate code and configurations.

**1. Instant Project Setup (Zero Configuration)**

Create Next App eliminates the need for manual setup steps such as:

- configuring Webpack or Babel
- setting up TypeScript
- configuring environment variables
- initializing routing and page structure
- setting up development and production scripts

It provides a fully configured boilerplate, allowing developers to start coding immediately.

Example:
```bash
npx create-next-app@latest my-nextjs-app
cd my-nextjs-app
npm run dev
```

**2. Best-Practice Defaults**

The generated template includes:

- optimal folder structure (`app/` or `pages/`)
- recommended TypeScript configuration (optional)
- ESLint rules aligned with Next.js best practices
- built-in support for CSS Modules, Sass, and Tailwind (optional during setup)
- default Git setup and `.gitignore`

This ensures the project adheres to industry standards from day one.

**3. Built-In Performance Optimization**

Next.js is built for high performance, and Create Next App sets up all necessary optimizations:

- automatic code splitting
- image optimization
- font optimization
- caching strategies
- server-side rendering (SSR) and static site generation (SSG) support
- hybrid rendering support

Developers do not need to manually configure these aspects.

**4. Seamless Development Workflow**

Using Create Next App provides:

- hot reloading
- development server (`npm run dev`)
- built-in error overlays
- friendly debugging and linting tools

These features streamline the development lifecycle and reduce friction.

**5. Flexibility and Optional Integrations**

The CLI allows you to pick technologies during setup:

- JavaScript or TypeScript
- Tailwind CSS
- ESLint configuration
- src directory structure
- experimental features

This flexibility lets developers tailor the environment to the project’s needs without complicated configuration.


**6. Production-Ready from Day One**

Next.js is known for its robust production capabilities, including:

- API routes support
- serverless deployments
- edge function support
- file-system routing
- built-in SEO utilities
- environment variable management
- incremental static regeneration (ISR)

Create Next App ensures all these features are enabled and correctly configured from the start.


**7. Avoiding Manual Configuration Errors**

Manually configuring Webpack, Babel, ESLint, routing, and build tools increases the likelihood of misconfiguration. Create Next App eliminates:

- version mismatches
- missing dependencies
- incorrect builds
- security vulnerabilities from outdated boilerplates

This reduces project risk and improves maintainability.

**8. Supported by the Next.js Team**

Because Create Next App is officially maintained by the Next.js (and Vercel) team:

- templates are kept up-to-date
- new Next.js features are immediately integrated
- the CLI receives regular patches and improvements

This ensures long-term stability and compatibility.

