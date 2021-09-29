# Nuxt.js Preview Links DatoCMS Plugin

> Forked from the Next.js Preview Links DatoCMS Plugin [https://github.com/wbobeirne/datocms-plugin-nextjs-preview]

Plugin that adds quick links to preview & view your DatoCMS on a Nuxt.js site.
Assumes you have enabled the Nuxt preview mode: https://nuxtjs.org/docs/features/live-preview/

## Configuration

After installing the plugin, you'll need to configure the plugin settings like so:

![Configuration screenshot](./docs/configuration.png)

Then on each model you'd like to be able to preview, you'll need to add a JSON field, and under the "Presentation"
tab, you'll want to select "Nuxt.js Preview Links" as the "Field editor", and fill out the entity path for the
given entity on your site. You can sub in any field on the entity using the $field_name, e.g. /blog/$slug or
/product/$id.

![JSON field screenshot](./docs/field.png)

## Preview Links

Once you've configured the plugin and added the field to a model, you will be able to see it as a sidebar widget.

![Plugin screenshot](./docs/preview.png)

A blog post with a slug of `my-first-post` using the configuration from the example above would link to:

* `https://my-nuxt-site.com/blog/my-first-post?preview=true` for the "Preview" link
* `https://my-nuxt-site.com/blog/my-first-post` for the "View published" link


## Development

If you want to develop on this extension, the quickest way is to run `yarn addToProject`. That will walk you through
setting it up. If you have trouble going through that setup, you can manually install it by going to Settings > Plugins,
clicking the add button, and clicking "create a private one" in the lower right. Give it:

* a name of your choosing
* an entry point URL of `http://localhost:5000`
* `Sidebar widget` as type of plugin
* `JSON` as field types
* Copy the JSON from `package.json`'s `parameters` object into the parameter defintions

After that, you can just run `yarn start`, and it should be loading in the sidebar after you configure it with a model.

This project was largely based on the [Gatsby plugin](https://github.com/gatsby-inc/datocms-plugin-gatsby-cloud),
and the [DatoCMS Todo List example plugin](https://github.com/datocms/plugins/tree/master/todo-list).
