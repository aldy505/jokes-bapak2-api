<script lang="ts">
  import { goto } from '$app/navigation';
  import { _ } from 'svelte-i18n';

  let open = false;
  let duration = 0.4;
  let burgerColor = 'rgb(18.4, 18.4, 18.4)';
  let menuColor = 'rgb(180, 180, 180)';
</script>

<nav class="flex flex-row py-6 font-body items-center">
  <div on:click={() => goto('/')} class="hover:cursor-pointer flex-5 font-bold text-2xl">Jokesbapak2</div>
  <div on:click={() => goto('/why')} class="navigation-item">{$_('navigation.why')}</div>
  <div on:click={() => goto('/guide')} class="navigation-item">{$_('navigation.guide')}</div>
  <div on:click={() => goto('/api')} class="navigation-item">{$_('navigation.api')}</div>
  <div
    class="flex-1 md:hidden transition-all duration-400 ease-in-out"
    class:open
    on:click={() => (open = !open)}
    style="color: {open ? menuColor : burgerColor};"
  >
    <svg width="32" height="32" class="dark:text-white text-black">
      <line
        id="top"
        x1="0"
        y1="9"
        x2="32"
        y2="9"
        style="transition: transform {duration}s ease-in-out, opacity {duration}s ease-in-out;"
      />
      <line
        id="mid"
        x1="0"
        y1="18.5"
        x2="32"
        y2="18.5"
        style="transition: transform {duration}s ease-in-out, opacity {duration}s ease-in-out;"
      />
      <line
        id="bot"
        x1="0"
        y1="28"
        x2="32"
        y2="28"
        style="transition: transform {duration}s ease-in-out, opacity {duration}s ease-in-out;"
      />
    </svg>
  </div>
</nav>

{#if open}
  <menu
    class="top-of-the-world dark:bg-gray-900 dark:text-white bg-lavender-200 bg-gradient-to-br to-lavender-400 dark:to-lavender-900 text-black w-full h-full overscroll-none"
  >
    <div class="container -pr-10">
      <div class="flex flex-col items-center content-center text-center pt-20">
        <div
          on:click={() => {
            open = false;
            return goto('/');
          }}
          class="hover:cursor-pointer flex-1 font-bold text-3xl pt-6 pb-10"
        >
          Jokesbapak2
        </div>
        <div
          on:click={() => {
            open = false;
            return goto('/why');
          }}
          class="flex-1 py-3 text-4xl"
        >
          {$_('navigation.why')}
        </div>
        <div
          on:click={() => {
            open = false;
            return goto('/guide');
          }}
          class="flex-1 py-3 text-4xl"
        >
          {$_('navigation.guide')}
        </div>
        <div
          on:click={() => {
            open = false;
            return goto('/api');
          }}
          class="flex-1 py-3 text-4xl"
        >
          {$_('navigation.api')}
        </div>
      </div>
    </div>
  </menu>
{/if}

<style>
  .navigation-item {
    @apply hidden 'md:block' text-center 'md:flex-1' duration-300 transition ease-in-out py-2 'md:py-0' 'md:opacity-50' 'hover:cursor-pointer' 'hover:scale-110' 'hover:opacity-100';
  }
  .top-of-the-world {
    @apply fixed z-20 -top-4 left-0 right-0 bottom-0;
  }
  svg line {
    stroke: currentColor;
    stroke-width: 3;
  }
  .open {
    @apply z-30 fixed right-12;
  }
  /* rotate the top line */
  .open #top {
    transform: translate(10px, 0px) rotate(45deg);
  }
  /* hide the middle */
  .open #mid {
    opacity: 0;
  }
  /* rotate the bottom line */
  .open #bot {
    transform: translate(-15px, 8px) rotate(-45deg);
  }
</style>
