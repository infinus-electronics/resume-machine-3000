<script>
  import SectionTitle from "./SectionTitle.svelte";

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  let prjs = resume["personal-projects"];
</script>

<div class="container">
  <SectionTitle text="Personal Projects" uc />

  {#each prjs as prj}
    <div class="item">
      <div class="flex">
        <h3>{prj.title}</h3>
        <date>{prj.duration}</date>
      </div>
      <ul>
        {#each prj.description as description}
          <li>{description}</li>
        {/each}
      </ul>
    </div>
  {/each}
</div>

<style lang="scss">
  div.container {
    margin-top: 0.75em;
    box-sizing: border-box;
    white-space: normal;
  }

  div.item {
    margin: 0.5em 0;
    break-inside: avoid;
    box-sizing: border-box;
    white-space: normal;

  }

  // span.location{
  //   font-weight: 300;
  // }

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
    margin: 0;
    margin-right: 1em !important;
  }

  ul {
    margin: 0.25em 0;
    // margin-top: 0.1em;
  }

  p,
  li{
    margin: 0;
    width: fit-content;
    // font-weight: 300;
    font-size: 14px;
  }
</style>
