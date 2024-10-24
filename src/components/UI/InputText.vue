// DatePicker.vue
<template>
  <input type="text" :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"  :type="typeInput" :placeholder="placeholder"/>

</template>

<script>
export default {
  props: {
    modelValue: {
      type: String,
      required: true
    },
    typeInput: {
      type: String,
      default: 'date'
    },
    placeholder: {
      type: String,
      default: 'Что то тут....'
    },
    width: {
      type: String,
      default: '100%'
    },
    height: {
      type: String,
      default: '10px'
    },
    color: {
      type: String,
      default: 'gray'
    }
  },
  data() {
    return {
      dateValue: this.value
    }
  }
}
</script>

<style scoped>
input {
  width: v-bind(width);
  font-size: 11px;
  box-shadow: 0px 0px 2px v-bind(color);
  border-radius: 20px;
  padding: v-bind(height);
  outline: none;
  border: none;
  transition: 0.1s;
  font-family: "Courier New", Courier, monospace;
  font-weight: bold;
}
input:hover{
  box-shadow: 0px 2px 2px v-bind(color);
}

input:focus{
  box-shadow: 0px 2px 2px v-bind(color);
  color: black;
}
</style>