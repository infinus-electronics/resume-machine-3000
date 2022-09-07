<script lang='ts'>
  const name = "Ye Heng Hor";
  const phone = "+447825224575";

  import yaml from 'js-yaml';
  import me from "./src/me.yaml?raw";


  const data = yaml.load(fs.readFileSync('/src/me.yaml', 'utf8'));
  console.log(data);

</script>

<div>
  <div class="resume">
    <h1>{name}</h1>
    <h2 class="noprint">{phone}</h2>
  </div>
</div>

<style lang="scss">
    .resume {
        width: 100%;
        margin-top: 1em;
    }
</style>
