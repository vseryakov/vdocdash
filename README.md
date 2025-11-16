# Docdash


JSDoc 4 documentation template theme forked and modified from clenemt/docdash.

## Example

Visit the [documentation](https://vseryakov.github.io/backendjs/docs/web/index.html).

## Install

```bash
$ npm install vdocdash
```

## Usage
Clone repository to your designated `jsdoc` template directory, then:

```bash
$ jsdoc entry-file.js -t path/to/vdocdash
```

## Usage (npm)
In your projects `package.json` file add a new script:

```json
"script": {
  "generate-docs": "node_modules/.bin/jsdoc -c jsdoc.json"
}
```

In your `jsdoc.json` file, add a template option.

```json
"opts": {
  "template": "node_modules/vdocdash"
}
```

## Sample `jsdoc.json`

```json
{
    "tags": {
        "allowUnknownTags": false
    },
    "source": {
        "include": "../js",
        "includePattern": "\\.js$",
        "excludePattern": "(node_modules/|docs)"
    },
    "plugins": [
        "plugins/markdown"
    ],
    "opts": {
        "template": "node_modules/vdocdash",
        "encoding": "utf8",
        "destination": "docs/",
        "recurse": true,
        "verbose": true
    },
    "templates": {
        "cleverLinks": false,
        "monospaceLinks": false
    }
}
```

## Options
Docdash supports the following options:

```json5
{
    "docdash": {
        "static": [false|true],         // Display the static members inside the navbar
        "sort": [false|true],           // Sort the methods in the navbar
        "sectionOrder": [               // Order the main section in the navbar (default order shown here)
             "Tutorials",
             "Modules",
             "Classes",
             "Externals",
             "Events",
             "Namespaces",
             "Mixins",
             "Interfaces",
             "Global"
        ],
        tutorialsOrder: [               // Order of the tutorials in the navbar
              "file3,
              "file1", ...
        ],
        "disqus": "",                   // Shortname for your disqus (subdomain during site creation)
        "openGraph": {                  // Open Graph options (mostly for Facebook and other sites to easily extract meta information)
            "title": "",                // Title of the website
            "type": "website",          // Type of the website
            "image": "",                // Main image/logo
            "site_name": "",            // Site name
            "url": ""                   // Main canonical URL for the main page of the site
        },
        "meta": {                       // Meta information options (mostly for search engines that have not indexed your site yet)
            "title": "",                // Also will be used as postfix to actualy page title, prefixed with object/document name
            "description": "",          // Description of overal contents of your website
            "keyword": ""               // Keywords for search engines
        },
        "search": [false|true],         // Display seach box above navigation which allows to search/filter navigation items
        "commonNav": [false|true],      // Group all html code for <nav> in a nav.inc.html fetched on each page (instead of include it in each html page, save {navSize}×{nb html pages} which can be huge on big project)
        "collapse": [false|true|top],   // Collapse navigation by default except current object's navigation of the current page, top for top level collapse
        "wrap": [false|true],           // Wrap long navigation names instead of trimming them
        "typedefs": [false|true],       // Include typedefs in menu
        "navLevel": [integer],          // depth level to show in navbar, starting at 0 (false or -1 to disable)
        "private": [false|true],        // set to false to not show @private in navbar
        "removeQuotes": [none|all|trim],// Remove single and double quotes, trim removes only surrounding ones
        "scripts": [],                  // Array of external (or relative local copied using templates.default.staticFiles.include) js or css files to inject into HTML,
        "ShortenTypes": [false|true], // If set to true this will resolve the display name of all types as the shortened name only (after the final period).
        "menu": {                       // Adding additional menu items after Home
            "Project Website": {        // Menu item name
                "href":"https://myproject.com", //the rest of HTML properties to add to manu item
                "target":"_blank",
                "class":"menu-item",
                "id":"website_link"
            },
            "Forum": {
                "href":"https://myproject.com.forum",
                "target":"_blank",
                "class":"menu-item",
                "id":"forum_link"
            }
        },
        "scopeInOutputPath": [false|true], // Add scope from package file (if present) to the output path, true by default.
        "nameInOutputPath": [false|true], // Add name from package file to the output path, true by default.
        "versionInOutputPath": [false|true] // Add package version to the output path, true by default. 
    }
}
```

Place them anywhere inside your `jsdoc.json` file.

## License
Licensed under the Apache License, version 2.0. (see [Apache-2.0](LICENSE.md)).
