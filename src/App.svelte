<script>
  import Screen from "./Screen.svelte";
  import Button from "./Button.svelte";

  const rows = [
    ["7", "8", "9", "÷"],
    ["4", "5", "6", "x"],
    ["1", "2", "3", "-"],
    ["0", "C", "=", "+"],
  ];

  let result = "0";
</script>

<style>
  main {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    border-radius: 1em;
    padding: 2em;
    width: 350px;
    background: #f5f5f5;
    box-shadow: 0.3em -0.3em 0.6em #fff, -0.3em 0.3em 0.6em #ccc,
      inset 0.3em -0.3em 0.3em #eee, inset -0.3em 0.3em 0.3em #fff;
  }

  .row {
    display: flex;
  }
</style>

<main>
  <Screen {result} />
  <div class="keys">
    {#each rows as row}
      <div class="row">
        {#each row as key}
          <Button {key} bind:result />
        {/each}
      </div>
    {/each}
  </div>
</main>
