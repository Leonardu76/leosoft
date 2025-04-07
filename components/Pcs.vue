<template>
  <div class="div-pcs" id="pcs" >
    <div class="div-pcs-title">
      <h2>PCs Montados</h2>
      <p class="pcs-description">Pcs prontos para o que você precisar.</p>
    </div>

    <a-carousel arrows :dots="false">
      <template #prevArrow>
      <div class="custom-slick-arrow" style="left: 10px; z-index: 1">
      </div>
    </template>
    <template #nextArrow>
      <div class="custom-slick-arrow" style="right: 10px">
      </div>
    </template>

      <div
        v-for="(group, groupIndex) in groupedPcs"
        :key="groupIndex"
        class="div-pcs-row"
      >
        <div class="div-img" v-for="(pc, index) in group" :key="index">
          <div class="img">
            <a-image
              :preview="{ visible: false }"
              :width="200"
              :height="200"
              :src="pc.mainImage"
              @click="visibles[groupIndex * 5 + index] = true"
            />
            <div style="display: none">
              <a-image-preview-group
                :preview="{ visible: visibles[groupIndex * 5 + index], onVisibleChange: vis => (visibles[groupIndex * 5 + index] = vis) }"
              >
                <a-image v-for="(img, i) in pc.previewImages" :key="i" :src="img" />
              </a-image-preview-group>
            </div>
          </div>
          <div class="div-text">
            <p>{{ pc.price }}</p>
            <p>
              <strong>{{ pc.name }}</strong>
              <hr />
              {{ pc.description }}

            </p>
            
            <a class="button" target="_blank" :href="getNumerApiWhastsapp(pc.name)" title="Comprar"><WhatsAppOutlined /> Comprar</a>
          </div>
        </div>
      </div>
    </a-carousel>
  </div>
</template>

<script lang="ts" setup>
import { h, ref, computed } from 'vue'
import { WhatsAppOutlined, RightCircleOutlined } from '@ant-design/icons-vue';

const pcs = [  {
    mainImage: '/assets/imgs/pc-gamer-2.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Deluxe',
    description: 'NVídia GeForce RTX 3060, 16GB RAM, SSD 500GB, Gabinete RGB, Mouse e telcado',
  },
  {
    mainImage: '/assets/imgs/pc-gamer.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Basic',
    description: 'Ryzen 5 5500, NVídia GeForce RTX 4060, 12GB RAM, SSD 250GB, Gabinete RGB',
  },
  {
    mainImage: '/assets/imgs/pc-gamer4.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Supreme',
    description: 'Ryzen 7 8700g, NVídia GeForce RTX 4060, 64GB RAM, SSD 1TB, Gabinete RGB',
  },
  {
    mainImage: '/assets/imgs/pc-gamer-2.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Deluxe',
    description: 'NVídia GeForce RTX 3060, 16GB RAM, SSD 500GB, Gabinete RGB, Mouse e telcado',
  },
  {
    mainImage: '/assets/imgs/pc-gamer.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Basic',
    description: 'Ryzen 5 5500, NVídia GeForce RTX 4060, 12GB RAM, SSD 250GB, Gabinete RGB',
  },
  {
    mainImage: '/assets/imgs/pc-gamer4.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Supreme',
    description: 'Ryzen 7 8700g, NVídia GeForce RTX 4060, 64GB RAM, SSD 1TB, Gabinete RGB',
  },
  {
    mainImage: '/assets/imgs/pc-gamer-2.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Deluxe',
    description: 'NVídia GeForce RTX 3060, 16GB RAM, SSD 500GB, Gabinete RGB, Mouse e telcado',
  },{
    mainImage: '/assets/imgs/pc-gamer-2.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Deluxe',
    description: 'NVídia GeForce RTX 3060, 16GB RAM, SSD 500GB, Gabinete RGB, Mouse e telcado',
  },
  {
    mainImage: '/assets/imgs/pc-gamer.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Basic',
    description: 'Ryzen 5 5500, NVídia GeForce RTX 4060, 12GB RAM, SSD 250GB, Gabinete RGB',

  },
  {
    mainImage: '/assets/imgs/pc-gamer4.png',
    previewImages: [
      '/assets/imgs/game1.webp',
      '/assets/imgs/game2.webp',
      '/assets/imgs/game3.jpg',
      '/assets/imgs/banner2.jpg',
    ],
    price: 'R$ 0.000,00',
    name: 'PC Gamer ITX Arena Supreme',
    description: 'Ryzen 7 8700g, NVídia GeForce RTX 4060, 64GB RAM, SSD 1TB, Gabinete RGB',
  },]

const chunkArray = <T>(arr: T[], size: number): T[][] =>
  Array.from({ length: Math.ceil(arr.length / size) }, (_, i) =>
    arr.slice(i * size, i * size + size)
  )

const groupedPcs = computed(() => chunkArray(pcs, 7))
const visibles = ref(Array(pcs.length).fill(false))
function getNumerApiWhastsapp(text: string) {
  return `https://api.whatsapp.com/send?phone=5531985808502&text=Olá!%20Gostaria%20de%20saber%20mais%20sobre%20o%20produto:%20${text}`
}
</script>

<style scoped>
.div-pcs {
  background-color: #1E293B;
  padding-bottom: 40px;
}

.div-pcs-title {
  margin-inline-start: 95px;
  padding-top: 20px;
  font-size: 20px;
}

.div-pcs-row {
  display: inline-flex !important;
  justify-content: center;
  flex-wrap: nowrap;
}

.div-img {
  background-color: #0F172A;
  margin: 14px;
}

.div-text {
  max-width: 180px;
  margin: 12px;
  color: white;
}

.img {
  margin: 7px;
}

.ant-image-img {
  margin-inline-start: 10px;
}

h2, p {
  color: white;
  margin-left: 14px;
  font-family: poppins;
}

.pcs-description {
  color: #ffffffa2;
}

/* Setas personalizadas */
.custom-arrow {
  background-color: #0F172A;
  color: white;
  border: none;
  font-size: 24px;
  padding: 10px 16px;
  cursor: pointer;
  z-index: 1;
  border-radius: 4px;
}

.custom-arrow.left {
  position: absolute;
  top: 50%;
  left: -32px;
  transform: translateY(-50%);
}

.custom-arrow.right {
  position: absolute;
  top: 50%;
  right: -32px;
  transform: translateY(-50%);
}

.slick-arrow{
  color: white;
  font-size: 30px;
  transition: cubic-bezier(0.075, 0.82, 0.165, 1) 0.5s;

}
.slick-arrow:hover{
  font-size: 39px !important;
  transition: cubic-bezier(0.075, 0.82, 0.165, 1) 0.5s;
  color:white;
}

.button{
  margin: 10px;
    padding: 10px;
    display: inline-flex;
    gap: 10px;
    align-content: space-between;
    align-items: center;
background: #081c3d;
    width: 90%;
    font-size: 16px;
    opacity: 0;
  visibility: hidden;
  transition: opacity 0.5s ease;
  text-align: center;
  justify-content: center;

}
.button:hover{
scale: 1.1;
transition: 1s;
color: white;
}

.div-img:hover .button {
  opacity: 1;
  visibility: visible;
}


.button:hover .anticon {
  color: green;
transition: 1s;
}
</style>
