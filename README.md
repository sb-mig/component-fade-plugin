# Storyblok Plugin Boilerplate compatible with sb-mig

## Installing the plugin in your storyblok space

To use `xxx` plugin you need to compile and minify the plugin. But first you need to change name of the plugin.
Go to `./src/` and open `Plugin.vue`.
You need to prefix plugin name, with for example name of your department:

```
initWith() {
      return {
        // needs to be equal to your storyblok plugin name
        plugin: "name-of-the-plugin"
      };
    },
```

#### Compiles and minifies for production

Go to root folder and run:

```
npm install
npm run build
```

After running the build you should get a folder `/dist` with an `export.js` file inside.
Create a new plugin in storyblok (it has to have exact name as in first step) and paste the content of `export.js` and publish it.

<!-- TODO: you can also run `sb-mig plugin upload` command - not existing for now -->

The plugin will be available in your storyblok component schemas.

##### More info on storyblok plugin usage/implementation:

https://www.storyblok.com/docs/Guides/Creating-a-field-type-plugin

---

## Using the plugin output in your components

The output of the plugin has following structure:

```
{
  "plugin": "name-of-the-plugin",
  "data": "some data",
  "_uid": "78dba965-6c4e-42cc-9eb8-f04a50c8215e",
  ...
  ...
  ...
}
```
