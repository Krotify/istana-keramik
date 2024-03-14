<script>
    import Footer from "../footer.svelte";
import Nav from "../nav.svelte";

</script>
<Nav />
    <div class="flex-container">
        <div><img src="aurora.avif"></div>
        
    <div class="flex-container2">
        <h1>Title</h1>
        <div><p>DeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsiDeskripsi</p></div>
        <button style="background-color: green;">Click Button</button>
    </div>
    </div>

<style>
    .flex-container {
        display: flex;
    }
    .flex-container2 {
        display: flex;
        flex-direction: column;
        
    }
    
</style>
<Footer />