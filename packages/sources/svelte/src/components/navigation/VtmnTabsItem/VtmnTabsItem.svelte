<script>
  import VtmnBadge from '../../indicators/VtmnBadge/VtmnBadge.svelte';
  import VtmnIcon from '../../../guidelines/iconography/VtmnIcon/VtmnIcon.svelte';
  export let href = '#';
  export let badgeValue = undefined;
  export let icon = undefined;
</script>

<li role="tab">
  <a
    {...$$restProps}
    {href}
    on:click|preventDefault
    on:mouseover
    on:mouseenter
    on:mouseout
    on:focus
    on:blur
    on:keydown
  >
    {#if icon}
      <VtmnIcon value={icon} aria-hidden="true" />
    {/if}
    <slot />
    {#if badgeValue}
      <VtmnBadge value={badgeValue} />
    {/if}
  </a>
</li>
