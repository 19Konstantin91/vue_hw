<template>
  <div> 
    <p class="container hw">Домашняя работа.</p>

    <nav class="container header">
      <a class="logoHeader" href="#"><img class="logo" src="./assets/logo.png" alt="logo"></a>
      <button>basket</button>
    </nav>

    <main class="product container">
      
        <div class="card" v-for="item, i of list" v-bind:key="i" >
          <h3>{{cart.title}}</h3>
          <p>{{cart.price}}</p>
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
      item: [
        {title: 'Shirt', price: 'green', id},
        {title: 'Shoes', price: 'red', id},
        {title: 'Hat', price: 'orange', id},
        {title: 'Jacket', price: 'black', id},
        {title: 'Socks', price: 'white', id},
      ]
    }
  }
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
</style>
