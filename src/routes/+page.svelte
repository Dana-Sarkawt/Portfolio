<script lang="ts">
 import { DarkMode } from 'flowbite-svelte';
 import { Button, GradientButton } from 'flowbite-svelte';
let btnClass = 'text-gray-500 dark:text-gray-400 hover:bg-gray-100 dark:hover:bg-gray-700 rounded-lg text-xl p-2';

import Course from "$lib/component/courses.svelte";
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
 

a{
  cursor: url(../img/pointer.png), pointer;
}

i{
  cursor: url(../img/pointer.png), pointer;
}

</style>










<Navbar let:hidden let:toggle class="fixed z-50 dark:bg-dark-300">
    <NavBrand href="/">
      <span class="self-center whitespace-nowrap text-xl font-semibold dark:text-white" style="font-family: Title;">Dana Sarkawt</span>
    </NavBrand>
    <NavHamburger on:click={toggle} />
    <NavUl {hidden} {activeUrl} 
    activeClass="hover:text-dark-100 text-dark-100"
    nonActiveClass="hover:text-dark-100"
    ulClass="flex flex-col md:flex-row gap-5 h-auto w-full text-center bg-light-100 dark:bg-dark-200 md:bg-white dark:md:bg-dark-300 "
    
    >
      <NavLi href="#" on:click={() => scrollIntoView("section-1")} style="cursor: url(../img/pointer.png), pointer;">Home</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-2")} style="cursor: url(../img/pointer.png), pointer;">Project</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-3")} style="cursor: url(../img/pointer.png), pointer;">Courses</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-4")} style="cursor: url(../img/pointer.png), pointer;">Skills</NavLi>
      <NavLi href="#" on:click={() => scrollIntoView("section-5")} style="cursor: url(../img/pointer.png), pointer;">Contact</NavLi>
      <DarkMode {btnClass} class="flex justify-center" style="cursor: url(../img/pointer.png), pointer;"/>
    </NavUl>

  </Navbar>

