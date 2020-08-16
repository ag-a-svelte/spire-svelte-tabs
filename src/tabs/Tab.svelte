<script lang="ts">
  export let key: string | number;
  import { getContext } from "svelte";
  import type { Writable } from "svelte/store";
  const store: Writable<string | number> = getContext("activeTab");
</script>

<style>
  .title {
    /* border: solid lightgray 2px; */
    border-bottom: none;
    display: inline-block;
    padding: 1em;
    color: var(--tab-color-fg, black);
    background-color: var(--tab-color-bg, white);
  }
  .title.active {
    color: var(--tab-color-active-fg, white);
    background-color: var(--tab-color-active-bg, black);
  }
  .title:not(.active):hover {
    cursor: pointer;
    color: var(--tab-color-hover-fg, black);
    background-color: var(--tab-color-hover-bg, lightgray);
  }
</style>

<div
  class="title"
  on:click={() => ($store = key)}
  class:active={$store === key}>
  <slot />
</div>
