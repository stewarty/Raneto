/*
Title: Customizing the Template
*/

Templating in Raneto is powered by [Mustache](http://mustache.github.io). All of the template views can
be found in the `views` folder. Feel free to customize the template as you wish. The template structure
is as follows:

* `layout.html`: The parent template. You'll probably want to customize this first
* `home.html`: The homepage template. Shown if you don't have an [index.md](%base_url%/usage/custom-homepage)
* `page.html`: The template used for single pages
* `search.html`: The template used for search results
* `error.html`: Shown when Raneto encounters an error or can't find a page

Remember you will need to restart the app after changing the template.

## Template Variables

Below are a list of template variables available to use in their respective templates:

**home.html**

* `config`: Holds an array of values from `config.js`
* `pages`: Structured list of categories and pages (used for navigation)
* `body_class`: Class for the `<body>` tag

**page.html**

* `config`: Holds an array of values from `config.js`
* `pages`: Structured list of categories and pages (used for navigation)
* `body_class`: Class for the `<body>` tag
* `meta`: Holds an array of values taken from the page meta comment block (e.g. `meta.title`)
* `content`: The HTML content of the page
* `last_modified`: The formatted date of the time the file was last modified

**search.html**

* `config`: Holds an array of values from `config.js`
* `pages`: Structured list of categories and pages (used for navigation)
* `body_class`: Class for the `<body>` tag
* `search`: The current search query
* `searchResults`: An array search results

## Array Structure

The `pages` array has a structure similar to the following:

* `slug`: The categoy slug
* `title`: The category title
* `is_index`: True for the top level files (ie not in a category)
* `class`: CSS class
* `files[]`: Array of pages in this category
	* `slug`: The page slug
	* `title`: The page title
	* `active`: True if the current page is "active"

The `searchResults` array contains items which include:

* `slug`: The page slug
* `title`: The page title
* `body`: The page content
* `excerpt`: The page excerpt
