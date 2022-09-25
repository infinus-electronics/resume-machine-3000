<script>
  import SectionTitle from "./SectionTitle.svelte";

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  let edus = resume["education"];
</script>

<div class="container">
  <SectionTitle text="Education" uc />
  {#each edus as edu}
    <div class="item">
      <div class="flex">
        <h3>{edu["name"]}</h3>
        <date>{edu["duration"]}</date>
      </div>
      <div>
        <p>{edu["course"]} | {edu["description"]}</p>
      </div>
    </div>
  {/each}
</div>

<style lang="scss">
  div.container {
    margin-top: 0.75em;
  }
  div.item {
    margin: 0.5em 0;
  }
  div.flex {
    display: flex;
    margin: 0;
    margin-top: 0.25em;
    flex-direction: row;
    justify-content: space-between;
    flex-grow: 1000;
    flex-wrap: wrap;
    width: 100%;

    h3,
    date {
      display: flex;
      margin: 0;
    }
  }

  date {
    font-weight: 350;
    
  }

  h3 {
    font-size: medium;
    font-weight: 600;
    margin-right: 1em !important;
  }

  p {
    margin: 0;
    width: fit-content;
    // font-weight: 300;
    font-size: 14px;
  }
</style>
