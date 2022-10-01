<script lang="ts">
  import yaml from "js-yaml";
  import data from "/src/me.yaml?raw";
  import SocialMediaIcons from "./SocialMediaIcons.svelte";
  import EducationSection from "./EducationSection.svelte";
  import AwardsSection from "./AwardsSection.svelte";
  import JobsSection from "./JobsSection.svelte";
  import PersonalProjectsSection from "./PersonalProjectsSection.svelte";
  import SkillsSection from "./SkillsSection.svelte";

  const resume = yaml.load(data);
  console.log(resume);
</script>

<div class="resume-container">
  <div class="resume">
    <div class="flex">
      <h1>{resume["personal-information"]["name"]}</h1>
      <a href={resume["personal-information"]["website"]}
        >{resume["personal-information"]["website"]}</a
      >
    </div>
    <div class="flex">
      <p>{resume["personal-information"]["addr-uk"]}</p>
      <SocialMediaIcons />
    </div>
    <div>
      <EducationSection />
    </div>
    <div>
      <AwardsSection />
    </div>
    <div>
      <JobsSection />
    </div>
    <div>
      <PersonalProjectsSection />
    </div>
    <div>
      <SkillsSection />
    </div>
  </div>
</div>

<style lang="scss">
  // @import url("https://fonts.googleapis.com/css2?family=Noto+Sans:wght@100...900");

  

  $margin: 1em;

  .resume-container {
    width: 70%;
    margin: auto;
    // border: solid;
    font-family: "Noto Sans", sans-serif;
    font-size: 16px;
    h1,
    a,
    p {
      margin: 0;
    }
  }

  .resume {
    width: auto;
    padding: 0;
    margin: $margin;
    // display: flex;
    // flex-direction: column;

    h1 {
      font-weight: 500;
      margin-right: 1em;
    }

    p {
      font-weight: 300;
    }

    .flex {
      margin-bottom: 0.25em;
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
      box-sizing: border-box;
    }
  }
</style>
