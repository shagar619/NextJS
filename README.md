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
