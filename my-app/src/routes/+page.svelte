<script>
	import Gallery from './gallery.svelte';
    import Footer from "./footer.svelte";
import Nav from "./nav.svelte";

import { onMount } from 'svelte';
	export let posts = [];
  
	onMount(()=>{fetch('catalogue.json')
    	.then(response => response.json())
    	.then(data => {
      		posts = data.data;
    })});


</script>
<div class="notif">
    <p class = "font-semibold text-center">⚠️Hati-hati penipuan! Nomor WhatsApp cuma satu: 0818295921</p>
</div>
<Nav/>

<div class="hero">
    <h1 class="text-6xl font-semibold">Istananya <br>Bahan Bangunan</h1>
    <br>
    <b class="text-lg">Paling Lengkap dan Paling terpercaya</b>
    <p>Toko dan jasa bangunan paling lengkap dan terbesar di Puworejo</p>
    <br>
    <a href="https://wa.me/62818295921?%5Bcutomer%20website%5D%20hai%20istana%20keramik%20saya%20tertarik%20dengan%20produk%20" class="bg-black text-white px-3 py-2 rounded">Hubungi Kami</a>
    
</div>

<div class="p-20">
    <h2 class="text-4xl font-semibold mb-10">Tentang Kami</h2>
    <p>Tidak ada bangunan yang kokoh apabila tidak ada fondasi yang kuat dan material yang berkualitas.kami berusaha keras melakukan yang terbaik untuk bangunan rumah anda. Istana Keramik adalah toko bangunan dan penyedia jasa bangunan terbaik di Purworejo. Kami menyediakan banyak bahan bangunan, mulai dari keramik, granit, platform pvc, hingga water heater. Tidak hanya itu kami juga menyediakan jasa - jasa pembangunan. Apapun kebutuhan anda kami siap melayani anda dengan ramah dan tamah.</p>
    <br>
    <b>Kontak</b>
    <p>Alamat   :  Jl. WR Supratman No.24, Plaosan II, Baledono, Kec. Purworejo, Kabupaten Purworejo, Jawa Tengah 54118</p>
    <p>Nomor WhatsApp   :   0818295921</p>
</div>

  <center>
    <h2 class="text-4xl font-semibold mb-10">Layanan</h2>
    <p>Jasa dan Layanan pembangunan yang kami tawarkan:</p>
    </center>


    <div class="carousel">
      {#if posts.length > 0}
        {#each posts as post}
    
        <div class="card">
            <img src="{post.imageurl}" alt="{post.title} pic" style="width:100%">
            <div class="container">
                <h4><b>{post.title}</b></h4>
                <a class="btn" href={`/produk/${post.title}`}>Read More</a>
            </div>
        </div>
      {/each}
        {:else}
        <p>No blog posts available.</p>
      {/if}
    </div>


<center>
  <p>Jika anda mempunyai request lainnya dapat menghubungi kami</p>
  <br>
  <a href="https://wa.me/62818295921?%5Bcutomer%20website%5D%20hai%20istana%20keramik%20saya%20tertarik%20dengan%20produk%20" class="bg-black text-white px-3 py-2 rounded">Request Pesanan</a>
</center>




<Gallery />
<Footer/>
<style>
    .hero {
        text-align: center;
        background-image: url('hero.jpg');
        background-repeat: no-repeat;
        background-size: cover;
        padding-top: 150px;
        padding-bottom: 150px;
        background-position: center;
    }
    .notif{
        background-color: rgb(255, 89, 89);
        padding: 5px;
    }

    .card-image{
        width: 100px;
    }
    .card {
        box-shadow: 0 4px 8px 0 rgba(0,0,0,0.2);
        transition: 0.3s;
        border-radius: 5px; /* 5px rounded corners */
        width: 200px;
        min-width: 250px;
        margin: 20px;
        
    }
    .container{
        margin: 20px;
    }
    .carousel {
        display: flex;
        overflow-x: auto;
        scroll-behavior: smooth;
        -webkit-overflow-scrolling: touch;
        
    }
    .btn {
        background-color: #0c0a18;
        color: white;
        padding: 5px 10px;
        text-decoration: none;
    }

/* Add rounded corners to the top left and the top right corner of the image */
img {
  border-radius: 5px 5px 0 0;
}

</style>