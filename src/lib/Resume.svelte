<script lang="ts">
  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  console.log(resume);
</script>

<div class="resume-container">
  <div class="resume">
    
      <div class="resume-header">
        <h1>{resume["personal-information"]["name"]}</h1>
        <a href="{resume["personal-information"]["website"]}">{resume["personal-information"]["website"]}</a>
      </div>
    
  </div>
</div>

<style lang="scss">
  @import url("https://fonts.googleapis.com/css?family=Noto+Sans:wght@100...900&display=swap");

  $margin: 1em;

  .resume-container {
    width: 70%;
    margin: auto;
    border: solid;
    font-family: "Noto Sans";
  }

  .resume {
    width: auto;
    padding: 0;
    margin: 0;
    display: flex;
   

    .resume-header{
      margin: $margin;
      padding: 0;
      width: 100%;
      display: flex;
      flex-direction: row;
      justify-content: space-between;
      align-items: center;
      
      h1, a, p {
        margin: 0;
      }
      
    }

  }
  @media print {
    .resume-container {
      width: 100%;
      margin: 0;
      padding: 0;
    }
    .resume {
      margin: 0.25in;
    }
  }
</style>
