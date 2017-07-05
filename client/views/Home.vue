<template>

  <div class="page">
    <split-pane>

      <counter slot="right" ></counter>

    </split-pane>

  </div>
</template>

<script>
import Counter from 'components/Counter'
import SplitPane from 'components/SplitPane.vue'

export default {
  components: {
    SplitPane,
    Counter
  }
}
</script>

