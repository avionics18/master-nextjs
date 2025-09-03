## L07 - Dynamic Routes

Next.js introduces **dynamic route segments** to handle URLs that contain variable parts, which is crucial for applications with numerous items like products or blog posts. This method is more practical than creating a separate folder for each item, especially when dealing with hundreds or thousands of entries.

### The Problem with Predefined Nested Routes

Previously, nested routes were created by making subfolders (e.g., `/blog/first`, `/blog/second`). While effective for a few predefined paths, this approach becomes unmanageable for scenarios like product details where you might have `hundreds of products`. Creating a folder for `product ID 1`, `product ID 2`, and so on for every single product would be a **maintenance nightmare**.

### Scenario: Product Listing and Details Page

Consider building a feature where:

-   ` /products` displays a list of all products.
-   ` /products/1` displays details for the first product.
-   ` /products/2` displays details for the second product.
-   And so forth for any product ID.

### Implementing Dynamic Routes

1.  **Create a base folder**: First, create a `products` folder inside your `app` directory.
2.  **Create the product list page**: Inside the `products` folder, create a `page.tsx` file. This file will export a React component that displays a general **product list** (e.g., "Product 1", "Product 2", "Product 3").

    -   Visiting `localhost:3000/products` will show this list.

3.  **Implement the Dynamic Segment**:
    -   **Delete any individual product ID folders** you might have created (e.g., a folder named `1`).
    -   Inside the `products` directory, create a **special folder using square brackets**: `[productID]`. The name `productID` (or whatever you choose) is a descriptive placeholder for the dynamic segment.
    -   Inside this `[productID]` folder, create a `page.tsx` file.
    -   This `page.tsx` file will contain a React component that represents the **product details page**.
    -   Now, when you visit `localhost:3000/products/1`, `localhost:3000/products/2`, `localhost:3000/products/100`, or even `localhost:3000/products/iPhone`, they will **all be handled by this single `page.tsx` file** within the `[productID]` folder. Next.js treats a folder name in square brackets as a **dynamic segment**, making routes flexible.

### Accessing Dynamic Route Parameters

To make the product details page useful, you need to know which specific product ID was in the URL.

-   Every page in the App Router receives **route parameters** through the `params` prop.
-   You can **destructure `params`** from the component's props.
-   The `params` object contains the dynamic segments as **key-value pairs**. The key will be the name you gave to your dynamic folder (e.g., `productID`).
-   For server components, you can use `async`/`await` to access these parameters directly.

    ```typescript
    // app/products/[productID]/page.tsx
    export default async function ProductDetails({
        params,
    }: {
        params: { productID: string };
    }) {
        const productID = params.productID; // Access the dynamic segment
        return <h1>Details about product {productID}</h1>;
    }
    ```

-   Now, visiting `localhost:3000/products/1` will display "Details about product 1", and `localhost:3000/products/iPhone` will show "Details about product iPhone".
-   The `productID` can be a **number or a string**.

### Summary of Dynamic Routes

-   **Folder with square brackets** (e.g., `[productID]`) within a route directory defines a dynamic segment.
-   Any URL matching this pattern (e.g., `/products/1`, `/products/foo`) will map to the `page.tsx` file inside the dynamic folder.
-   Inside the component, the dynamic value (e.g., `1`, `foo`) is retrieved from the **`params` prop** using the folder name as the key (`params.productID`).
-   This pattern is incredibly useful for building **list-detail views** in applications, whether for e-commerce, blogs, or any system requiring dynamic content based on a URL identifier.
