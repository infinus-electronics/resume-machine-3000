<script>
  import SectionTitle from "./SectionTitle.svelte";

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";
  //   import { each } from "svelte/internal";

  const resume = yaml.load(data);
  let awards = resume["awards"];
  awards.forEach((e, i, r) => {
    if (!e.name) {
      let nameText = e;
      r[i] = { name: nameText };
    }
  });
  console.log(awards);
</script>

<div class="container">
  <SectionTitle text="Awards" uc />

  {#each awards as award}
    <div class="item">
      <h3>{award.name}</h3>
      {#if award.description}
        <p>{award.description}</p>
      {/if}
    </div>
  {/each}
</div>

<style lang="scss">
  div.container {
    margin-top: 0.75em;
  }
  div.item {
    margin: 0.5em 0;
    page-break-inside: avoid;
  }
   
  // div{
  //   margin-top: 0.25em;
  // }

  h3 {
    font-size: medium;
    font-weight: 600;
    margin: 0;
  }

  p {
    margin: 0;
    width: fit-content;
    // font-weight: 300;
    font-size: 14px;
  }
</style>
