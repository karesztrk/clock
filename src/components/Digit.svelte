<script>
  import { fly } from "svelte/transition";
  import { sineIn, quadOut } from "svelte/easing";

  export let number;
</script>

<span class="digit-container">
  {#key number}
    <span
      class="digit"
      in:fly={{ y: -50, duration: 600, easing: sineIn }}
      out:fly={{ y: 50, duration: 500, easing: quadOut }}
    >
      {number.toString().padStart(2, "0")}
    </span>
  {/key}
</span>

<style>
  .digit-container {
    position: relative;
    display: inline-block;
    width: 2ch;
  }

  .digit {
    position: absolute;
    left: 0;
    bottom: 0;
  }
</style>
