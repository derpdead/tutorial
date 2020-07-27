/* * Copyright © Bold Brand Commerce Sp. z o.o. All rights reserved. * See
LICENSE for license details. */
<template>
  <div>
    <button class="my-button" @click="onClick" v-text="'Click me'" />
    <span v-text="title" />
    <span v-text="myValue" />
  </div>
</template>

<script>
export default {
  name: 'Button',
  props: {
    mySuperProp: {
      type: String,
      default: 'Cos',
    },
  },
  data() {
    return {
      title: '123',
    }
  },
  computed: {
    myValue() {
      return this.title || this.mySuperProp
    },
  },
  methods: {
    onClick() {
      this.title = 'Cos'
    },
  },
}
</script>

<style scoped lang="scss">
.my-button {
  padding: 8px;
  color: #000;
  background-color: #3b8070;
  border: none;

  &:hover {
    background-color: #f5f5f5;
    color: #3b8070;
  }
}
</style>
