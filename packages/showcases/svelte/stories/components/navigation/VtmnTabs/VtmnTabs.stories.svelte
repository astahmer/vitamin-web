<script>
  import { action } from '@storybook/addon-actions';
  import { Meta, Story, Template } from '@storybook/addon-svelte-csf';
  import { VtmnTabs, VtmnTabsItem } from '@vtmn/svelte';
  import {
    parameters,
    argTypes,
  } from '@vtmn/showcase-core/csf/components/navigation/tabs.csf';

  const tabItems = () =>
    new Array(4).fill(0).map((_, index) => ({
      tabText: `Tab Name  ${index + 1}`,
    }));
</script>

<Meta
  title="Components / Navigation / VtmnTabs"
  component={VtmnTabs}
  {argTypes}
  {parameters}
/>

<Template let:args>
  <div class="block">
    <VtmnTabs aria-label="Tabs list" {...args}>
      {#each tabItems() as { tabText }, index}
        <VtmnTabsItem on:click={() => action('click')(index.toString())}>
          {tabText}
        </VtmnTabsItem>
      {/each}
    </VtmnTabs>
  </div>
</Template>

<Template let:args>
  <div class="block">
    <VtmnTabs aria-label="Tabs list" {...args}>
      {#each tabItems() as { tabText }, index}
        <VtmnTabsItem
          on:click={() => action('click')(index.toString())}
          icon="heart-line"
        >
          {tabText}
        </VtmnTabsItem>
      {/each}
    </VtmnTabs>
  </div>
</Template>

<Template let:args>
  <div class="block">
    <VtmnTabs aria-label="Tabs list" {...args}>
      {#each tabItems() as { tabText }, index}
        <VtmnTabsItem
          on:click={() => action('click')(index.toString())}
          icon="heart-line"
          badgeValue={6}
        >
          {tabText}
        </VtmnTabsItem>
      {/each}
    </VtmnTabs>
  </div>
</Template>

<Story name="Overview" />
