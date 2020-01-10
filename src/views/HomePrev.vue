<template>
  <div class="home">
    <input type="text" name="text-iuput" v-model="value" />
    <div>
      <p>{{ value }}</p>
      <p>{{ count }}</p>
    </div>
    <div>
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
  computed: {
    count (): number {
      return this.value.length;
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
