<script lang="ts">
  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";

  const resume = yaml.load(data);
  console.log(resume);
</script>

<div class="resume-container">
  <div class="resume">
    
      <div class="header">
        <h1>{resume["personal-information"]["name"]}</h1>
        <a href="{resume["personal-information"]["website"]}">{resume["personal-information"]["website"]}</a>
      </div>
      <div class="contacts">
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
    h1, a, p {
      margin: 0;
    }
      
  }

  .resume {
    width: auto;
    padding: 0;
    margin: 0;
    display: flex;
 

    .header{
      margin: $margin;
      padding: 0;
      width: auto;
      display: flex;
      flex-direction: row;
      flex-grow: 1000;
      flex-wrap: wrap;
      justify-content: space-between;
      align-items: center;      
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
