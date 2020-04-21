<template>
  <div class="container">
    Here is front of your plugin
  </div>
</template>

<script>
export default {
  mixins: [window.Storyblok.plugin],
  data: function() {
    return {
      title: "Here is your data"
    };
  },
  methods: {
    // declare methods like in normal vue component here 
    initWith() {
      // init `model` with that values
      return {
        // needs to be equal to your storyblok plugin name
        plugin: "name-of-the-plugin",
        data: "some data"
      };
    },
    pluginCreated() {
      // eslint-disable-next-line
      console.log(
        "View source and customize: https://github.com/storyblok/storyblok-fieldtype"
      );
    },
  },
  watch: {
    model: {
      handler: function(value) {
        this.$emit("changed-model", value);
      },
      deep: true,
    },
  },
};
</script>

<style>
.container {
  display: flex;
  flex-direction: column;
}
</style>
