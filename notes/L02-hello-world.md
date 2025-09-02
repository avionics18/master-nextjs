# L02 - Hello World

This tutorial guides you through setting up your development environment, creating your first Next.js application, running it, and making a simple change.

#### **1. Development Environment Setup**

-   **Node.js**:
    -   Required version: **18.18 or later**.
    -   Download from: nodejs.org
    -   Ensure your existing installation is up to date.
-   **Text Editor**:
    -   Recommended: **VS Code**.
    -   Download from: code.visualstudio.com

#### **2. Creating a New Next.js Project**

-   **Workspace**: Create a folder (e.g., `nextjs-tutorials`) and open it in VS Code.
-   **Command**: Open your terminal (Ctrl+` or Cmd+`) and run:
    ```bash
    npx create-next-app@latest
    ```
-   **Configuration Prompts**:

    1.  **Project Name**: `hello-world`
    2.  **TypeScript**: Yes
    3.  **ESLint**: Yes
    4.  **Tailwind CSS**: Yes
    5.  **Source Directory**: Yes (code in `src` folder)
    6.  **App Router**: Yes (use the new app router)
    7.  **Turbopack**: No (opt out for now, though stable in v15)
    8.  **Import Alias**: Default

-   After a few seconds, a new folder named `hello-world` will be created with your Next.js application.

-   You can also use the following command to create nextjs project in your current folder:

    ```bash
    npx create-next-app@latest ./
    ```

#### **3. Running the Application**

-   **Navigate**: Change into the project directory:
    ```bash
    cd hello-world
    ```
-   **Start Development Server**: Run the command:
    ```bash
    npm run dev
    ```
-   **Access**:
    -   The server starts on `localhost:3000`.
    -   **Control + click** (or Command + click) the link in the terminal to open the application in your browser.
    -   You will see the Next.js welcome page.

#### **4. Making Changes to the Application**

-   **Locate File**:
    -   Go back to VS Code.
    -   Minimize the terminal (Ctrl+` or Cmd+`).
    -   Open the `src` folder, then the `app` folder.
    -   Find and open `page.tsx`.
-   **Edit Content**:
    -   Scroll down within `page.tsx`.
    -   Find the second list item's text, which says "save and see your changes instantly".
    -   **Replace this text with:** `Hello World`
-   **Observe Changes**:
    -   **Save** the file.
    -   The browser will automatically refresh, and you will see "Hello World" displayed on the screen.

#### **Summary**

You have successfully set up your environment, generated a Next.js app using `create-next-app`, run it, and made your first code change, observing instant updates. The next step is to explore the project's folder structure.
