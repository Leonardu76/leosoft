<template>
  <div  >
    
  <a-carousel  autoplay>
    <div class="slide">
      <div class="div-img"  style="background-image: url('assets/imgs/banner.png')">
        <div class="text-box">
          <h2 class="slide-title">A melhor seleção de PCs, Notebooks e Periféricos</h2>
          <p class="slide-description">Desempenho, qualidade e preço justo para quem gosta de tecnologia.</p>
        </div>
      </div>
    </div>
    
    <div class="slide" >
      <div class="div-img" style="background-image: url('assets/imgs/banner3.jpg')">
        <div class="text-box">
          <h2 class="slide-title">Ofertas exclusivas</h2>
          <p class="slide-description"> <strong>Aproveite descontos em toda a loja!</strong></p>
        </div>
      </div>
    </div>

  </a-carousel>
</div>

</template>

  
  <script setup>
  </script>
  
  <style scoped>
:deep(.slick-slide) {
  /* height: 400px; */
  position: relative;
}

.div-img {
  min-height: 750px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
  display: flex;
  align-items: center;
}

.div-img::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.5);
  z-index: 1;
}

.text-box {
  position: relative;
  z-index: 2;
  padding: 20px 30px;
  border-radius: 10px;
  color: #fff;
  max-width: 400px;
  margin-left: 40px;
  text-align: left;
  background-color: #0f172aa8;
}

.text-box h3 {
  font-size: 24px;
  margin: 0;
}

.text-box h4 {
  font-size: 16px;
  margin-top: 10px;
}

h2,h3,h4,p{
  font-family: Playfair Display;
  font-weight: 400;
  font-size: 30px;
}
 
.slide-description{
  font-size: large;
  color: #ffffffa2;
  font-weight: bold;

}
  </style>
  