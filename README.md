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


