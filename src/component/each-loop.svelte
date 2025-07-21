<script>
let items = [
  { hex: "#f00", name: 'white' },
  { hex: "#0f0", name: 'black' },
  { hex: "#00f", name: 'pink' }
];


</script>
<div>

   
        <ul class="flex flex-col gap-6 items-center">
        {#each items as item}
        <li class="text-xl font-semibold rounded-lg px-4 py-2 shadow-sm bg-gray-50 hover:bg-gray-100 transition-colors duration-200" style="color: {item.hex}">{item.name}</li>
        {/each}
        </ul>
</div>
  



