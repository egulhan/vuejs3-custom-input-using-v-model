<template>
  <ul>
    <li v-for="(option, index) in options" :key="index" @click="changeOption(index)"
        :class="{active: this.modelValue===index}">
      {{ option }}
    </li>
  </ul>
</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      required: true
    },
    options: {
      type: Array,
      required: true
    },
    defaultOption: {
      type: Number,
      required: false,
    },
  },
  emits: ['update:modelValue'],
  name: "MultipleChoiceInput",
  methods: {
    changeOption(option) {
      this.$emit('update:modelValue', option);
    }
  }
}
</script>

<style scoped>
ul {
  list-style-type: none;
  display: flex;
}

ul li {
  display: flex;
  margin: 0 2rem;
  width: 4rem;
  padding: 1rem;
  justify-content: center;
  background: white;
  color: #111;
  border: 1px solid #ccc;
  cursor: pointer;
}

ul li.active {
  background: burlywood;
  border: 1px solid darkgoldenrod;
}
</style>