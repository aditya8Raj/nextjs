

<div align='center'>
  <h2>📚 Here are some key notes I took while learning Next.js. Feel free to fork and improve them! 🚀</h2>
  <img align='center' src="https://cdn.brandfetch.io/id2alue-rx/w/394/h/80/theme/light/logo.png?c=1id64Mup7ac03k1S4NH&k=bfHSJFAPEG" alt="Next.js Logo" class="logo"/> <h1>Notes</h1>
</div>

---

#### 1. **File Structure & Special Files** 📂

   - **`loading.tsx`**: Handles custom loading states for pages. Place it within the route folder to show a loading screen while the page is loading.
   - **`error.tsx`**: Manages custom error handling. Use it to display a user-friendly error message if something goes wrong on a page.
   - **`layout.tsx`**: Acts as a layout wrapper for all pages in the specified directory. Any common layout components (e.g., headers, footers) can go here to ensure consistency across pages.
   - **`page.tsx`**: Defines a page in Next.js. Files with this name are treated as routes.
   - **Braces `( )`**: Wrap folder names in parentheses to exclude them from routes, allowing you to organize files without creating new URLs.
   - **Square Brackets `[ ]`**: Use square brackets around folder names for dynamic routing, such as `[id]`, to create pages that rely on dynamic parameters.

---

#### 2. **Routing** 🛤️

   - **Static Routes**: Any `page.tsx` file in a directory automatically becomes a route. For example, `about/page.tsx` will be accessible at `/about`.
   - **Dynamic Routes**: Use square brackets `[param]` in folder names for dynamic routes, such as `[id]/page.tsx` for routes like `/product/123`.
   - **Nested Routes**: Organize folders within folders to create nested routes. For example, `products/[id]/reviews/page.tsx` will result in `/products/:id/reviews`.
   - **Catch-All Routes**: Use `[...slug].tsx` to capture all subpaths under a route. For example, `blog/[...slug]` matches `/blog/2024/01/post-title`.

---

#### 3. **Data Fetching** 📡

   - **`getStaticProps`**: Fetches data at build time. Useful for pages with content that doesn’t change often. Ideal for static generation.
   - **`getServerSideProps`**: Fetches data on each request. Use it for content that changes frequently and requires server-side rendering.
   - **`getInitialProps`**: Legacy data-fetching method that works on both client and server sides but is generally less efficient.
   - **`getStaticPaths`**: Works with `getStaticProps` to define paths that should be pre-rendered for dynamic routes (e.g., for blog posts).

---

#### 4. **API Routes** 🌐

   - Next.js allows creating API routes directly within the `pages/api` folder. Each file in this folder becomes an endpoint, such as `/api/user`.
   - These endpoints can be used for server-side logic, such as handling form submissions, authenticating users, or connecting to databases.
   - API routes are useful for building serverless functions within Next.js apps.

---

#### 5. **Optimizations** ⚡

   - **Automatic Code Splitting**: Next.js automatically splits code at the page level, only loading the necessary code for each page.
   - **Image Optimization**: Use the built-in `next/image` component to automatically optimize images for faster load times.
   - **Static Generation with Incremental Static Regeneration (ISR)**: Allows updating static content without rebuilding the entire site. Use `revalidate` in `getStaticProps` to specify the revalidation interval.
   - **Prefetching**: Next.js prefetches linked pages in the background, making navigation between pages faster.

---

#### 6. **Built-In Components and Utilities** 🛠️

   - **`next/head`**: Import this component to manage the `<head>` section of a page (e.g., for meta tags, titles).
   - **`next/link`**: For client-side navigation. Automatically prefetches linked pages for fast transitions.
   - **`next/router`**: Use this for programmatic navigation within components.
   - **`Image` Component**: Optimizes images by serving them in modern formats, handling lazy loading, and resizing.

---

#### 7. **Middleware** 🔒

   - Next.js Middleware enables running code before a request is completed. This is useful for things like authentication, A/B testing, and bot protection.
   - Middleware is defined in the `middleware.ts` file in the root of your project. It allows conditional redirects and rewrites based on request properties.

---

#### 8. **Environment Variables** 🔑

   - Store sensitive data in `.env.local`, `.env.development`, and `.env.production` files.
   - Use `NEXT_PUBLIC_` prefix for variables you want exposed on the client side (e.g., `NEXT_PUBLIC_API_URL`).
   - Access environment variables via `process.env.VARIABLE_NAME` in your code.

---

#### 9. **Error Handling** ❗

   - **Custom Error Pages**: Customize error pages by adding `_error.js` in the `pages` folder.
   - **Fallback Error Component**: Wrap components in error boundaries to handle and display user-friendly error messages.

---
