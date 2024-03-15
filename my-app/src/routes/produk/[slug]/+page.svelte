<script>
    import Footer from "../../footer.svelte";


import Nav from "../../nav.svelte";

import { onMount } from 'svelte';
	export let posts = [];
    export let sub
    export let image
  
	onMount(()=>{fetch('/catalogue.json')
    	.then(response => response.json())
    	.then(blog => {
      		posts = blog.data;

              for (const post of posts) {
                    if (post.title === data.title) {
                        sub = post.desc;
                        image = post.imageurl;
                        
                    }
                }
    })});


    export let data;


</script>
<Nav />
<a href="../produk" style="font-size: 15px;padding: 0px 20px"align="left"> 🔙 kembali ke list produk</a>
<div class="flex-container">
    <div class="flex-content1">
        <img src="{image}" alt="{image}">
    </div>
        
    <div class="flex-content2">
        <h1>{data.title}</h1>
        <p style="word-wrap: break-word;">{sub}</p>
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
            max-width: 300px;
            margin-bottom: 20px; /* Make the image responsive */
        }
    }
    </style>
<Footer />