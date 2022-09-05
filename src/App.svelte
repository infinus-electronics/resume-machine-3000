<script lang="ts">
  import Resume from "./lib/Resume.svelte";
</script>

<main>
  <Resume />
</main>

<style>
  @media print {
    @page {
      size: A4;
      margin: 0;
    }

    :global(.noprint) {
      display: none;
    }
  }
</style>
