<template>
  <div>
    <b-form-input v-model="search" placeholder="Enter your name"></b-form-input>
    <div class="mt-2">Value: {{ search }}</div>
  </div>
</template>
<script>
import { ref } from 'vue'
export default {
    setup() {
        const search = ref("")
        return { search }
    },
}
</script>