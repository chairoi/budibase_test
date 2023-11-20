<script>
  import { getContext } from "svelte"
  const { styleable } = getContext("sdk")
  const component = getContext("component")
  
  const _text;

  const importObject = {
      env: {
          __memory_base: 0,	
      }
  };
  
  WebAssembly.instantiateStreaming(fetch("./side_module.wasm"), importObject).then(result => {
      const value = result.instance.exports.Increment(17);
      _text = value.toString();
  });

  export let text = _text;
</script>

<div use:styleable={$component.styles}>
  This is a new-custom component. 17 + 1 is: {text}.
</div>
