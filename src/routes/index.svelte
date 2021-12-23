<script>
    import OBJ from '$lib/object.svelte';
    const print = () => window.print();
    let list = "aaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa\naaaaaa";
</script>
<noprint>
아래에 필요한 문자열을 \n (line break) 별로 배치해주세요.
<textarea name="Text1" cols="40" rows="5" bind:value={list}></textarea>
<button on:click={print}>인쇄</button>
</noprint>

<div class="list">
    {#each list.split("\n") as item}
        <OBJ text={item}/>
	{/each}
    
</div>
<style>
noprint {
    display: flex;
    flex-direction: column;
}
@media print {
    noprint {
        display: none;
    }
}
</style>