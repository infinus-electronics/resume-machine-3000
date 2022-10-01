<script lang="ts">
  import Resume from "./lib/Resume.svelte";
</script>

<svelte:head>
  <!-- elements go here -->
  <link rel="preconnect" href="https://fonts.gstatic.com/" crossorigin />
  <link
    href="https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100;200;300;400;500;600;700;800;900"
    rel="stylesheet"
  />
</svelte:head>

<main>
  <Resume />
</main>

<style>
  @media print {
    @page {
      size: A4;
      /* margin: 0; */
      margin: 1cm;
    }

    :global(.noprint) {
      display: none;
    }
  }
  /* :global(*) {
    box-sizing: border-box;
  } */
</style>
