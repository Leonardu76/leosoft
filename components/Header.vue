<template>
    <div class="header">
    <div class="div-logo">
        <img src="/assets/imgs/logo.png" alt="">
    </div>
  
      <a-anchor 
        direction="horizontal"
        :items="[
          {
            key: 'pcs',
            href: '#pcs',
            title: 'PCs',
          },
          {
            key: 'notebooks',
            href: '#notebooks',
            title: 'Notebooks',
          },
          {
            key: 'perifericos',
            href: '#perifericos',
            title: 'Periféricos',
          },
          {
            key: 'Quem somos',
            href: '#quem-somos',
            title: 'Quem somos',
          },
          {
            key: 'localizacao',
            href: '#localizacao',
            title: 'Localização',
          },
        ]"
      />
      <a-button class="button">Compre Agora</a-button>

    </div>
  </template>


<script>

import Menubar from 'primevue/menubar';

</script>

<style>
.header{
    
    display: inline-flex;
    flex-wrap: nowrap;
    align-items: center;
    gap:150px;
}

:where(.css-dev-only-do-not-override-1p3hq3p).ant-anchor-wrapper .ant-anchor .ant-anchor-link-title{
    color: azure;
    margin-left:50px;
}
.div-logo img{
    max-width: 300px;
  max-height: 300px;
  object-fit: cover; }

  .button{
    font-weight: bold;
    background-color: #64748B;
    color: azure;
    border-radius: 8px a 16px;
  }
  .button:hover{
    transition: all 0.3s ease-in-out;
  }
  
  @media (max-width: 768px) {
    .header{
      gap: 8px;
        display: grid;
        justify-items: center;
    }
    :where(.css-dev-only-do-not-override-1p3hq3p).ant-anchor-wrapper .ant-anchor .ant-anchor-link-title{
      margin-left: 14px;

    }
  }
</style>