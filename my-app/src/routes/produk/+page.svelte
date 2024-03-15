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

<Footer />

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