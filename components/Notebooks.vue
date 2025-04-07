<template>
<div class="div-pcs" id="notebooks">
    <div class="div-pcs-title">
      <h2>Notebooks</h2>
    </div>

    <div class="div-pcs-row">
      <a-tabs v-model:activeKey="activeKey">
        <a-tab-pane key="1" class="div-tab-row">
          <template #tab>
            <span>
              <LaptopOutlined />
              Gamer
            </span>
          </template>
          <div class="div-img">
            <div class="img">
              <a-image :preview="{ visible: false }" :width="200" :height="200" src="/assets/imgs/note1.png"
                @click="visibles[0] = true"  />

              <div style="display: none">
                <a-image-preview-group :preview="{
                  visible: visibles[0],
                  onVisibleChange: (vis) => (visibles[0] = vis),
                }">
                  <a-image src="/assets/imgs/game1.webp" />
                  <a-image src="/assets/imgs/game2.webp" />
                  <a-image src="/assets/imgs/game3.jpg" />
                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 0.000,00</p>
              <p>
                <strong>ASUS TUF Gaming </strong>
              </p>
              <hr />

              <ul>
                <li>15,6 Polegadas</li>
                <li>Cinza</li>
                <li>SSD 512 GB</li>
                <li>Core i5 2.3 GHz</li>
                <li>16 GB</li>
                <li>Windows 11 Home</li>
                <li>Anti Glare Coating</li>
              </ul>
            </div>
            <a class="button" target="_blank" :href="getNumerApiWhastsapp('Notebook ASUS TUF Gaming')" title="Comprar">
              <WhatsAppOutlined /> Comprar
            </a>

          </div>

          <div class="div-img">
            <div class="img">
              <a-image :preview="{ visible: false }" :width="200" :height="200" src="/assets/imgs/note2.png"
                @click="visibles[1] = true" />

              <div style="display: none">
                <a-image-preview-group :preview="{
                  visible: visibles[1],
                  onVisibleChange: (vis) => (visibles[1] = vis),
                }">
                  <a-image src="/assets/imgs/game1.webp" />
                  <a-image src="/assets/imgs/game2.webp" />
                  <a-image src="/assets/imgs/game3.jpg" />
                  <a-image src="/assets/imgs/banner2.jpg" />
                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 0.000,00</p>
              <p>
                <strong>Acer Nitro V15 </strong>
              </p>
              <hr />

              <ul>
                <li>Intel Core i5 13ª</li>
                <li>8GB RAM</li>
                <li>512GB SSD</li>
                <li>15.6 Polegadas</li>
                <li>Windows 11 Home</li>
                <li>NVIDIA GeForce RTX3050 - ANV15-51-58AZ</li>
              </ul>
            </div>
            <a class="button" target="_blank" :href="getNumerApiWhastsapp('Notebook Acer Nitro V15')" title="Comprar">
              <WhatsAppOutlined /> Comprar
            </a>

          </div>
        </a-tab-pane>
        <a-tab-pane key="2">
          <template #tab>
            <span>
              <LaptopOutlined />
              Empresarial
            </span>
          </template>
          <div class="div-img">
            <div class="img">
              <a-image :preview="{ visible: false }" :width="200" :height="200" src="/assets/imgs/note3.webp"
                @click="visibles[0] = true"/>

              <div style="display: none">
                <a-image-preview-group :preview="{
                  visible: visibles[0],
                  onVisibleChange: (vis) => (visibles[0] = vis),
                }">
                  <a-image src="/assets/imgs/game1.webp" />
                  <a-image src="/assets/imgs/game2.webp" />
                  <a-image src="/assets/imgs/game3.jpg" />
                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 0.000,00</p>
              <p>
                <strong>LENOVO IdeaPad 1i</strong>
              </p>
              <hr />

              <ul>
                <li>Intel Core i5-1235U</li>
                <li>Cinza</li>
                <li>SSD 512GB</li>
                <li>Core i5 2.3 GHz</li>
                <li>16GB RAM</li>
                <li>15,6 Polegadas</li>
                <li>Windows 11 Home</li>
              </ul>
            </div>
            <a class="button" target="_blank" :href="getNumerApiWhastsapp('LENOVO IdeaPad 1i')" title="Comprar">
              <WhatsAppOutlined /> Comprar
            </a>

          </div>
        </a-tab-pane>
      </a-tabs>
    </div>
  </div>
</template>
<script lang="ts" setup>
import { ref } from "vue";
const visibles = ref([false, false, false]);
import { LaptopOutlined, WhatsAppOutlined } from "@ant-design/icons-vue";

const activeKey = ref("1");
function getNumerApiWhastsapp(text: string) {
  return `https://api.whatsapp.com/send?phone=5531985808502&text=Olá!%20Gostaria%20de%20saber%20mais%20sobre%20o%20produto:%20${text}`
}
</script>

<style scoped>
.div-img {
  background-color: #1e293b;
  margin: 14px;
  transition: 1s;

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



.div-pcs-row,
.div-tab-row {
  display: flex;
  justify-content: center;
}

h2,
p,  #notebooks  span {
  color: white;
  margin-left: 14px;
  font-family: poppins;
}

.pcs-description {
  color: #ffffffa2;
}

.div-pcs-title {
  margin-inline-start: 95px;
  padding-top: 20px;
  font-size: 20px;
}

#rc-tabs-0-tab-1 {
  color: #ffffffa2 !important;
}

.button {
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

.button:hover {
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
