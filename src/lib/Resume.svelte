<script lang="ts">
  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  console.log(resume);
</script>

<div class="resume-container">
  <div class="resume">
    <h1>{resume["personal-information"]["name"]}</h1>
  </div>
</div>

<style lang="scss">
  @import url("https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100...900&display=swap");

  .resume-container {
    width: 70%;
    margin-left: auto;
    margin-right: auto;
  }

  .resume {
    width: 100%;
    margin-top: 1em;

    h1 {
      font-family: "Noto Sans";
    }
  }
  @media print {
    .resume-container {
      width: 100%;
      margin: 0;
      padding: 0;
    }
    .resume {
      margin: 0.5in;
    }
  }
</style>
