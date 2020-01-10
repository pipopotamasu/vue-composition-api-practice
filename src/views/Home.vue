<template>
  <div class="home">
    <input type="text" name="text-iuput" v-model="value" />
    <div>
      <span>{{ value }}</span>
      <button @click="onSubmit">submit</button>
      <button @click="onClear">clear</button>
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'home',
  data () {
    return {
      value: ''
    }
  },
  methods: {
    onSubmit() {
      if (!this.value) return;
      alert(this.value)
    },
    onClear () {
      this.value = ''
    }
  }
})
</script>
