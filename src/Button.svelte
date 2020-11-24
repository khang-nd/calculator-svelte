<script>
  export let key;
  export let result;
  const error = "Invalid input!";

  function replace(value) {
    return value.replace("x", "*").replace("÷", "/");
  }

  function handleClick() {
    switch (key) {
      case "=":
        try {
          result = eval(replace(result));
        } catch (e) {
          result = error;
        }
        break;
      case "C":
        result = "0";
        break;
      default:
        result = result === error || result === "0" ? key : result + key;
    }
  }
</script>

<style>
  button {
    width: 100%;
    margin: 0.3em;
    border: 0;
    padding: 1em 0.5em;
    box-shadow: 0.1em -0.1em 0.2em #fff, -0.1em 0.1em 0.2em #ccc;
    background: unset;
    outline: none;
    font-size: 110%;
    cursor: pointer;
    border-radius: 0.2em;
    transition: box-shadow 0.4s;
  }

  button:hover {
    box-shadow: 0.1em -0.1em 0.2em transparent, -0.1em 0.1em 0.2em transparent,
      inset 0.1em -0.1em 0.3em 0.1em #fff, inset -0.1em 0.1em 0.4em #ccc;
  }
</style>

<button on:click={handleClick}>{key}</button>
