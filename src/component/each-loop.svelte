<script>
let items = [
  { hex: "#f00", name: 'white' },
  { hex: "#0f0", name: 'black' },
  { hex: "#00f", name: 'pink' }
];


</script>
<div>

   
        <ul class="flex flex-col gap-4 items-center">
        {#each items as item}
        <li class="text-lg font-medium rounded-full" style="color: {item.hex}">{item.name}</li>
        {/each}
        </ul>
</div>
  



