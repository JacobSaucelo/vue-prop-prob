<template>
  <div>
    <hr />
    <h1>Component 1</h1>
    <code>
      {{ this.employee }}
    </code>
    <Component2 :employee="employee" />
  </div>
</template>

<script>
import Component2 from "./Component2.vue";

export default {
  props: {
    employee: {
      stringVariable: String,
      numberVariable: Number,
      booleanVariable: Boolean,
    },
  },
  components: {
    Component2,
  },
};
</script>
