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
    <div class="flex">
        <h3>{edu["name"]}</h3>
        <date>{edu["duration"]}</date>
    </div>
    <div>
        <p>{edu["course"]} | {edu["description"]}</p>
    </div>
  {/each}
</div>

<style lang="scss">
  div.container {
    margin-top: 0.75em;
  }
  div.flex{
    display: flex;
    margin: 0;
    margin-top: 0.25em;
    flex-direction: row;
    justify-content: space-between;
    flex-grow: 1000;
    flex-wrap: wrap;
    width: 100%;

    h3, date {
        display: flex;
        margin: 0;
    }
  }
  h3 {
 
    font-size: medium;    
    font-weight: 600;

  }
  date {
    font-weight: 350;
  }

  p{    
    margin: 0;
    width: fit-content;
    font-size: 14px;
  }
 
</style>
