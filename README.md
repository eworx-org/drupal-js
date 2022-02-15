# Drupal decoupled backend with JS frontend

Best practices, basic steps, lists of tools and tips to help you integrate a Drupal 8.x+ backend with a Javascript frontend.

_Notice: Some examples bellow refer only to React development and are not JS agnostic._

---

<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**

- [JS](#js)
  - [Popular JS frontend frameworks](#popular-js-frontend-frameworks)
  - [Compare JS frameworks](#compare-js-frameworks)
  - [Parameters to consider when selecting a frontend framework](#parameters-to-consider-when-selecting-a-frontend-framework)
  - [Tools for JS development](#tools-for-js-development)
  - [JS terminology](#js-terminology)
  - [Learn JS frameworks basics](#learn-js-frameworks-basics)
  - [JS app structure](#js-app-structure)
  - [Styling a JS app](#styling-a-js-app)
- [Drupal](#drupal)
- [About Drupal decoupled solutions](#about-drupal-decoupled-solutions)
  - [Drupal slack channels](#drupal-slack-channels)
  - [Drupal modules](#drupal-modules)
    - [JSON API (core)](#json-api-core)
    - [GraphQL](#graphql)
    - [Other](#other)
  - [Drupal Distributions](#drupal-distributions)
  - [Drupal starter-kits with JS frameworks](#drupal-starter-kits-with-js-frameworks)
  - [npm packages for Drupal](#npm-packages-for-drupal)
  - [Drupal common issues with decoupled](#drupal-common-issues-with-decoupled)
- [Framework: React](#framework-react)
  - [Learn React](#learn-react)
  - [Drupal + React](#drupal--react)
  - [Articles](#articles)
- [Framework: NextJS](#framework-nextjs)
  - [Why choose NextJS](#why-choose-nextjs)
  - [Learn NextJS](#learn-nextjs)
  - [Drupal + NextJS](#drupal--nextjs)
  - [NextJS popular tools](#nextjs-popular-tools)
  - [Articles](#articles-1)
- [Final tips](#final-tips)
- [LICENSE](#license)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

## JS

### Popular JS frontend frameworks

- [React](https://reactjs.org)
  - [Gatsby](https://www.gatsbyjs.com)
  - [Next](https://nextjs.org)
  - [Remix](https://remix.run)
  - [Blitz](https://blitzjs.com)
  - [Inferno](https://www.infernojs.org)
- [Angular](https://angular.io)
- [Vue](https://vuejs.org)
  - [Nuxt](https://nuxtjs.org) 
- [WebComponents](https://www.webcomponents.org) (not a pure JS solution)

### Compare JS frameworks

Online services to use when comparing frameworks (trends, popularity, usage, downloads, benchmarks etc).

- **Questionnaires**
  - https://2020.stateofjs.com/en-US/technologies/front-end-frameworks/
  - https://www.jetbrains.com/lp/devecosystem-2021/javascript/
  - https://insights.stackoverflow.com/survey/2021#section-most-popular-technologies-web-frameworks
- **Trends**
  - https://trends.google.com/trends/explore?cat=733&date=today%205-y&q=React,Vue,Angular,Next
  - https://insights.stackoverflow.com/trends?tags=reactjs%2Cvue.js%2Csvelte%2Cvuejs3%2Cangular
  - https://www.npmtrends.com/next-vs-react-vs-svelte-vs-vue
- **Popularity**
  - https://www.githubcompare.com/vercel/next.js+facebook/react+angular/angular.js+vuejs/vue
  - https://star-history.com/#facebook/react&vuejs/vue&angular/angular&vercel/next.js&Timeline
  - https://www.hntrends.com/2020/dec-year-unlike-any-other-tech-tools-didnt-change-much.html?compare=AngularJS&compare=Ember&compare=React&compare=Vue
  - https://frontpagemetrics.com/r/reactjs#compare=vuejs+angular2+sveltejs+nextjs
- **Usage**
  - https://trends.builtwith.com/javascript/javascript-library
  - https://www.wappalyzer.com/technologies/javascript-libraries/react/
  - https://www.datanyze.com/market-share/frameworks-and-libraries--66/react-market-share
  - https://www.similartech.com/technologies/react-js
- **Analysis & dependencies**
  - https://npmgraph.js.org
  - https://bundlephobia.com
  - https://packagephobia.com
- **Benchmarks**
  - https://krausest.github.io/js-framework-benchmark

### Parameters to consider when selecting a frontend framework

List is of random order.

- Performance
- Stability
- Development experience
- Documentation and support
- Vendors behind
- Complexity and learning curve
- CRUD requirements
- Serving multiple platforms and consumers
- Existing in-house knowledge

### Tools for JS development

Notice: Before using these tools try to use the built-in, bundled tools you get from each framework.

- [VSCode](https://code.visualstudio.com)
- [nvm](https://github.com/nvm-sh/nvm), [npm](https://www.npmjs.com) (no need to use `yarn` over `npm` in 2022)
- [Typescript](https://www.typescriptlang.org)
- [Storybook](https://storybook.js.org)
- [Babel](https://babeljs.io)
- [PostCSS](https://postcss.org)
- [husky](https://github.com/typicode/husky)
- [JSX](https://reactjs.org/docs/introducing-jsx.html)
- [JSON](https://www.json.org/json-en.html), [JSON API](https://jsonapi.org)
- Bundlers: [Webpack](https://webpack.js.org), [esbuild](https://esbuild.github.io)
- Code linting etc: [EditorConfig](http://editorconfig.org), [ESLint](https://eslint.org), [Prettier](https://prettier.io), [JSLint](https://www.jslint.com)
- Code generators: [Hygen](https://www.hygen.io), [nx](https://nx.dev), [ReexJs CLI](https://codingcodax.github.io/reexjs-cli), [generact](https://github.com/diegohaz/generact)
- Testing: [Jest](https://jestjs.io), [Cypress](https://cypress.io), [testing-library](https://testing-library.com)
- Data fetch: [axios](https://axios-http.com), [react-query](https://react-query.tanstack.com), [SWR](https://swr.vercel.app), [node-fetch](https://www.npmjs.com/package/node-fetch)
- Data parser: [qs](https://www.npmjs.com/package/qs)
- Routing: [React Router](https://reactrouter.com)
- Quality:  [danger](https://www.npmjs.com/package/danger)
- Logging: [pino](https://getpino.io)
- Documentation: [jsdoc](https://www.npmjs.com/package/jsdoc)
- Performance: [next-boost](https://github.com/next-boost/next-boost), [react-lazy-load-image-component](https://www.npmjs.com/package/react-lazy-load-image-component), [node-cache](https://www.npmjs.com/package/node-cache), [webpack-bundle-analyzer](https://www.npmjs.com/package/webpack-bundle-analyzer)
- Security: (npm built-in: `npm-audit, npm-outdated, npm-doctor` [npm-check](https://www.npmjs.com/package/npm-check), [snyk](https://snyk.io), [npm-check-updates](https://www.npmjs.com/package/npm-check-updates)
- State management: [redux](https://redux.js.org), [zustand](https://github.com/pmndrs/zustand), [recoil](https://recoiljs.org), [jotai](https://jotai.org)
- Translations, i18n: [lingui](https://github.com/lingui/js-lingui), [polyglot](https://www.npmjs.com/package/node-polyglot)
- Mocks, faker: [sinon](https://sinonjs.org), [faker](https://fakerjs.dev), [JSON Server fake API](https://www.npmjs.com/package/json-server)

### JS terminology

In order to start with JS you sould be familiar with the basic terms bellow. Notice that some of them may refer to a specific JS framework.

- CORS
- Cache
- Code splitting
- Components
- Composition
- DOM
- Data fetch
- HMR (Hot Module Reload)
- HOC (Higher Order Components)
- Hook events
- Injection
- Invalidation
- Isomorphic
- PWA
- Props
- Routing
- SEO
- [SSR](https://vuejs.org/guide/scaling-up/ssr.html), [SSG](https://blog.logrocket.com/ssg-vs-ssr-in-next-js), [ISR](https://blog.logrocket.com/incremental-static-regeneration-with-next-js), [DSG](https://www.gatsbyjs.com/docs/how-to/rendering-options/using-deferred-static-generation), [CSR](https://frontend-digest.com/client-side-rendering-vs-server-side-rendering-vs-static-site-generation-2a0702cbb08d)
- SWA
- SideEffect
- State
- Web Vitals (LCP, FID, CLS)
- a11y
- es6/es7 etc
- hydration
- i18n
- library
- module
- node daemon
- package
- virtual DOM

### Learn JS frameworks basics

- https://www.patterns.dev

### JS app structure

- [Move files around until it feels right](https://react-file-structure.surge.sh/)
- Group by file type
- Avoid too much nesting
- Keep with the trends (e.g. use common names like "`src, public, pages, __tests__, docs`" etc

```
ToDo: Add some example structure here..
```

Sources: [1](https://gist.github.com/literat/4f7c8a4a9b9d113886df77fa34228623), [2](https://hackernoon.com/react-project-structure-best-practices-kh20323x), [3](https://blog.usejournal.com/folder-structure-in-react-apps-c2ae8974d21f), [4](https://hackernoon.com/structuring-projects-and-naming-components-in-react-1261b6e18d76), [5](https://reactjs.org/docs/faq-structure.html)

### Styling a JS app

- Prefer "CSS in files" approach except if there are specific requirements.
- For inline styles use utility CSS libraries like [tailwindcss](https://tailwindcss.com) and [Windi CSS](https://windicss.org)
- For UI building isolation and sandboxing use [Storybook](https://storybook.js.org), [React Styleguidist](https://react-styleguidist.js.org), [React Cosmos](https://reactcosmos.org), [React Preview](https://reactpreview.com) etc.

---

## Drupal

## About Drupal decoupled solutions

- https://dri.es/headless-cms-rest-vs-jsonapi-vs-graphql
- https://dri.es/how-to-decouple-drupal-in-2019
- https://dri.es/drupal-looking-to-adopt-react
- https://dri.es/advancing-drupal-web-services
- https://www.drupal.org/industries/decoupled
- https://www.lullabot.com/articles/should-you-decouple
- https://www.softescu.com/en/blog/fully-decoupled-or-progressively-decoupled
- https://medium.com/analytics-vidhya/decoupled-drupal-as-a-solution-bd0ec25f39cf
- https://opensenselabs.com/blog/articles/different-options-decoupling-drupal
- https://www.lullabot.com/articles/decoupled-hard-problems-routing

### Drupal slack channels

- [#decoupled](https://app.slack.com/client/T06GX3JTS/C1AKSFBEW)
- [#headless](https://app.slack.com/client/T06GX3JTS/C8ZK4VDMW)
- [#graphql](https://app.slack.com/client/T06GX3JTS/C6LMJ0ZAT)
- [#contenta](https://app.slack.com/client/T06GX3JTS/C5A70F7D1)
- [#react](https://app.slack.com/client/T06GX3JTS/CUW94TUBX)
- [#nextjs](https://app.slack.com/client/T06GX3JTS/C01E36BMU72)
- [#gatsby](https://app.slack.com/client/T06GX3JTS/CDQC1MDU6)
- [#druxt (NuxtJS)](https://app.slack.com/client/T06GX3JTS/C01ALFZ8459)
- [#vue](https://app.slack.com/client/T06GX3JTS/C9SR65F6K)
- [#custom-elements](https://app.slack.com/client/T06GX3JTS/C01G23CS86Q)


### Drupal modules

Notice: Modules in emfasis are the most used across the Drupal universe.

#### JSON API (core)

[jsonapi.org](https://jsonapi.org), [JSON API: Drupal core module documentation](https://www.drupal.org/docs/core-modules-and-themes/core-modules/jsonapi-module)

- **Basic**
  - **decoupled_kit**
  - **decoupled_menus**
  - **drupal_jsonapi_params**
  - entity_view_mode_normalize
  - fieldable_path
  - jsonapi_aliases
  - jsonapi_comment
  - jsonapi_embed
  - **jsonapi_extras**
  - **jsonapi_menu_items**
  - **jsonapi_views**
  - jsonrpc
  - pager_serializer
  - rest_absolute_urls
  - rest_menu_detail
  - rest_menu_items
  - rest_normalizer
  - https://github.com/pmelab/contextual_aliases
- **Subrequests, nesting**
  - jsonapi_include
  - rest_entity_recursive
  - rest_export_nested
  - **subrequests**
- **Routing**
  - **decoupled_router**
  - entity_router
- **Collections**
  - jsonapi_cross_bundles
  - decoupled_pages
  - jsonapi_resources
  - page_manager
  - jsonapi_user_resources
- **Search**
  - **jsonapi_search_api**
- **Preview**
  - **dpl**
- **Performance**
  - jsonapi_earlyrendering_workaround
  - **jsonapi_boost**
  - **warmer**
- **Images**
  - **jsonapi_image_styles**
  - **consumer_image_styles**
  - image_derivatives_selection
  - image_derivatives_base64_representation
- **Rate limits**
  - rate_limiter
  - **rate_limits**
- **API Documentation**
  - schemata
  - openapi_ui_swagger
  - **openapi**
  - openapi_ui
  - **openapi_jsonapi**
  - openapi_rest
  - **openapi_ui_redoc**
  - swagger_ui_formatter
  - jsonapi_schema
  - social_json_api
- **Authentication**
  - api_proxy
  - **simple_oauth**
  - **consumers**
  - **cors_ui**
  - rest_api_authentication
  - key_auth
  - api_key_manager
  - access_filter
  - jsonapi_access
  - rest_password
- **Administration**
  - **restui**
  - jsonapi_explorer
  - restuiextention
  - api_proxy
- **Forms**
  - **webform_rest**
  - webform_jsonschema
  - rjsf
- **Logging**
  - **http_client_log**
  - request_logger
  - rest_log
  - restfullogger

#### GraphQL

(Advice: Do not prefer GraphQL over JSON API except if there are special requirements)

- **graphql**
- graphql_entity_by_object
- graphql_entity_definitions
- graphql_extras
- graphql_formatters
- graphql_menu
- graphql_metatag
- graphql_node_preview
- graphql_redirect
- graphql_redirect_entity
- graphql_search_api
- graphql_views
- graphql_webform
- preview_graphql

#### Other

- pdb
- **relaxed**
- jdrupal
- js_component

### Drupal Distributions

- https://www.contentacms.org
- https://www.drupal.org/project/tide
- https://github.com/systemseed/falcon
- https://www.drupal.org/project/ezcontent (using REST, not a decoupled example)

### Drupal starter-kits with JS frameworks

- https://next-drupal.org (Next)
- https://druxtjs.org (Nuxt)
- https://stack.lupus.digital (Nuxt)

### npm packages for Drupal

- [d8-jsonapi-querystring](https://www.npmjs.com/package/d8-jsonapi-querystring)
- [d8-subrequests](https://www.npmjs.com/package/d8-subrequests)
- [drupal-jsonapi-extractor](https://www.npmjs.com/package/drupal-jsonapi-extractor)
- [drupal-jsonapi-params](https://www.npmjs.com/package/drupal-jsonapi-params)
- [drupal-sdk](https://www.npmjs.com/package/drupal-sdk)
- [jsonapi-parse](https://www.npmjs.com/package/jsonapi-parse)
- [react-drupal-json-api](https://www.npmjs.com/package/react-drupal-json-api)

### Drupal common issues with decoupled

- Displaying embedded entities on CKEditor (eg Media) inside JS components
- Multilingual
- Subrequets and relationships in data
- Customizing of responses like filtering, quering and altering
- Routing and path aliases
- Non entities data (e.g. metatags, redirects, path aliases, image styles)
- Workflows (Content Moderation) and revisions
- Node preview
- Authentication
- Invalidate partial cache
- Forms

---

## Framework: React

- https://reactjs.org
- https://github.com/enaqx/awesome-react
- https://github.com/brillout/awesome-react-components

### Learn React

- [Thinking in React - reactjs.org](https://reactjs.org/docs/thinking-in-react.html)
- [Complete guide React + Drupal - drupalize.me](https://drupalize.me/series/drupal-8-and-reactjs)
- [React in patterns](https://krasimir.gitbooks.io/react-in-patterns)
- [30 Days of React - GitHub](https://github.com/Asabeneh/30-Days-Of-React)
- [Functional Components - codeburst.io](https://codeburst.io/react-js-understanding-functional-class-components-e65d723e909)
- React Components: https://reactjs.org/docs/react-component.html, https://github.com/brillout/awesome-react-components
- React Hooks: https://reactjs.org/docs/hooks-intro.html, https://usehooks.com
- React Props: https://akd3257.medium.com/what-are-props-in-react-2f822330e3a7

### Drupal + React

- Guide: https://reactfordrupal.com
- Starter: https://github.com/systemseed/drupal_reactjs_boilerplate
- Example: https://github.com/DrupalizeMe/react-and-drupal-examples

### Articles

- https://www.smashingmagazine.com/2021/11/maintain-large-nextjs-application

---

## Framework: NextJS

- https://nextjs.org
- https://github.com/unicodeveloper/awesome-nextjs

### Why choose NextJS

- Better SEO. Supports SSR, SSG, ISR.
- Built in solutions for common requirements (routing, head/metatags, images, links, font optimization, data fetching, injected scripts, i18n, AMP)
- Built in tools (Typescript, Sass, ESLint, Webpack, env variables, preview mode, polyfills)
- Better Development Experience (DX) (zero config, built in tools, fast refresh)
- Based on React (can use all the React goodies)

### Learn NextJS

- https://nextjs.org/learn/basics/create-nextjs-app
- https://nextjstips.com

### Drupal + NextJS

- https://next-drupal.org
- [About Drupal, Gatsby and Next](https://gist.github.com/colorfield/22b1a451d90b2a159c7d3d679197812f)
- [Next.js and Headless CMS - GitHub issue](https://github.com/vercel/next.js/discussions/33087)

### NextJS popular tools

- https://swr.vercel.app (React Hooks for Data Fetching)
- https://next-auth.js.org (Authentication for Next.js)
- https://github.com/atilafassina/next-g11n (Translate and localize your Next.js app smoothly)
- https://github.com/next-boost/next-boost (Adds a cache layer to your SSR applications)

### Articles

- https://www.smashingmagazine.com/2021/11/maintain-large-nextjs-application
- https://stackabuse.com/guide-to-getting-started-with-nextjs-create-a-nextjs-app

---

## Final tips

- Make it really "decoupled" (except if other requirements)
- Keep it simple. Use the basic tools and extend when needed.
- Less JS packages and less Drupal modules is prefferable.
- Work only with NodeJS lts versions.
- Think in Components
- Create enough Components
- Modify the state directly
- Add keys on the lists
- Declare types, validate functions
- Always test your Components and app
- Dockerize your JS app
- Drupal: Prefer Drupal modules from core (e.g. JSON API instead of GraphQL)
- Drupal: Do not override the default Drupal field machine names on JSON
- Start with the official starter kits (e.g [create-react-app](https://create-react-app.dev/))

---

## LICENSE

[MIT](LICENSE) - Copyright (c) 2022 [EWORX S.A.](https://github.com/eworx-org)
