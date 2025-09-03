## L05 - Routing Fundamentals

Next.js utilizes a **file system-based routing system**, where the URLs accessible in your browser are determined by the organization of your files and folders in your code. This approach emphasizes **conventions over configuration**, meaning you don't typically need to install or configure a separate router.

### Project Setup

1.  Create a new Next.js project using `npx create next app@latest <project-name>`.
2.  Navigate to the `src` folder.
3.  To start fresh, you can delete any existing `app` folder within `src`.

### Core Routing Conventions

There are three primary conventions to remember for Next.js routing:

1.  **All routes must reside inside the `app` folder** (within the `src` directory).
2.  Route files must be named either **`page.js` or `page.tsx`** (depending on whether you are using TypeScript).
3.  **Each folder represents a segment of the URL path**.

When these conventions are followed, the file automatically becomes available as a route.

### Creating a Homepage (Root Route)

To create a homepage that appears at your site's root URL (e.g., `localhost:3000/`):

1.  Create an `app` folder inside your `src` directory.
2.  Inside the `app` folder, create a file named `page.tsx` (or `page.js`).
3.  From this file, **default export a simple React component**. For example:

    ```typescript
    export default function Home() {
        return <h1>Welcome home</h1>;
    }
    ```

4.  Run `npm run dev` in your terminal to start the development server.
5.  Visiting `localhost:3000` will now display "Welcome home".

> **Key Concept:** A `page.tsx` file directly inside the `app` folder automatically maps to the root URL (`/`).

### The `layout.tsx` File

Even if you delete the `layout.tsx` file when initially removing the `app` folder, Next.js will **automatically create and set it up** behind the scenes when you first access the root route. This file is crucial for shared layouts but will be explored in more depth in later discussions.

### Creating Sub-Routes

To create additional routes like `/about` or `/profile`:

1.  **For `/about`:**
    -   Create a new folder named `about` inside the `app` folder.
    -   Inside the `about` folder, create a `page.tsx` file.
    -   Default export a React component from `page.tsx`. For example:
        ```typescript
        export default function About() {
            return <h1>About me</h1>;
        }
        ```
2.  **For `/profile`:**
    -   Similarly, create another folder named `profile` inside the `app` folder.
    -   Inside the `profile` folder, create a `page.tsx` file.
    -   Default export a React component from `page.tsx`. For example:
        ```typescript
        export default function Profile() {
            return <h1>My profile</h1>;
        }
        ```

After saving, navigating to `localhost:3000/about` will show the "About me" page, and `localhost:3000/profile` will show the "My profile" page.

> **Key Concept:** Routes are directly tied to their folder names within the `app` directory. For instance, a `page.tsx` file inside an `about` folder maps to the `/about` route.

### Route Mapping Summary

-   `app/page.tsx` maps to the **root route (`/`)**.
-   `app/folder_name/page.tsx` maps to a URL segment (e.g., `app/about/page.tsx` maps to `/about`).

### Handling Non-Existent Routes (404)

If someone attempts to access a URL that does not correspond to any file in your `app` folder (e.g., `localhost:3000/dashboard` if no `/dashboard` route exists), Next.js automatically serves up a **404 Not Found response**. You do not need to write any specific code to handle these non-existing routes.

### Benefits of File-Based Routing

The beauty of Next.js's file system-based routing is that:

-   You **don't need to install and configure a router** in your code.
-   Your **file and folder structure does all the heavy lifting**, streamlining development and making routes intuitive to understand and manage.
