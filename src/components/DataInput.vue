<template>
  <InputWrapper
      :id="id"
      :label="label"
      :notEmpty="notEmpty"
      :focused="focused">

    <input
        v-model.trim="text"
        class="data-input"
        type="text"
        @focus="focus()"
        @blur="blur()">
  </InputWrapper>
</template>

<script>
import InputWrapper from "@/components/InputWrapper";

export default {
  name: "DataInput",
  components: {InputWrapper},

  props: {
    label: String,
    id: String
  },

  data() {
    return {
      focused: false,
      text: ''
    }
  },

  computed: {
    notEmpty() {
      return this.text !== '' || this.focused
    },

  },

  methods: {

    focus() {
      return this.focused = true
    },

    blur() {
      return this.focused = false
    }
  }
}
</script>

<style lang="scss">

</style>