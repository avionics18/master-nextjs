# L03 - Project Structure

This tutorial explains the structure of a Next.js project, detailing the purpose of its files and folders, and how they contribute to the application's functionality.

#### **1. Project Overview**

-   When the "hello world" project is opened in VS Code, it contains **four folders and ten files** at the root level.
-   Understanding this structure is key to how the application runs.

#### **2. Root Level Files**

-   **`package.json`**:
    -   **Dependencies**: Lists essential project dependencies like **Next.js (version 15), React, and React DOM (version 19)**.
    -   May also include TypeScript, Tailwind CSS, Post CSS, and ESLint packages depending on setup choices.
    -   **Scripts**:
        -   `dev`: For running the application in **development mode**.
        -   `build`: For creating **production builds**.
        -   `start`: For running the **production server**.
        -   `lint`: For setting up Next.js's built-in ESLint configuration.
-   **Configuration Files**:
    -   `next.config.js`: For Next.js specific settings.
    -   `tsconfig.json`: For TypeScript configuration.
    -   `eslint.config.js`: For ESLint configuration.
    -   `tailwind.config.ts`: For Tailwind CSS configuration.
-   **Other Files (Less Focus)**:
    -   `package-lock.json`: Ensures consistent installation of dependencies.
    -   `.gitignore`: For Version Control, specifying files/folders to ignore.
    -   `README.md`: Contains instructions for running, building, and deploying the application.
    -   `next-env.d.ts`: Contains TypeScript declarations for Next.js.

#### **3. Root Level Folders**

-   **`.next` folder**:
    -   Created when `dev` or `build` scripts are run.
    -   This is where your **Next.js application is actually served from**.
    -   It is `.gitignore`d, so you don't need to worry about it during development.
-   **`node_modules` folder**:
    -   Contains **all installed dependencies**.
    -   Created when `npm install` is run, or automatically when the `dev` script runs.
    -   Like the `.next` folder, it is `.gitignore`d and not a primary concern during development.
-   **`public` folder**:
    -   Houses **static assets** like images and SVGs.
-   **`src` folder**:
    -   The **"start of the show"** and where most of the work will be done.
    -   Contains the `app` folder, which represents the **App Router**.

#### **4. Inside the `src/app` Folder**

-   **`favicon.ico`**: Used for the **browser tab icon**.
-   **`global.css`**: For **application-wide styles**.
-   **`layout.tsx`**: Defines **shared UI elements across pages** (e.g., root layout component).
-   **`page.tsx`**:
    -   This file creates **what you see at `localhost:3000`**.
    -   It's the file that was tweaked earlier to display "Hello World".
    -   The **home component defined here slots into `layout.tsx`** as a `children` prop to create the complete UI.
    -   Might include `Geist font` import, either as a Google font or local font, which doesn't affect core learning.

#### **5. Application Execution Flow**

-   When `npm run dev` is executed in the terminal:
    1.  Execution begins from `package.json`.
    2.  It moves to `layout.tsx`, **rendering the root layout component**.
    3.  For the URL `localhost:3000`, it then looks for the component in `page.tsx` within the `app` folder (our home component).
    4.  This home component is rendered **inside the root layout**, completing the UI.

The `app` folder is crucial for routing, but understanding new React concepts is necessary before diving into that.
