<template>
  <div>
    <h1>App</h1>
    <Component1 :employee="employee" />
  </div>
</template>

<script>
import Component1 from "./components/Component1.vue";

export default {
  data() {
    return {
      employee: {},
    };
  },

  components: {
    Component1,
  },
  mounted() {
    this.handleFetch();
  },
  methods: {
    handleFetch() {
      setTimeout(() => {
        this.employee = {
          stringVariable: "String Value",
          numberVariable: 123,
          booleanVariable: true,
        };
      }, 300);

      console.log("Fetch done");
    },
  },
};
</script>
