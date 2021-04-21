## Quick Setup

#### *Set-up Locally*
In your terminal, navigate to where you would like this blog to live, then run
```bash
#clone the repo
git clone git@github.com:kendallstrautman/brevifolia-nuxt-forestry.git

#navigate to the directory
cd brevifolia-nuxt-forestry

#install dependencies & run dev server with yarn
yarn install
yarn dev

#or with npm
npm install
npm run dev
```
You should then be able to navigate to localhost:3000 in your web browser

## Project Structure

- Site-level configuration is stored in `content/data/config.json`. This data is loaded into `nuxt.config.js` to provide default site metadata.
- Add and access webpack and Nuxt config options via `gridsome.config.js`. Global styles are loaded here. This is also where all the dynamic routes are generated for static export. [This blog](https://regenrek.com/posts/create-a-frontmatter-markdown-powered-blog-with-nuxt-js-in-2019/) and [this template](https://github.com/jake-101/bael-template) were a big help in figuring out how to approach dynamic routing with Nuxt.
- Edit global & reset styles via `assets/styles/...`. All component and page scss files are imported in the `global.scss` file.
- `content/...`contains all your markdown blog posts & data files (e.g. authors list, info page data). These are all editable by Forestry.
- Images live and are uploaded in `static/`
- The `pages/` directory is a very important and required directory for Nuxt. This is where all your pages for the site live and routes for each page are built automatically based on filename.
- Blog posts are built from a template that can be accessed at `pages/blog/_slug.vue`. The markdown is parsed by [frontmatter-markdown-loader](https://www.npmjs.com/package/frontmatter-markdown-loader). This is a [dynamic template](https://nuxtjs.org/guide/routing#dynamic-routes) that gets passed a slug value as a parameter through the route.
- The pages & blog template are comprised of components from the `components/...` directory.

## Using Forestry as your CMS

The `.forestry` directory contains all the settings information and frontmatter configuration to allow Forestry to setup the sidebar structure and editing capacity for this blog. After importing this blog into forestry, you can [access and edit](https://forestry.io/docs/editing/) all of the content via the sidebar.

You can add new blog posts, [data files](https://forestry.io/docs/editing/data-files/), or entire pages and sections to fit your needs. You can also [customize how media](https://forestry.io/docs/media/) is handled, by configurating gitLFS, Cloudinary, S3, or Netlify Large Media.

You can set up a [remote admin](https://forestry.io/docs/editing/remote-admin/) for content editors to log in directly to yoururl.com/admin to make content updates.

### Instant Previews

The [instant preview](https://forestry.io/docs/previews/instant-previews/) method spins up the Nuxt development server for a long-lived preview that can quickly respond to content updates. When using instant previews, your preview command should be the develop command. The development server spawned by this command should be available over port 8080, and bind to 0.0.0.0. The forestry:preview command in this project's package.json will launch a dev server compatible with Forestry's instant previews.
