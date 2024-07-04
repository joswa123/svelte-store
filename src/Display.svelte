<script>
 import {count} from "./Store"
 import {onDestroy} from 'svelte'

   let counter
 const unsubscribe=  count.subscribe((value)=>{
    counter=value
   })
   onDestroy(unsubscribe)
</script>
<main>
    <h2>Currrent count is {counter}</h2>
</main>
