<template>
  <div class="q-pa-md">
    <q-ajax-bar
      ref="bar"
      position="bottom"
      color="accent"
      size="10px"
      skip-hijack
    />

    <q-btn color="primary" label="Trigger" @click="trigger" />
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  setup () {
    const bar = ref(null)

    function trigger () {
      const barRef = bar.value
      barRef.start()

      setTimeout(() => {
        const barRef = bar.value
        if (barRef) {
          barRef.stop()
        }
      }, Math.random() * 3000 + 1000)
    }

    return {
      bar,
      trigger
    }
  }
}
</script>
