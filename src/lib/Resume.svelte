<script lang='ts'>
  const name = "Ye Heng Hor";
  const phone = "+447825224575";

  import yaml from 'js-yaml';
  import data from '/src/me.yaml?raw';


  const resume = yaml.load(data);


</script>

<div>
  <div class="resume">
    <h1>{resume['personal-information']['name']}</h1>
    <h2 class="noprint">{phone}</h2>
  </div>
</div>

<style lang="scss">
    .resume {
        width: 100%;
        margin-top: 1em;
    }
</style>
