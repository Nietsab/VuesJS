<template>
  <div class="input">
    <InputBlock
      v-bind:value="value"
      v-bind:placeholder="placeholder"
      v-on:input="$emit('input', $event.target.value)">
    </InputBlock>
  </div>
</template>

<script>
export default {
  name: 'InputBlock',
  props: {
    value : String,
    placeholder: String
  }
}
</script>