<template>
  <div class="div-pcs" id="perifericos">
    <div class="div-pcs-title">
      <h2>Periféricos</h2>
    </div>

    <div class="div-pcs-row">
      <a-tabs v-model:activeKey="activeKey">
        <a-tab-pane key="1"  class="div-tab-row">
          <template #tab>
            <span>
              <AimOutlined />
              Mouse
            </span>
          </template>
          <div class="div-img">
            <div class="img">
              <a-image
                :preview="{ visible: false }"
                :width="200"
                :height="200"
                src="/assets/imgs/mouse.png"
                @click="visibles[0] = true"
              />

              <div style="display: none">
                <a-image-preview-group
                  :preview="{
                    visible: visibles[0],
                    onVisibleChange: (vis) => (visibles[0] = vis),
                  }"
                >
                  <a-image src="/assets/imgs/mouse1.1.png" />
                 
                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 150,00</p>
                Mouse Gamer Logitech G403 Hero USB Preto
            </div>
          </div>

          <div class="div-img">
            <div class="img">
              <a-image
                :preview="{ visible: false }"
                :width="200"
                :height="200"
                src="/assets/imgs/mouse2.png"
                @click="visibles[1] = true"
              />

              <div style="display: none">
                <a-image-preview-group
                  :preview="{
                    visible: visibles[1],
                    onVisibleChange: (vis) => (visibles[1] = vis),
                  }"
                >
                  <a-image src="/assets/imgs/mouse2.1.png" />
            
                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 530,00</p>
              Mouse sem fio Logitech MX Master 3S preto 910-006561
            </div>
          </div>
        </a-tab-pane>
        <a-tab-pane key="2">
          <template #tab>
            <span>
              <LaptopOutlined />
              Teclados
            </span>
          </template>
          <div class="div-img">
            <div class="img">
              <a-image
                :width="200"
                :height="200"
                src="/assets/imgs/teclado.png"
              />

            </div>
            <div class="div-text">
              <p>R$ 149,83</p>
              Teclado Logitech K400 Plus Wireless com touchpad
            </div>
          </div>
        </a-tab-pane>

   

        <a-tab-pane key="4">
          <template #tab>
            <span>
              <SoundOutlined />              Caixas de som
            </span>
          </template>
          <div class="div-img">
            <div class="img">
              <a-image
                :preview="{ visible: false }"
                :width="200"
                :height="200"
                src="/assets/imgs/cs-som.png"
                @click="visibles[2] = true"
              />

              <div style="display: none">
                <a-image-preview-group
                
                  :preview="{
                    visible: visibles[2],
                    onVisibleChange: (vis) => (visibles[2] = vis),
                  }"
                >
                <a-image src="/assets/imgs/cx-som-2.1.png" />

                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 136,78</p>
              CAIXA DE SOM GAMER 2.0 REDRAGON STENTOR GS500 (cor: preto e vermelho | 5W)
            </div>
          </div>

          <div class="div-img">
            <div class="img">
              <a-image
                :preview="{ visible: false }"
                :width="200"
                :height="200"
                src="/assets/imgs/cs-som.png"
                @click="visibles[2] = true"
              />

              <div style="display: none">
                <a-image-preview-group
                
                  :preview="{
                    visible: visibles[2],
                    onVisibleChange: (vis) => (visibles[2] = vis),
                  }"
                >
                <a-image src="/assets/imgs/cx-som-2.1.png" />

                </a-image-preview-group>
              </div>
            </div>
            <div class="div-text">
              <p>R$ 136,78</p>
              CAIXA DE SOM GAMER 2.0 REDRAGON STENTOR GS500 (cor: preto e vermelho | 5W)
            </div>
          </div>
        </a-tab-pane>
      </a-tabs>
    </div>
  </div>
</template>
<script lang="ts" setup>
import { ref } from "vue";
const visibles = ref([false, false, false]);
import { LaptopOutlined, SoundOutlined, AimOutlined } from "@ant-design/icons-vue";
const activeKey = ref("1");
</script>

<style scoped>
.div-img {
  background-color: #0F172A;

  margin: 14px;
}
.div-pcs {
  background-color: #1e293b;

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



.div-pcs-row, .div-tab-row {
  display: flex;
  justify-content: center;
}

h2,
p, #perifericos  span {
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
:where(.css-dev-only-do-not-override-1p3hq3p).ant-tabs .ant-tabs-tabpane{
  width: auto;
}
</style>
