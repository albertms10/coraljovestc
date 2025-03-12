<script>
  export let label = '1r';
  export let color = 'bg-yellow-500';
</script>

<div class="flex flex-col items-center justify-center md:col-start-2">
  <div class="mb-2 h-8 w-20 rounded-t-xl bg-red-600 shadow-md">
    <div class="h-full bg-gradient-to-r from-red-600 via-red-500 to-red-600"></div>
  </div>

  <div
    class="h-24 w-24 bg-gradient-to-t from-{color} via-{color} flex scale-105 transform items-center justify-center rounded-full to-yellow-500 shadow-xl"
  >
    <div
      class="flex h-20 w-20 items-center justify-center rounded-full border-4 border-white bg-yellow-400 text-2xl font-bold text-white"
    >
      {label}
    </div>
  </div>
</div>