<div class="w-full h-16 lg:hidden"></div>
<div class="w-full h-auto flex justify-between items-center px-5 flex-wrap flex-row-reverse md:flex-nowrap flex-row" id="section-1">

  {#if ready}
  <div class="flex w-full visible-on-mount" data-aos="fade-up" data-aos-duration="2000">
      <img src="../img/dana.png" alt="sample 1" />
  </div>
  {/if}


    {#if ready}
    <div class="w-full pt-32" data-aos="fade-down" data-aos-duration="2000">
        <p class="text-2xl dark:text-white 2xl:text-2xl">Hello I'm</p>
        <h1 class="text-5xl text-dark-100 2xl:text-7xl" style="font-family:Title-2;">DANA SARKAWT</h1>
        <h2 class="text-2xl dark:text-white 2xl:text-4xl" style="font-family: Title-2;">Front-End Web Developer</h2>
        <br>
        <h4 class="dark:text-white 2xl:text-2xl">I am a highly competent Web Developer with a proven
            track record in designing & Development websites . I have strong technical
            skills as well as excellent interpersonal skills, enabling me to interact with
            a wide range of clients. I am eager to be challenged in order to grow and further
            improve my Development skills. My greatest passion is in life is using my technical
            know-how to benefit other people and organisations.</h4>
            <div class="w-full h-auto flex justify-center md:justify-start gap-3">
              <a href="https://drive.google.com/file/d/1nTu_pDaZfotIZx_jh3nRmNohCe-putW9/view?usp=sharing">
            <GradientButton shadow color="purple" class="mt-5" style="cursor: url(../img/pointer.png), pointer;">CV - Online Preview</GradientButton></a>
            <a href="https://drive.google.com/uc?export=download&id=1nTu_pDaZfotIZx_jh3nRmNohCe-putW9">
            <GradientButton shadow color="green" class="mt-5" style="cursor: url(../img/pointer.png), pointer;" download>CV - Download</GradientButton></a>
          </div>


            <div class="h-auto w-full md:w-px gap-5 flex flex-row justify-center md:justify-start md:flex-col pt-12">
              <a href="https://instagram.com/dana__sarkawt?igshid=YTQwZjQ0NmI0OA=="><i class="fa-brands fa-instagram fa-2xl dark:text-white hover:text-dark-100 dark:hover:text-dark-100 "></i></a>
              <a href="https://www.facebook.com/dana.biotechnology?mibextid=LQQJ4d"><i class="fa-brands fa-facebook fa-2xl dark:text-white hover:text-dark-100 dark:hover:text-dark-100"></i></a>
              <a href="https://github.com/Dana-Sarkawt"><i class="fa-brands fa-github fa-2xl dark:text-white hover:text-dark-100 dark:hover:text-dark-100"></i></a>
            </div>



            <div class="h-auto w-px pt-12">
              <!-- svelte-ignore a11y-invalid-attribute -->
              <a href="#" on:click={() => scrollIntoView("section-2")}>
              <i class="gg-arrow-long-down dark:text-white h-16"></i>

            </a>
            </div>
    </div>
    {/if}
  
  
    
</div>









<div class="w-full h-auto flex items-center gap-3 mt-28" data-aos="fade-right" data-aos-duration="2000">
  <div class="h-0.5 w-2/6  bg-dark-100"></div>
  <h2 class="text-4xl dark:text-white" style="font-family: Title-2;" id="section-2">Project</h2>
</div>




<div class="container mx-auto flex justify-center items-center  mt-50 flex-wrap" data-aos="fade-up">
   <Card />
  
</div>








<div class="w-full h-auto flex items-center gap-3 mt-28" data-aos="fade-right" data-aos-duration="2000" >
  <div class="h-0.5 w-2/6  bg-dark-100" ></div>
  <h2 class="text-4xl dark:text-white" style="font-family: Title-2;">courses</h2>
</div>


<div class="container mx-auto flex justify-center items-center  mt-50 flex-wrap" id="section-3">
  <Course />
</div>



<div class="w-full h-auto flex items-center gap-3 mt-28" data-aos="fade-right" data-aos-duration="2000">
  <div class="h-0.5 w-2/6  bg-dark-100" ></div>
  <h2 class="text-4xl dark:text-white" style="font-family: Title-2;">Skill</h2>
</div>


<div class="container mx-auto flex justify-center items-center  mt-50 flex-wrap" id="section-4">
   <Skill />
</div>


<div class="w-full h-auto flex items-center gap-3 mt-28" data-aos="fade-right" data-aos-duration="2000">
  <div class="h-0.5 w-2/6  bg-dark-100" ></div>
  <h2 class="text-4xl dark:text-white" style="font-family: Title-2;">Contact</h2>
</div>


<div class="flex w-full flex-wrap md:flex-nowrap h-auto justify-center items-center my-10" id="section-5">
  <img src="../img/contact.svg" alt="contact" class="w-80 h-80">
  <div class="w-4/5 md:w-1/2 h-32 flex dark:bg-dark-200 justify-center items-center bg-white rounded-2xl border-solid border-2 border-dark-100">

<div class="flex w-full h-auto flex-col items-center gap-5">
<div class="w-full flex  gap-5  items-center justify-center md:justify-end md:pr-24">
  <p class="text-md lg:text-xl dark:text-white">dana.code01@gmail.com</p>
  <i class="fa-solid fa-envelope fa-2xl" style="color: #5462FF;"></i>
</div>


<div class="w-full flex  gap-5  items-center justify-center md:justify-end md:pr-24">
  <p class="text-md lg:text-xl dark:text-white">dana__sarkawt</p>
  <i class="fa-brands fa-square-instagram fa-2xl" style="color: #5462FF;"></i>
</div>

</div>

</div>
</div>

<div class="flex justify-center w-full items-top mb-5">
   <!-- svelte-ignore a11y-invalid-attribute -->
   <a href="#" class="scroll-smooth" on:click={() => scrollIntoView("section-1")}>
  <GradientButton shadow color="purple" class="bg-dark-100 px-4 rounded z-100 ml-5"
  style="cursor: url(../img/pointer.png), pointer;"
  >
    <i class="fa-solid fa-caret-up fa-bounce"></i>

  </GradientButton>
   </a>

 </div>
<Footer />