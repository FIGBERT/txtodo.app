<script>
    export let isDarkMode
    export let srcPair
    export let alt
    export let label
    export let link
</script>

<a href={link} class="w-32 h-10 rounded-lg border border-{isDarkMode ? "2" : "4"} border-{isDarkMode ? "white" : "black"} border-solid flex items-center" target="_blank" rel="noopener noreferrer">
    <img src={isDarkMode ? srcPair[0] : srcPair[1]} alt={alt} class="w-5 my-1 mx-2"/>
    <p class="{isDarkMode ? "text-white" : "text-dark"} text-xs leading-snug">{label}</p>
</a>