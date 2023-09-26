<script lang="ts">

import {fly} from "svelte/transition";
import { onDestroy, onMount } from 'svelte';
import Card from "$lib/component/card.svelte";
import Skill from "$lib/component/skill.svelte"
import Footer from "$lib/component/footer.svelte"
import { page } from '$app/stores';
    import { Navbar, NavBrand, NavLi, NavUl, NavHamburger} from 'flowbite-svelte';
    $: activeUrl = $page.url.pathname;

 
  let ready = false;
  onMount(() => ready = true);


  function scrollIntoView(id: string) {
    const el = document.getElementById(id);
    if (el) {
      el.scrollIntoView({ behavior: "smooth" });
    }
  }
  

  let scrollY = 0;

// Function to update scrollY on scroll
function handleScroll() {
  scrollY = window.scrollY;
}

// Add a scroll event listener when the component is mounted
onMount(() => {
  window.addEventListener('scroll', handleScroll);
});







</script>



<style>
  /* Add your transition styles here */
  .scroll-transition {
    /* Define your transition properties, e.g., opacity and transform */
    opacity: 0;
    transition: opacity 0.2s, transform .5s ease-in-out;
  }

  /* Add styles for when the element should be visible */
  .visible {
    opacity: 1;
    transition: all ease-in-out 2s;
  }



</style>










<Navbar let:hidden let:toggle class="fixed z-50 ">
    <NavBrand href="/">
      <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white" style="font-family: Title;">Dana Sarkawt</span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {hidden} {activeUrl} 
    activeClass="hover:text-dark-100 text-dark-100"
    nonActiveClass="hover:text-dark-100"
    >
      <NavLi href="#" on:click={() => scrollIntoView("section-1")}>Home</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-2")}>Project</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-3")}>Skills</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-4")}>Contact</NavLi>
    </NavUl>
  </Navbar>

<div class="w-full h-16 lg:hidden"></div>
<div class="w-full h-auto flex justify-between items-center px-5 flex-wrap flex-row-reverse md:flex-nowrap flex-row" id="section-1">

  {#if ready}
  <div class="flex w-full visible-on-mount" in:fly = {{y:300, duration: 2000}}>
      <img src="../img/dana.png" alt="sample 1" />
  </div>
  {/if}


    {#if ready}
    <div class="w-full pt-32" in:fly = {{y:-300, duration: 2000}}>
        <p class="text-2xl">Hello I'm</p>
        <h1 class="text-5xl text-dark-100" style="font-family:Title-2;">DANA SARKAWT</h1>
        <h2 class="text-2xl" style="font-family: Title-2;">Front-End Web Developer</h2>
        <br>
        <h4>I am a highly competent Web Developer with a proven
            track record in designing & Development websites . I have strong technical
            skills as well as excellent interpersonal skills, enabling me to interact with
            a wide range of clients. I am eager to be challenged in order to grow and further
            improve my Development skills. My greatest passion is in life is using my technical
            know-how to benefit other people and organisations.</h4>


            <div class="h-auto w-px gap-5 flex flex-row md:flex-col pt-12">
              <a href="https://instagram.com/dana__sarkawt?igshid=YTQwZjQ0NmI0OA=="><i class="fa-brands fa-instagram fa-2xl hover:text-dark-100"></i></a>
              <a href="https://www.facebook.com/dana.biotechnology?mibextid=LQQJ4d"><i class="fa-brands fa-facebook fa-2xl hover:text-dark-100"></i></a>
              <a href="https://github.com/Dana-Sarkawt"><i class="fa-brands fa-github fa-2xl hover:text-dark-100"></i></a>
            </div>



            <div class="h-auto w-px pt-12">
              <!-- svelte-ignore a11y-invalid-attribute -->
              <a href="#" on:click={() => scrollIntoView("section-2")}>
              <i class="gg-arrow-long-down  h-16"></i>
            </a>
            </div>
    </div>
    {/if}
  

    
</div>









<div class="w-full h-auto flex items-center gap-3 mt-28 {scrollY > 100 ? 'scroll-transition visible' : 'scroll-transition'}">
  <div class="h-0.5 w-2/6  bg-dark-100" ></div>
  <h2 class="text-4xl" style="font-family: Title-2;" id="section-2">Project</h2>
</div>



<div class="container mx-auto flex justify-center items-center  mt-50 flex-wrap
{scrollY > 100 ? 'scroll-transition visible' : 'scroll-transition'}" >
   <Card />
</div>







<div class="w-full h-auto flex items-center gap-3 mt-28">
  <div class="h-0.5 w-2/6  bg-dark-100" ></div>
  <h2 class="text-4xl" style="font-family: Title-2;">Skill</h2>
</div>


<div class="container mx-auto flex justify-center items-center  mt-50 flex-wrap" id="section-3">
   <Skill />
</div>



<Footer />