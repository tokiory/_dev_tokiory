<script>
  const {src} = $props();

  let diagram = $state()

  $effect(() => {
    fetch(src).then(res => {
      return res.text()
    }).then(res => {
      diagram = res
    })
  })
</script>

<div class="diagram">
  <!-- eslint-disable-next-line svelte/no-at-html-tags -->
  {@html diagram}
</div>

<style scoped>
  .diagram {
    @apply w-full h-fit mt-4 mb-10;
  }
  :global(.diagram svg) {
    @apply w-full h-full;
    font-family: 'Virgil';
  }
</style>
