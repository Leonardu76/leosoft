<template>
  <div id="quem-somos" >
    
    <div class="slide">

      <div class="div-img"  style="background-image: url('assets/imgs/quemsomos.webp')">
        
        <div class="text-box">
          <h2>Quem somos</h2>
          <p class="slide-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis doloremque illo illum iste minus facilis dolores laborum sint nostrum dolorem, repudiandae exercitationem, ad eius officiis esse eaque, praesentium omnis! Veniam?</p>
        </div>

        <div class="text-box _2">
          <h2>Nossa Missão</h2>
          <p class="slide-description">Lorem ipsum dolor sit amet consectetur adipisicing elit. Veritatis doloremque illo illum iste minus facilis dolores laborum sint nostrum dolorem, repudiandae exercitationem, ad eius officiis esse eaque, praesentium omnis! Veniam?</p>
        </div>

        
        <div class="text-box _3">
          <h2>Cases de sucesso</h2>
          <a-carousel autoplay :dots="false" effect="scrollx">
    <div v-for="(testimonial, index) in testimonials" :key="index" class="carousel-slide">
      <p class="testimonial-text">"{{ testimonial.text }}"</p>
      <p class="testimonial-author">- {{ testimonial.author }}</p>
    </div>
  </a-carousel>
        </div>
      </div>
    </div>

    

</div>

</template>

  
  <script setup>

const testimonials = [
  { text: 'Produto excelente, chegou rápido e bem embalado!', author: 'João Silva' },
  { text: 'Ótimo atendimento, voltarei a comprar!', author: 'Maria Oliveira' },
  { text: 'Super recomendo, melhor experiência que já tive!', author: 'Carlos Souza' },
  { text: 'Muito satisfeito com a qualidade e o suporte.', author: 'Ana Lima' },
];
  </script>
  
  <style scoped>
:deep(.slick-slide) {
  /* height: 400px; */
  position: relative;
}

.carousel-slide {
  height: 120px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  text-align: center;
  background: black;
  color: white;
  font-family: 'Poppins', sans-serif;
  padding: 20px;
}

.testimonial-text {
  font-size: 1rem;
  margin-bottom: 8px;
}

.testimonial-author {
  font-weight: bold;
  font-size: 0.9rem;
  opacity: 0.7;
}

.div-img {
  min-height: 750px;
  background-size: cover;
  background-position: center;
  background-repeat: no-repeat;
  position: relative;
}

.div-img::before {
  content: "";
  position: absolute;
  inset: 0;
  background: rgba(0, 0, 0, 0.699);
  z-index: 1;
}

.text-box {
  position: relative;
  z-index: 2;
  padding: 20px 30px;
  border-radius: 10px;
  color: #fff;
  max-width: 800px;
  text-align: left;
}

.text-box._2 {
  float: right;
  text-align: end;
}

._3 {
  display: inline-block;
  max-width: 97%;
  text-align: center;

}

.text-box h3 {
  font-size: 24px;
  margin: 0;
}

.text-box h4 {
  font-size: 16px;
  margin-top: 10px;
}


 
.slide-description{
  font-size: 22px;
  color: #fffffff2;
  font-weight: bold;
  font-family: "poppins", serif;
  line-height: 40px;


}




.div-pcs-title {
  margin-inline-start: 95px;
  padding-top: 20px;
  font-size: 20px;
}
  </style>
  