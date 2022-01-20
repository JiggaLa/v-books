# VersaBooks

VersaBooks is an open, editable library catalog, building towards a web page for every book ever published.

`Responsive` VersaBooks website is fully responsive and compatible with all major browsers across devices.

`API:` Open Library Book API, check out [documentation](https://openlibrary.org/dev/docs/api/books)

`Goal:` Build an open, curated and an editable library containing book information and metadata. A request can be made to VersaBooks to add a book to the catalogue, but not available for the current alpha build. Website must be accessible across all platforms and browsers (IE11 or older are not supported).

`Problems and possible improvements:`

- API doesn't allow post requests. User book request feature can't be built until the request endpoint is ready.
- For future development, API is not secured with an access key. For testing purposes and in the alpha stage, this is ok, but not advisable for production. API needs to be secured and keys saved to '.env' file and added to 'gitignore'.
- API is called for every page load, caching might be needed and deployed for a snappier user experience in the future. This may also require the use of vue state management - Vuex (store).
- Loading state element popping. This is probably due to the fetch hook and Axios syncing. But styling needs more tweaking to improve state feedback for the user.

### `Dev stack:`

- Nuxt.js (Vue.js 2)
- Tailwind CSS
- SASS
- Axios

## Build Setup

```bash
# install dependencies
$ npm install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm run start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [documentation](https://nuxtjs.org).

## Special Directories

You can create the following extra directories, some of which have special behaviors. Only `pages` is required; you can delete them if you don't want to use their functionality.

### `assets`

The assets directory contains your uncompiled assets such as Stylus or Sass files, images, or fonts.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/assets).

### `components`

The components directory contains your Vue.js components. Components make up the different parts of your page and can be reused and imported into your pages, layouts and even other components.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/components).

### `layouts`

Layouts are a great help when you want to change the look and feel of your Nuxt app, whether you want to include a sidebar or have distinct layouts for mobile and desktop.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/layouts).

### `pages`

This directory contains your application views and routes. Nuxt will read all the `*.vue` files inside this directory and setup Vue Router automatically.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/get-started/routing).

### `plugins`

The plugins directory contains JavaScript plugins that you want to run before instantiating the root Vue.js Application. This is the place to add Vue plugins and to inject functions or constants. Every time you need to use `Vue.use()`, you should create a file in `plugins/` and add its path to plugins in `nuxt.config.js`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/plugins).

### `static`

This directory contains your static files. Each file inside this directory is mapped to `/`.

Example: `/static/robots.txt` is mapped as `/robots.txt`.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/static).

### `store`

This directory contains your Vuex store files. Creating a file in this directory automatically activates Vuex.

More information about the usage of this directory in [the documentation](https://nuxtjs.org/docs/2.x/directory-structure/store).
