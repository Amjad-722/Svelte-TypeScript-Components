<script>
let items = [
  { hex: "#f00", name: 'white' },
  { hex: "#0f0", name: 'black' },
  { hex: "#00f", name: 'pink' }
];


</script>
<div class="p-6 max-w-md mx-auto">
        <h2 class="text-2xl font-bold mb-4 text-center">Color List</h2>
        <ul class="flex flex-col gap-6 w-full">
        {#each items as item}
        <li class="text-xl font-semibold rounded-lg px-4 py-2 shadow-sm bg-gray-50 hover:bg-gray-100 transition-colors duration-200 border border-gray-200 flex items-center justify-between w-full">
          <span>{item.name}</span>
          <span class="w-6 h-6 rounded-full" style="background-color: {item.hex}"></span>
        </li>
        {/each}
        </ul>
</div>
  



