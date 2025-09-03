# L06 - Nested Routes

Next.js leverages its file-based routing system to make nested routes exceptionally straightforward to implement, automatically mirroring your folder structure in the URLs.

### Core Concept

-   Building on the foundational understanding that `page.tsx` files in folders map to URL segments, **nested routes** are created by simply introducing subfolders within existing route folders.

### Scenario: Implementing `/blog`, `/blog/first`, and `/blog/second`

Let's break down how to create a main blog page and two nested blog post pages:

1.  **Setting up the Main Blog Page (`/blog`):**

    -   **Create a `blog` folder** inside your `app` directory.
    -   Inside this new `blog` folder, add a **`page.tsx` file**.
    -   Default export a simple React component from `page.tsx`.

        ```typescript
        // app/blog/page.tsx
        export default function Blog() {
            return <h1>My blog</h1>;
        }
        ```

    -   This setup immediately makes `localhost:3000/blog` accessible, displaying "My blog".

2.  **Creating Nested Blog Posts (`/blog/first` and `/blog/second`):**

    -   **For `/blog/first`:**

        -   Inside the existing `blog` folder, **create a new folder named `first`**.
        -   Inside this `first` folder, create a **`page.tsx` file**.
        -   Default export its specific React component.

            ```typescript
            // app/blog/first/page.tsx
            export default function FirstBlog() {
                return <h1>First blog post</h1>;
            }
            ```

        -   Navigating to `localhost:3000/blog/first` will now render "First blog post".

    -   **For `/blog/second`:**

        -   Similarly, inside the `blog` folder, **create another new folder named `second`**.
        -   Inside this `second` folder, create a **`page.tsx` file**.
        -   Default export its specific React component.

            ```typescript
            // app/blog/second/page.tsx
            export default function SecondBlog() {
                return <h1>Second blog post</h1>;
            }
            ```

        -   Visiting `localhost:3000/blog/second` will display "Second blog post".

### Visualization and Key Takeaway

The file and folder structure directly dictates the URL paths:

-   `app/page.tsx` maps to the **root route (`/`)**.
-   `app/blog/page.tsx` maps to `/blog`.
-   `app/blog/first/page.tsx` maps to `/blog/first`.
-   `app/blog/second/page.tsx` maps to `/blog/second`.

The **key takeaway** is that Next.js automatically mirrors your folder structure directly in your URLs. This makes creating and managing nested routes incredibly simple and intuitive within the App Router.
