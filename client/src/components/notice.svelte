<script lang="ts">
  export let emoji = '';
</script>

<div
  class="bg-chetwode-200 dark:bg-chetwode-800 font-body px-4 md:px-8 py-6 md:my-8 rounded-lg text-black dark:text-white shadow-xl bg-gradient-to-br from-transparent to-chetwode-300 dark:to-chetwode-900"
>
  <div class="flex flex-row items-center content-center">
    <div class="flex-initial px-4 text-center text-lg">{emoji}</div>
    <div class="flex-auto"><slot /></div>
  </div>
</div>
