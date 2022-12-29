## Utility-First Fundamentals

Building complex components from a constrained set of primitive utilities.

### Why not just use inline styles?

A common reaction to this approach is wondering, “isn’t this just inline styles?” and in some ways it is — you’re applying styles directly to elements instead of 
assigning them a class name and then styling that class.

But using utility classes has a few important advantages over inline styles:

- Designing with constraints. Using inline styles, every value is a magic number. With utilities, you’re choosing styles from a predefined design system,
  which makes it much easier to build visually consistent UIs.
 
- Responsive design. You can’t use media queries in inline styles, but you can use Tailwind’s responsive utilities to build fully responsive interfaces easily.

- Hover, focus, and other states. Inline styles can’t target states like hover or focus, but Tailwind’s state variants make it easy to style those states with 
  utility classes.
 
### Maintainability concerns

The biggest maintainability concern when using a utility-first approach is managing commonly repeated utility combinations.

This is easily solved by extracting components and partials, and using editor and language features like multi-cursor editing and simple loops.

If you’d like to hear about others’ experiences with this approach, check out the following resources:

- By The Numbers: A Year and a Half with Atomic CSS by John Polacek
- Building a Scalable CSS Architecture by Sarah Dayan of Algolia
- No, Utility Classes Aren’t the Same As Inline Styles by Sarah Dayan of Algolia
- Diana Mounter on using utility classes at GitHub, a podcast interview



## Next.js 13 

Next.js 13 (stable) lays the foundations to be dynamic without limits:

- app Directory (beta): Easier, faster, less client JS.
- Layouts
- React Server Components
- Streaming
- Turbopack (alpha): Up to 700x faster Rust-based Webpack replacement.
- New next/image: Faster with native browser lazy loading.
- New @next/font (beta): Automatic self-hosted fonts with zero layout shift.
- Improved next/link: Simplified API with automatic <a>.
  
  
  ### New app Directory (Beta)
  
  we're improving the routing and layouts experience in Next.js and aligning with the future of React with the introduction of the app directory. This is a follow-up
  to the Layouts RFC previously published for community feedback.

The app directory is currently in beta and we do not recommend using it in production yet. You can use Next.js 13 with the pages directory with stable features like
  the improved next/image and next/link components, and opt into the app directory at your own pace. The pages directory will continue to be supported for the 
  foreseeable future.
  
 The app directory includes support for:

- Layouts: Easily share UI between routes while preserving state and avoiding expensive re-renders.
- Server Components: Making server-first the default for the most dynamic applications.
- Streaming: Display instant loading states and stream in units of UI as they are rendered.
- Support for Data Fetching: async Server Components and extended fetch API enables component-level fetching.
  
  
  #### Layouts
  
The app/ directory makes it easy to lay out complex interfaces that maintain state across navigations, avoid expensive re-renders, and enable advanced routing 
  patterns. Further, you can nest layouts, and colocate application code with your routes, like components, tests, and styles.
  
  #### Server Components
  
The app/ directory introduces support for React's new Server Components architecture. Server and Client Components use the server and the client each for what 
  they're best at - allowing you to build fast, highly-interactive apps with a single programming model that provides a great developer experience.


  #### Streaming
  
The app/ directory introduces the ability to progressively render and incrementally stream rendered units of the UI to the client.

![image] (https://nextjs.org/_next/image?url=%2Fstatic%2Fblog%2Fnext-13%2Fstreaming.png&w=3840&q=75)
  
  #### Data Fetching
  
React's recent Support for Promises RFC introduces a powerful new way to fetch data and handle promises inside components 
  
  
  
### Introducing Turbopack (Alpha)
  
  Next.js 13 includes Turbopack, the new Rust-based successor to Webpack.

Webpack has been downloaded over 3 billion times. While it's been an integral part of building the Web, we've hit the limits of the maximum performance possible
  with JavaScript-based tooling.

In Next.js 12, we began our transition to native Rust-powered tooling. We started by migrating away from Babel, which resulted in 17x faster transpilation. Then, 
  we replaced Terser, which resulted in 6x faster minification. It's time to go all-in on native for bundling.

Using the Turbopack alpha with Next.js 13 results in:

- 700x faster updates than Webpack
- 10x faster updates than Vite
- 4x faster cold starts than Webpack
  
 ![image] (https://nextjs.org/_next/image?url=%2Fstatic%2Fblog%2Fnext-13%2Fturbopack.png&w=2048&q=75)
  
### Upgrading next/image to Next.js 13 
  
  We've provided a codemod that will automatically update your existing usage of next/image to next/legacy/image. For example, this command would run the codemod 
  on your ./pages directory when run from the root:

                      npx @next/codemod next-image-to-legacy-image ./pages
  
### OG Image Generation
  
  Social cards, also known as open graph images, can massively increase the engagement rate of clicks on your content, with some experiments showing up to 40% 
  better conversions.

Static social cards are time-consuming, error-prone, and hard to maintain. Because of this, social cards are often lacking or even skipped. Until today, dynamic
  social cards that need to be personalized and computed on the fly were difficult and expensive.

We've created a new library @vercel/og that works seamlessly with Next.js to generate dynamic social cards.
  
### Middleware API Updates
  
  In Next.js 12, we introduced Middleware to enable full flexibility with the Next.js router. We've heard your feedback on the initial API design and have added 
  some additions to improve the developer experience and add powerful new functionality.

