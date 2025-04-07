<template >
  <a-float-button-group shape="circle" :style="{ right: '24px' }">
      <a class="button" target="_blank" href="https://api.whatsapp.com/send?phone=5531985808502&text=Olá!%20Gostaria%20de%20saber%20mais%" title="Entrar em contato">
  
      <a-float-button class="whatsapp">
        <template #icon>
          <WhatsAppOutlined />
        </template>
      </a-float-button>
    </a>
  
      <a-float-button class="profile" @click="setModal1Visible(true)">
        <template #icon>
          <ProfileOutlined />      </template>
      </a-float-button>
      
      <a-back-top :visibility-height="0" />
    </a-float-button-group>
   
    <a-modal
        v-model:open="modal1Visible"
        title="Solicitar orçamento"
        style="top: 20px"
        @ok="setModal1Visible(false)"
      >
      </a-modal>
    <div class="principal">
  
        <a-row type="flex" justify="center" align="middle" class="body">
            <a-col class="gutter-row" :span="5">
                <div>
                    <nuxt-link to='/'>
                        <img class="logo-footer"
                            src="/assets/imgs/logo.png"
                            alt="">
                    </nuxt-link>
                </div>
            </a-col>
  
            <a-col class="gutter-row adress-footer-div" :span="10">
                <div class="adress-footer">
                    <div class="adress-footer-item">
                        <PhoneOutlined /> +55000000000
                    </div>
                    <div class="adress-footer-item">
                        <MailOutlined /> company@yahoo.com.br
                    </div>
                    <div class="adress-footer-item">
                        <CompassOutlined /> Granjas Primavera - 73 -
                        <strong>Granjas
                            339360-00 - Ribeirão das Neves - MG </strong>
                    </div>
                </div>
            </a-col>
            <a-col class="gutter-row">
                <div class="redes-sociais">
                    <h5>Siga-nos</h5>
                    <nuxt-link to='https://www.instagram.com/' target="_blank">
                        <InstagramOutlined />
                    </nuxt-link>
                    <nuxt-link to='https://www.facebook.com/' target="_blank">
                        <FacebookOutlined />
                    </nuxt-link>
                    <nuxt-link to='https://www.youtube.com/' target="_blank">
                        <YoutubeOutlined />
                    </nuxt-link>
                    <nuxt-link to='https://twitter.com/login?lang=pt' target="_blank">
                        <TwitterOutlined />
                    </nuxt-link>
                </div>
            </a-col>
        </a-row>
        <div class="footer-footer">
            <p>Copyright © {{ anoAtual }}</p>
            Desenvolvido com
            <CoffeeOutlined /> por
            <nuxt-link to='https://leonardoliveiras.com.br/' target="_blank" class="link-by">
                Leonardo Souza
            </nuxt-link>
        </div>
    </div>
  </template>
  
  <script setup>
import { ref } from 'vue'
import {
  InstagramOutlined,
  FacebookOutlined,
  YoutubeOutlined,
  TwitterOutlined,
  PhoneOutlined,
  MailOutlined,
  CompassOutlined,
  CoffeeOutlined,
  WhatsAppOutlined,
  ProfileOutlined
} from '@ant-design/icons-vue'

const modal1Visible = ref(false)
const anoAtual = new Date().getFullYear()

const setModal1Visible = (open) => {
  modal1Visible.value = open
}
</script>
  
  <style scoped>
  .principal {
    background-color: var(--secondary-color);
    margin-top: 20px;
  
  }
  
  .redes-sociais {
    font-size: 20px;
    font-family: Poppins;
  
    text-align: center;
  }
  .whatsapp {
    background-color: #25D366;
    color: white;
  }
  
  .profile {
    background-color: #64748B;
    color: white;
  } 
  .adress-footer-item .anticon {
    margin-right: 15px !important;
  }
  
  .redes-sociais .anticon {
    margin-right: 4px !important;
    text-align: center;
    color: white;
    transition: 1s;
  
  }
  
  .redes-sociais .anticon:hover {
    font-size: 25px;
    transition: 1s;
  }
  
  h5 {
    text-transform: uppercase;
    margin-top: unset;
    margin-bottom: 2px;
    font-family: Poppins;
    color: white;
  
  
  
  }
  
  .adress-footer {
    color: white;
    font-size: 15px;
    text-align: start;
    font-family: Poppins;
  
  }
  
  .adress-footer-item {
    line-height: 40px;
  }
  
  .footer-footer {
    color: white;
    text-align: center;
    font-family: Poppins;
    font-size: 15px;
  
  }
  
  .link-by {
    font-weight: bolder;
  }
  
  .logo-footer {
    width: 140px;
  }
  @media screen and (max-width: 635px) {
    .body {
        display: inline-grid;
    align-content: stretch;
    justify-content: space-evenly;
    align-items: center;
    justify-items: center;
    }
    .adress-footer-div{
        max-width: -webkit-fill-available;
    margin: 20px;
    }}
  </style>