<template>
  <div id="app">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.1.1/css/all.min.css" integrity="sha512-KfkfwYDsLkIlwQp6LFnl8zNdLGxu9YAA1QvwINks4PhcElQSvqcyVLLD9aMhXd13uQjoXtEKNosOWaZqXgel0g==" crossorigin="anonymous" referrerpolicy="no-referrer" />

  <div class="container h-100">
    <div id="menu-cus">
      <p id="title-site">Matheus <span style="color:blue">Ribeiro</span></p>
      <div class="d-flex">
        <p class="item-menu-active" v-on:click="changeBar">Inicio</p>
        <p class="item-menu" v-on:click="changeBar">Projetos</p>
        <i class="fa-solid fa-lightbulb lampada"></i>
      </div>
    </div>
    <div id="item-body" v-if="firSide">
    <div class="col-md-4">
      <div id="foto" >
      <img id="img-logo" src="./assets/me.jpg">
      </div>
    </div>
    <div class="col-md-8">
      <div class="pl-4">
      <h1 id="name">Ola, Tudo Bem?</h1>
      <p id="text-desc">Meu nome é Matheus Menezes, tenho 21 Anos e e'stou no ultimo ano de Ciência da Computação, Ja atuando 1 ano na area como desenvolvedor web, como stack principal asp.net core para back end 
        e Vue Js para fronend. Com o principal objetivo de me torna um Full Stack
      </p>
      </div>
      <div class="d-flex justify-content-center pt-3">
        <div class="redes-socias mr-3"><img class="img-redes" src="./assets/1051326.png"></div>
        <div class="redes-socias  ml-3"><img class="img-redes" src="./assets/174857.png"></div>
      </div>
    </div>
    </div>
    <div v-else>
      <div id="project-body" v-if="projectDetalhe == false">
      <div id="projects pt-5" @click="openDetalhe">
        <div class="cards-project mt-5">
          <div class="card-head">
            <img id="foto-project" src="./assets/og-default-image.jpeg">
            <div class="card-desc-project">
                POKEMON
            </div>
          </div>
        </div>
      </div>
       <div id="projects pt-5" @click="openDetalhe">
        <div class="cards-project mt-5">
          <div class="card-head">
            <img id="foto-project" src="./assets/pasted image 0.png">
            <div class="card-desc-project">
                CRUD SIMPLES
            </div>
          </div>
        </div>
      </div>
      <div id="projects pt-5" @click="openDetalhe">
        <div class="cards-project mt-5">
          <div class="card-head">
            <img id="foto-project" src="./assets/post_chat.png">
            <div class="card-desc-project">
                MENRICHAT
            </div>
          </div>
        </div>
      </div>
    </div>
      <ProjectInfo v-if="projectDetalhe"></ProjectInfo>
    </div>
  </div>
  </div>
</template>

<script>
import ProjectInfo from './components/project-info.vue'
export default {
  data () {
    return {
      firSide: true,
      projectDetalhe: false
    }
  },
  name: 'App',
  components: {
    ProjectInfo
  },
  methods: {
    changeBar (e) {
      document.querySelectorAll('.item-menu-active').forEach((Element) => {
        Element.classList.remove('item-menu-active')
        Element.classList.add('item-menu')
      })
      this.firSide = !this.firSide
      e.target.classList.remove('item-menu')
      e.target.classList.add('item-menu-active')
    },
    openDetalhe () {
      this.projectDetalhe = true
    }
  }
}
</script>

<style>
html,body{
  margin: 0px;
  padding: 0px;
  height: 100%;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  margin: 0px;
  padding: 0px;
  background-color: rgb(7, 3, 15);
  width: 100%;
  overflow-y: none;
  height: 100%;
}
#menu-cus{
  display: flex;
  height: 50px;
  padding-right: 30px;
  justify-content: space-between;
  align-items: center;
}

#project-body{
  justify-content: space-evenly;
  flex-wrap: wrap;
  display: flex;
}
#foto-project{
  height: 95%;
   border-radius: 10px;
  width: 95%;
}
#projects{
  display: flex;
}
.card-desc-project{
  background: rgba(0, 0, 0, 0.603);
  position: absolute;
  bottom: 6px;
  width: 95%;
  border-radius: 0 0 10px 10px;
  display: flex;
  justify-content: center;
  align-items: center;
  color: white;
  font-weight: bold;
}
.cards-project{
  height: 250px;
  width: 250px;
  transition: 500ms;
  cursor: pointer;
  background: rgb(1, 1, 177);
  border-radius: 10px;
}
.cards-project:hover{
  transform: scale(1.1);
}
.card-head{
  height: 100%;
  width: 100%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
}
.item-menu{
  color: blue;
  padding: 0px;
  cursor: pointer;
  margin: 0px;
  font-weight: bold;
  cursor: pointer;
  padding-left: 10px;
  padding-right: 10px;
  font-size: 20px;
}
.item-menu-active{
  color: white;
  padding: 0px;
  margin: 0px;
  text-decoration: underline;
  padding-left: 10px;
  padding-right: 10px;
  font-size: 20px;
}
#item-body{
  display: flex;
  height: 94%;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
}
#foto{
  height: 300px;
  width: 300px;
  background: white;
  border: 15px solid rgb(0, 0, 124);
  border-radius: 50%;
}
#img-logo{
  height: 100%;
  width: 100%;
  border-radius: 50%;
  object-fit: contain;
}

#name{
  color: white;
  font-weight: bold;
}
#title-site{
  font-size: 24px;
  padding: 0px;
  margin: 0px;
  font-weight: bold;
  color: white;
}
.lampada{
  color: yellow;
  padding-left: 15px;
  font-size: 24px;
  cursor: pointer;
}
#text-desc{
  color: white;
  padding-left: 15px;
}
.redes-socias{
  height: 50px;
  width: 50px;
  cursor: pointer;
  background: white;
  transition: 500ms;
  border-radius: 8px;
}
.redes-socias:hover{
  transform: scale(1.2);
}
.img-redes{
  height: 100%;
  width: 100%;
}


</style>
