<script>
  import SectionTitle from "./SectionTitle.svelte";

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  let jobs = resume["jobs"];
</script>

<div class="container">
  <SectionTitle text="Work Experience" uc />

  {#each jobs as job}
    <div class="item">
      <div class="flex">
        <h3>{job.title}</h3>
        <date>{job.duration}</date>
      </div>
      <p>{job.company}, {job.location}</p>
      <ul>
        {#each job.description as description}
          <li>{description}</li>
        {/each}
      </ul>
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
  }

  ul {
    margin: 0.25em 0;
  }

  p,
  li{
    margin: 0;
    width: fit-content;
    // font-weight: 300;
    font-size: 14px;
  }
</style>
