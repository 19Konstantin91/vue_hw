<template>
  <div> 
    <p class="container hw">Домашняя работа.</p>

    <nav class="container header">
      <a class="logoHeader" href="#"><img class="logo" src="./assets/logo.png" alt="logo"></a>
      <button v-on:click="onBasketBtnClick">basket</button>
      <div v-if="isBasketShowed" class="basket">
        <h2>Basket</h2>
        <button v-on:click="onCloseBasketBtnClick">Закрыть</button>
      </div>
    </nav>

    <main class="product container">
      
        <div class="card" v-for="prod, i of item" v-bind:key="i" >
          <h3>{{prod.title}}</h3>
          <p>{{prod.price}}</p>
          <button>add basket</button>

        </div>
        
    </main>

    <footer class="footer container">
      Все права защищены.
    </footer>

  </div>
</template>

<script>
export default {
  data() {
    return {
      isBasketShowed: false,
      item: [
        {title: "Shirt", price: "green"},
        {title: "Shoes", price: "red"},
        {title: "Hat", price: "orange"},
        {title: "Jacket", price: "black"},
        {title: "Socks", price: "white"}
      ]
    }
  },
  methods: {
        onBasketBtnClick() {
            this.isBasketShowed = true;
        },
        onCloseBasketBtnClick() {
            this.isBasketShowed = false;
        },
    },
}
</script>


<style lang="scss">
* {
  margin: 0;
  padding: 0;
}

.container {
  margin: 0 auto;
  max-width: 1140px;
}

.hw {
  text-align: center;
}
.header {
  background: rgb(213, 236, 255);
  display: flex;
  justify-content: space-around;
  padding: 10px 0;
}
.logo {
  height: 30px;
}
.product {
  display: flex;
  justify-content: space-around;
  box-sizing: border-box;
  background: rgb(255, 207, 207);
  padding: 10px;
}
.card {
  width: 100px;
  height: 200px;
  background: rgb(209, 209, 209);
  margin: 10px;
  text-align: center;
  border: 1px solid black;
  -webkit-box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
  -moz-box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
  box-shadow: 4px 4px 8px 0px rgba(34, 60, 80, 0.2);
}
.footer {
  position:fixed;
  top: 95%;
  left: 0;
  right: 0;
}
.basket {
    width: 300px;
    height: 300px;
    background: #fff;
    border: 1px solid black;
    padding: 5px;
    border-radius: 5px;
    position: absolute;
    top: 100px;
    left: calc(65% - 10px);
}
</style>
