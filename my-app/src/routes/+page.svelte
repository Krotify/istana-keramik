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
    <button class="bg-black text-white px-3 py-2 rounded">Hubungi Kami</button>
    
</div>

<div class="p-20">
    <h2 class="text-4xl font-semibold mb-10">Tentang Kami</h2>
    <p>Tidak ada bangunan yang kokoh apabila tidak ada fondasi yang kuat dan material yang berkualitas.kami berusaha keras melakukan yang terbaik untuk bangunan rumah anda. Istana Keramik adalah toko bangunan dan penyedia jasa bangunan terbaik di Purworejo. Kami menyediakan banyak bahan bangunan, mulai dari keramik, granit, platform pvc, hingga water heater. Tidak hanya itu kami juga menyediakan jasa - jasa pembangunan. Apapun kebutuhan anda kami siap melayani anda dengan ramah dan tamah.</p>
    <br>
    <b>Kontak</b>
    <p>Alamat   :  Jl. WR Supratman No.24, Plaosan II, Baledono, Kec. Purworejo, Kabupaten Purworejo, Jawa Tengah 54118</p>
    <p>Nomor WhatsApp   :   0818295921</p>
</div>

<div class = "box">
  <div id="layanan">
  <center>
    <h2 class="text-4xl font-semibold mb-10">Layanan</h2>
    <p>Jasa dan Layanan pembangunan yang kami tawarkan:</p>
    </center>
    </div>
    
{#each posts as post}
    <div class="card">
      <div class="card-image">
        <img src="{post.imageurl}" alt="{post.title}">
      </div>
      <div class="card-content">
        <h2 class="card-title">{post.title}</h2>
        <p class="card-description" style="margin-bottom: 10px;">{post.desc}</p>
        <a href="/produk/{post.title}" class="bg-black text-white px-3 py-2 my-1 rounded">lebih lanjut</a>
      </div>
    </div>
{/each}
<center>
  <p>Jika anda mempunyai request lainnya dapat menghubungi kami</p>
  <br>
  <button class="bg-black text-white px-3 py-2 rounded">Request Pesanan</button>
</center>
</div>



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
    .box {
      display: flex;
      flex-direction: column;
      width: 90%;
      padding-top: 40px;
      padding-bottom: 40px;
      margin: 20px auto;
      border: 1px solid #ddd;
      border-radius: 5px;
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    }
    .card {
      display: flex;
      flex-direction: column;
      width: 80%;
      margin: 20px auto;
      border: 1px solid #ddd;
      border-radius: 5px;
      box-shadow: 0 0 5px rgba(0, 0, 0, 0.1);
    }

    .card-image {
      flex: 0 0 30%;
      


    }

    .card-image img {
      width: 100%;
      max-height: 250px;
      object-fit: cover;
    }

    .card-content {
      flex: 1;
      padding: 10px;
    }

    .card-title {
      font-size: 20px;
      margin-bottom: 5px;
    }

    .card-description {
      font-size: 16px;
    }

    @media (max-width: 768px) {
      .card {
        flex-direction: column; /* Stack image and content on small screens */
      }

      .card-image {
        flex: 1; /* Make image take full width on small screens */
      }
    }

</style>