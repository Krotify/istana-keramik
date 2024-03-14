<script>
    import Footer from "../footer.svelte";
import Nav from "../nav.svelte";

</script>
<Nav />
<a href="" style="font-size: 15px;padding: 0px 20px"align="left"> 🔙 kembali ke list produk</a>
<div class="flex-container">
    <div class="flex-content1">
        <img src="aurora.avif" alt="nama gambar">
    </div>
        
    <div class="flex-content2">
        <h1>Title</h1>
        <p style="word-wrap: break-word;">Lorem ipsum dolor sit amet, consectetur adipiscing elit. Aliquam in convallis nisl, tempus molestie augue. Maecenas quis ornare mi. Duis risus tellus, fringilla in ultrices id, sagittis imperdiet sapien. Vestibulum luctus est lectus, nec accumsan mi gravida non. Quisque ullamcorper turpis ac viverra bibendum. Sed feugiat, purus sed scelerisque imperdiet, urna urna pellentesque augue, at mattis mauris nisl sit amet elit. Integer quis commodo urna. Nullam massa dui, feugiat a aliquet vitae, tempor sed diam.</p>
        <a href="" style="background-color: black; border-radius:5px; color:#fff; font-size:15px; padding:10px 12px; margin:10px 0">Order via WhatsApp</a>
    </div>
</div>

<style>
    .flex-container {
        display: flex;
        font-size: 30px;
        padding: 100px;
        text-align: center;
    }
    
    img {
        max-width: 500px;
    }
    
    .flex-content1 {
        flex: 1;
    }
    
    .flex-content2 {
        flex: 1;
        display: flex;
        flex-direction: column;
        align-items: flex-start;
        padding-left: 20px;
        text-align: left;
    }
    p{
        font-size: 20px;
    }
    
    @media (max-width: 950px) {
        .flex-container {
            flex-direction: column;
            align-items: center;
            padding: 20px; /* Adjust padding for mobile */
        }
    
        .flex-content1, .flex-content2 {
            flex: 1;
            padding: 0; /* Remove padding for mobile */
        }
    
        img {
            max-width: 100%; /* Make the image responsive */
        }
    }
    </style>
<Footer />