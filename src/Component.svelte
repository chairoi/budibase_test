<script>
  import { getContext } from "svelte"
  export let text = "text"
  const { styleable } = getContext("sdk")
  const component = getContext("component")
  function sum() {
      return 1 + 2;
  }
  
  const result = sum();
  export let text = result;
</script>

<div use:styleable={$component.styles}>
  This is a new-custom component. The text setting is: {text}.
</div>
