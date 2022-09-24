<script>
  import Fa from "svelte-fa/src/fa.svelte";
  import { faGithub, faLinkedin } from "@fortawesome/free-brands-svg-icons";
  import {faEnvelope} from "@fortawesome/free-solid-svg-icons"

  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";
  
  const resume = yaml.load(data);

</script>

<div>
    <a href="mailto:{resume["personal-information"]["email"]}" target="_blank" rel="noopener noreferrer"><Fa icon={faEnvelope} fw></Fa></a> 
    <a href="{resume["personal-information"]["github"]}" target="_blank" rel="noopener noreferrer"><Fa icon={faGithub} fw></Fa></a>
    <a href="{resume["personal-information"]["linkedin"]}" target="_blank" rel="noopener noreferrer"><Fa icon={faLinkedin} fw></Fa></a>  
</div>

<style lang="scss">
    a:link, a:visited {
        color:black;
        margin-left: 2px;
        padding: 1px;
    }
</style>