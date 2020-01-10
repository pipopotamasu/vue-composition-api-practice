<template>
  <div class="home">
    <input type="text" name="text-iuput" v-model="state.val" />
    <div>
      <p>{{ state.val }}</p>
      <p>{{ count }}</p>
    </div>
    <div>
      <button @click="onSubmit">submit</button>
      <button @click="onClear">clear</button>
    </div>
  </div>
</template>

<script lang="ts">
import { createComponent, computed, reactive } from '@vue/composition-api'

function createInputValueComposition () {
  const state = reactive<{ val: string }>({
    val: ''
  });

  const count = computed((): number => state.val.length);

  function onSubmit () {
    if (!state.val) return;
    alert(state.val)
  }

  function onClear () {
    state.val = ''
  }

  return {
    state,
    count,
    onSubmit,
    onClear
  }
}

export default createComponent({
  setup () {
    return { ...createInputValueComposition() }
  }
})
</script>
