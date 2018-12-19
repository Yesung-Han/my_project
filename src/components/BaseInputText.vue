<template>
  <input
    type="text"
    class="input"
    v-bind:value="value"
    v-on="listeners"
  />
</template>

<script>
/* eslint-disable */

export default {
    props: {
        value:{
            type: String,
            default: '',
        },
    },
    computed: {
        listeners: function() {
            return {
                ...this.$listeners,
                input: event => this.$emit("input", event.target.value)
            };
        },
    }
};

</script>

