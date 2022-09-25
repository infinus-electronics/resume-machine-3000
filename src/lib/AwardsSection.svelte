<script>
  import SectionTitle from "./SectionTitle.svelte";

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";
  import { each } from "svelte/internal";

  const resume = yaml.load(data);
  let awards = resume["awards"];
  awards.forEach((e,i,r) => {
    if (!e.name){
        let nameText = e;
        r[i] = {name: nameText}
    }
  });
  console.log(awards);
</script>


