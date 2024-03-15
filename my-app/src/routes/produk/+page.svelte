<script>
import { onMount } from 'svelte';
    import Nav from '../nav.svelte';
    import Footer from '../footer.svelte';
	export let posts = [];
  
	onMount(()=>{fetch('catalogue.json')
    	.then(response => response.json())
    	.then(data => {
      		posts = data.data;
    })});

</script>
<Nav />
<div class="content">
<center>
    <h1 class="text-4xl font-semibold mb-10">Produk kami</h1>
    <p>Untuk produk berupa barang bisa kontak ke nomor WhatsApp kami untuk menanyakan stok</p>
    
</center>
{#each posts as post}
    <div class="card">
      <div class="card-image">
        <img src="{post.imageurl}" alt="{post.title}">
      </div>
      <div class="card-content">
        <h2 class="card-title">{post.title}</h2>
        <p class="card-description" style="margin-bottom: 10px;">{post.desc}</p>
        <a href="/produk/{post.title}" class="bg-black text-white px-3 py-2 my-1 rounded">Lebih Lanjut</a>
      </div>
    </div>
{/each}
</div>
<Footer />

<style>
    .content{
        padding: 50px;
    }
    
    .card {
      display: flex;
      flex-direction: row;
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
      max-height: 150px;
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