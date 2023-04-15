<script>
    import Account from "/src/components/icons/Account.svelte";
    import Design from "/src/components/icons/Design.svelte";
    import Home from "/src/components/icons/Home.svelte";
    import People from "/src/components/icons/People.svelte";
    import { isActive, url } from '@roxi/routify'
    import { onMount } from 'svelte'
    const links = [
    ['./index', 'Home', Home],
    ['./people', 'Inspiration', People],
    ['./design', 'Design', Design],
    ['./account', 'Account', Account]
  ]
  onMount(async () => {
    const items = document.querySelectorAll(".item")
  items.forEach((item, index) => {
    item.addEventListener("click", () => clickitem(item, index));
    });

    function clickitem(item, index) {
        const wave = item.children[2]
        wave.classList.add("wave2");      
        setTimeout(function() {            
        wave.classList.remove("wave2")
    }, 200);
     
    }
})
  


  
</script>
<!-- routify:options preload="proximity" -->

<div class="surface">
    <slot />
</div>
<div class="bottom-bar">
    {#each links as [path, name, icon]}
    <a href={$url(path)} class="item" class:active={$isActive(path)}>
        <svelte:component this={icon} /><span>{name}</span><div class="wave"></div>
    </a>
    {/each}
</div>
