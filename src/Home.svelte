<script>
    import { onMount } from 'svelte';
    import { fade, fly } from 'svelte/transition';
    import { elasticOut } from 'svelte/easing';

    let mouseX = 0;
    let mouseY = 0;

    function handleMouseMove(event) {
      mouseX = event.clientX;
      mouseY = event.clientY;
    }

    const menuItems = [
      { href: "/freestyle", icon: "M8 5v14l11-7z", title: "Freestyle", description: "Practice with music randomization"},
      { href: "/upload-choreo", icon: "M9 16h6v-6h4l-7-7-7 7h4zm-4 2h14v2H5z", title: "Upload Choreo", description: "Learn and break down new choreographies"},
      { href: "/progress", icon: "M3 3v18h18V3H3zm16 16H5V5h14v14zM7 10h2v7H7v-7zm4-3h2v10h-2V7zm4 6h2v4h-2v-4z", title: "Progress", description: "Track your improvement over time" }
    ];

    let visible = false;
    onMount(() => {
      visible = true;
    });
</script>

<div class="min-h-screen bg-gradient-to-br from-purple-100 to-blue-100 flex flex-col items-center justify-center" on:mousemove={handleMouseMove}>
  <div 
    class="absolute inset-0 pointer-events-none"
    style="background-image: radial-gradient(circle at {mouseX}px {mouseY}px, rgba(138, 43, 226, 0.2) 0%, rgba(65, 105, 225, 0.1) 40%, transparent 60%); transition: 0.3s ease;"
  ></div>

  {#if visible}
    <h1 in:fly={{ y: -20, duration: 500, easing: elasticOut }} class="text-4xl font-bold text-purple-700 mb-24">Dance Master</h1>
    <div in:fade={{ duration: 500 }} class="w-full max-w-4xl bg-white bg-opacity-90 backdrop-blur-md rounded-lg shadow-xl">
      <div class="grid md:grid-cols-3 gap-4 p-4 justify-center items-center">
        {#each menuItems as item}
          <a href={item.href} class="block no-underline">
            <div class="card">
              <svg class="h-16 w-16 mb-4" viewBox="0 0 24 24" fill="currentColor">
                <path d={item.icon} />
              </svg>
              <h2 class="card-title">{item.title}</h2>
              <p class="card-description">{item.description}</p>
            </div>
          </a>
        {/each}
      </div>
    </div>
  {/if}
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@400;600;700&display=swap');

  :global(body) {
    font-family: 'Poppins', sans-serif;
  }

  .card {
    background: linear-gradient(to right, #e0c3fc, #8ec5fc);
    border-radius: 12px;
    padding: 20px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    transition: transform 0.3s ease;
    text-align: center;
    color: white;
    height: 280px;
    width: 350px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    margin: auto; 
  }

  .card:hover {
    transform: scale(1.05);
  }

  .card-title {
    font-size: 20px;
    font-weight: bold;
  }

  .card-description {
    font-size: 14px;
    margin-top: 8px;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(320px, 1fr));
    justify-items: center;
    gap: 20px; 
  }

  a.no-underline {
    text-decoration: none;
  }

  a.no-underline:hover {
    text-decoration: none;
  }
</style>
