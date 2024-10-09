<script>
    import { motion } from "svelte-motion"; 
    import { Link } from "svelte-routing"; 
    export let href;
    export let icon;
    export let title;
    export let description;
    export let color;
  </script>
  
  <Link href={href} passHref>
    <motion.div
      whileHover={{ scale: 1.05 }}
      whileTap={{ scale: 0.95 }}
      class={`cursor-pointer rounded-lg p-6 ${color} text-text-light shadow-lg transition-all duration-300 ease-in-out`}
    >
      <svelte:component this={icon} class="h-16 w-16 mb-4" />
      <h2 class="text-2xl font-semibold font-poppins mb-2">{title}</h2>
      <p class="text-sm font-roboto opacity-80">{description}</p>
    </motion.div>
  </Link>
  