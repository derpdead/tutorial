/* * Copyright © Bold Brand Commerce Sp. z o.o. All rights reserved. * See
LICENSE for license details. */
<template>
  <button
    :class="classes"
    :style="styles"
    @click="onClick"
    @mouseenter="onMouseEnter"
    @mouseleave="onMouseLeave"
    v-text="title"
  />
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
      isVisible: false,
      isHovered: false,
      title: '123',
    }
  },
  computed: {
    classes() {
      return ['my-button', { 'my-button--hovered': this.isHovered }]
    },
    styles() {
      return {
        border: 'solid red',
      }
    },
    myValue() {
      return this.title || this.mySuperProp
    },
  },
  watch: {
    mySuperProp() {
      this.title = 'Youve changed my super prop'
    },
  },
  methods: {
    onClick() {
      this.title = 'Cos'
    },
    onMouseEnter() {
      this.isHovered = true
    },
    onMouseLeave() {
      this.isHovered = false
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

  &--hovered {
    background-color: #f5f5f5;
    color: #3b8070;
  }
}
</style>
