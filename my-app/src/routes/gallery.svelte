
<style>
* {
  box-sizing: border-box;
}

.flex-container {
  display: flex;
  flex-wrap: wrap;
  font-size: 30px;
  text-align: center;
}

.flex-item-left {


  flex: 50%;
}

.flex-item-right {


  flex: 50%;
}

@media (max-width: 800px) {
  .flex-item-right, .flex-item-left {
    flex: 100%;
  }
}
</style>



<center style="margin-top: 60px;"><h1 class="text-4xl font-semibold mb-10">Gallery</h1></center>
<div class="flex-container">
  <div class="flex-item-left"><img src="gambar1.webp"></div>
  <div class="flex-item-right"><img src="gambar2.webp"></div>
  <div class="flex-item-left"><img src="gambar3.webp"></div>
  <div class="flex-item-right"><img src="gambar4.webp"></div>
  <div class="flex-item-left"><img src="gambar5.webp"></div>
  <div class="flex-item-right"><img src="gambar6.webp"></div>
</div>




