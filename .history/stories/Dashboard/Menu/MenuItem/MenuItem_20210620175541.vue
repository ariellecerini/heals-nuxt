<template>
  <div :class="classes" @click="onClick">{{ label }}</div>
</template>

<script>
import './Menu.css';
import '../../../assets/style.css'

export default {
  name: 'menu-item',

  props: {
    label: {
      type: String,
      required: true,
    },
    active:{
      type: Boolean,
      default: true
    },
    rounded: {
      type: Boolean,
      default: false,
    },
 
  },

  computed: {
    classes() {
      return {
        'nav-item': true,
        'nav-item-active': this.active,
        'nav-item-rounded': this.rounded,
      };
    },
   
  },

  methods: {
    onClick() {
      this.$emit('onClick');
    },
  },
};
</script>
