<script>
  import { getContext } from "svelte"
  const { styleable } = getContext("sdk")
  const component = getContext("component")

  function sum() {
    return 3 + 2;
  }

  const result = sum();

  export let text = result;
</script>

<div use:styleable={$component.styles}>
  This is a new-custom component. 3 + 2 is: {text}.
</div>
