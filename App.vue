<template>
  <div id="app">
    <!-- <img alt="Vue logo" src="./assets/logo.png"> -->
    <!-- <HelloWorld msg="Welcome to Your Vue.js App"/> -->
    <!-- <cityCard title="Mayank" subTitle="Hello Anuj Sir !!" btnText="Add to Cart"/>

    <cityCard title="Mayank" subTitle="Hello Anuj Sir !!" btnText="Add to Cart"/> -->
  <!-- <formData /> -->

  <!-- <dataForm /> -->
  <!-- <simpleForm />  -->
<!-- <courseGoal /> -->
  <!-- <AddItem /> -->
  <ShopingList />

  <!-- <CountryDropdown /> -->
  <NestedCountry />
  </div>
</template>

<script>
// import dataForm from './components/DataForm.vue';
// import simpleForm from './components/simpleform.vue';
// import HelloWorld from './components/HelloWorld.vue'
// import cityCard from './components/cityCard.vue'
  // import formData from './components/formData.vue'
  // import courseGoal from './components/courseGoal.vue'
  // import AddItem from './components/AddItem.vue'
import ShopingList from './components/ShopingList.vue'
// import CountryDropdown from './components/CountryDropdown.vue'
import NestedCountry from './components/NestesdCountry.vue'

export default {
  name: 'App',
  components: {
    // AddItem,
    ShopingList,
    // CountryDropdown,
    NestedCountry
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
