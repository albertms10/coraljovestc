<script>
  export let item;
</script>

<div class="transform rounded-lg bg-white p-6 shadow-lg transition duration-300 hover:scale-105">
  <img src={item.image} alt={item.title} class="mx-auto mb-4 h-16 w-16 rounded-full" />
  <h3 class="text-center text-xl font-semibold text-indigo-600">{item.title}</h3>
  <span class="block text-center text-sm text-gray-500">{item.year}</span>
  <p class="mt-2 text-center text-gray-600">{item.description}</p>
</div>
