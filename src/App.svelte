<script lang="ts">
  import { TabGroup, Tab, TabContent } from "./tabs";
  const tabs = [
    ["One", "Content of tab one. Foo. Foo. Foo."],
    ["Two", "Content of tab two. Bar. Bar. Bar."],
  ];
</script>

<main>
  <div class="center">
    <img src="favicon.png" alt="favicon" />
    <h1>Svelte App</h1>
    <h2>SpinSpire</h2>
  </div>
  <TabGroup active="foo">
    <div slot="tabs">
      {#each tabs as [title, body], index}
        <Tab key={title}>{title}</Tab>
      {/each}
      <Tab key="foo">Third</Tab>
    </div>
    {#each tabs as [title, body], index}
      <TabContent key={title}>{body}</TabContent>
    {/each}
    <TabContent key="foo">Contents of third tab.</TabContent>
  </TabGroup>
</main>
