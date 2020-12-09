<script>
    export let isDarkMode
    export let srcPair
    export let alt
    export let label
    export let link
</script>

<a href={link} target="_blank" rel="noopener noreferrer" class="download">
    <img src={isDarkMode ? srcPair[0] : srcPair[1]} alt={alt}/>
    <p>{label}</p>
</a>
