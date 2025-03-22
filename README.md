This is a Full Stack Next.js 15 App


## Next.js 15 benefits
- Simplifies development process
- Optimises apps:
React had 2 types of components: functional and class-based.
Now components are categories by where they run:
- Server components: run on the server (more performant, renders web pages on the server before sending it to browser.
When you visit a page, the server processes and renders the component on the server and sends to the browser fully rendered HTML and JS code instantly displaying the page.)
- Client components: run on the client (server sends basic HTML and JS code which browser executes to render components)
- Shared components: run on both server and client
Remix and Astro also supports it but Next.js was first.
- Automatically makes every component a server component unless we specify otherwise if it needs browser specific functionality.
- Page speed insights.
- Client side rendering makes it difficult to search engines to crawl and index pages as they are completely empty.
- Next.js 15 solves this problem by sending pre-redered code improving SEO with ranking.
- Routes: Next.js 15 has a file-based routing system. Each folder name becomes a route path.
  Doesn't require a separate package installation like React Router.
  E.g: app/about will create a route /about
- Fullstack framework: create serverless functions to handle native backend API requests.
This means you can create an API endpoint by simply creating a file called api/route.js and within it create endpoints /api
Without caring of the insfrastracture.
- Takes care of scaling automatically.
- Automatic code splitting. Instead of sending all JS code to the browser, it sends only the code needed for the page, per module.
Speading up page load time.
- Font optimisation: reducing layout shifts and performance by preloading font files.
- Image optimisation: automatically compresses images and serves them in the right format and applies lazy loading.
- CDN support: Next.js 15 has built-in support for CDN.
- Script optimisation: Next.js 15 automatically optimises scripts by removing unused code.
- Supports latest React features such as React compiler, MDX file integration, analytics that run on the server, hot module replacement, and more.
