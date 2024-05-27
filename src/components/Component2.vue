<template>
  <div>
    <hr />
    <h1>Component 2</h1>

    <h5>Employee Code</h5>
    <code>
      {{ this.employee }}
    </code>

    <hr />

    <h5>Data Code</h5>
    <code>{{ this.nhrData }}</code>

    <hr />
    <label>stringVariable</label>
    <input type="text" v-model="this.employee.stringVariable" disabled /><br />
    <label>numberVariable</label>
    <input type="text" v-model="this.employee.numberVariable" disabled /><br />
    <label>booleanVariable</label>
    <input type="text" v-model="this.employee.booleanVariable" disabled /><br />

    <label>moreVariable1</label>
    <input type="text" v-model="this.nhrData.moreVariable1" /><br />
    <label>moreVariable2</label>
    <input type="text" v-model="this.nhrData.moreVariable2" /><br />
    <label>moreVariable3</label>
    <input type="text" v-model="this.nhrData.moreVariable3" /><br />
  </div>

  <button @click="handleNext()">next</button>
</template>

<script>
export default {
  props: {
    employee: {
      stringVariable: String,
      numberVariable: Number,
      booleanVariable: Boolean,
    },
  },
  data() {
    return {
      nhrData: {
        stringVariable: this.employee.stringVariable,
        numberVariable: this.employee.numberVariable,
        booleanVariable: this.employee.booleanVariable,
        moreVariable1: "",
        moreVariable2: "",
        moreVariable3: "",
      },
    };
  },
  methods: {
    handleNext() {
      this.nhrData = {
        ...this.nhrData,
        stringVariable: this.employee.stringVariable,
        numberVariable: this.employee.numberVariable,
        booleanVariable: this.employee.booleanVariable,
      };

      console.log("you submitted: ", JSON.parse(JSON.stringify(this.nhrData)));
    },
  },
};
</script>
