# L04 - Basic Overview of `RSC` (React Server Components)

This tutorial introduces **React Server Components (RSC)**, a fundamental concept essential for understanding how routing works in Next.js.

#### **1. React Server Components (RSC) Overview**

-   RSC is a **new architecture** introduced by the React team and quickly adopted by Next.js.
-   It introduces a new approach by **dividing React components into two distinct types**: server components and client components.
-   Understanding these types is crucial for grasping routing concepts.

#### **2. Component Types: Server Components vs. Client Components**

-   **Server Components:**

    -   **Default Behavior**: By default, Next.js **treats all components as server components**.
    -   **Capabilities**:
        -   Can perform **server-side tasks**.
        -   Can **read files**.
        -   Can **fetch data directly from a database**.
    -   **Limitations**:
        -   **Cannot use React hooks**.
        -   **Cannot handle user interactions**.
    -   **Purpose**: They are designed for data fetching and backend operations without client-side overhead.

-   **Client Components:**
    -   **How to Create**: You must add the **`"use client"` directive** at the top of your component file to declare it as a client component.
    -   **Capabilities**:
        -   **Can use Hooks**.
        -   **Can handle user interactions**.
    -   **Limitations**:
        -   **Cannot perform server-side tasks** like reading files.
    -   **Analogy**: Think of client components as the **traditional React components** you are familiar with from previous versions of React.
    -   **Purpose**: They are designed for interactive UI elements that require client-side state and effects.

#### **3. Practical Application**

-   As you delve into routing, you will see **practical examples of both component types**.
-   You will work with server components that **wait for operations to complete before rendering content**.
-   You will use client components to **take advantage of hooks from the routing module**.

#### **4. Future Learning**

-   This is a basic understanding, and **React Server Components will be covered in much more detail later in the course**.
-   This foundation helps to better understand routing in Next.js.
