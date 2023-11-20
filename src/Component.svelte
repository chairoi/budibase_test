<script>
  import { getContext } from "svelte"

  const { styleable } = getContext("sdk")
  const component = getContext("component")

  function sum() {
      return 1 + 2;
  }
  
  const result = sum();
  export let text = result;

</script>

<div use:styleable={$component.styles}>
  This is a custom component. The text setting is: {text}.
</div>
