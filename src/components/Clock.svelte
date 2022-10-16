<script>
  import { onMount } from "svelte";
  import Digit from "./Digit.svelte";

  let date = new Date();

  $: hour = date.getHours();
  $: minute = date.getMinutes();
  $: second = date.getSeconds();

  onMount(() => {
    setInterval(() => {
      date = new Date();
    }, 1000);
  });
</script>

<h1>
  <Digit number={hour} />
  <Digit number={minute} />
  <Digit number={second} />
</h1>
