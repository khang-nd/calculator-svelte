<script>
  export let result;
</script>

<style>
  .screen {
    height: 100px;
    width: 100%;
    overflow: auto;
    font-size: 200%;
    background: #444;
    color: #fff;
    display: flex;
    align-items: center;
    justify-content: flex-end;
    padding: 0.3em;
    margin-bottom: 0.5em;
    border-radius: 0.2em;
    box-sizing: border-box;
    box-shadow: inset 0.2em -0.2em 0.2em #777, inset -0.2em 0.2em 0.2em #000;
  }
</style>

<div class="screen">{result}</div>
