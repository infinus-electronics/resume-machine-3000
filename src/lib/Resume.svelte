<script lang="ts">
  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  console.log(resume)
</script>

<div>
  <div class="resume">
    <h1>{resume["personal-information"]["name"]}</h1>
  </div>
</div>

<style lang="scss">
  .resume {
    width: 100%;
    margin-top: 1em;
  }
</style>
