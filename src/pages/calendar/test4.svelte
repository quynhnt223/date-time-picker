<script>
    import { onMount } from 'svelte';

    let url = ``;

    onMount(() => url = window.location.href);
</script>

<p>Current URL: {url}</p>
<a href="./test3">test4</a>
<a href="./test4">test4</a>