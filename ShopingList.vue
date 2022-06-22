<template>
  <div class="container">
    <div class="row">
      <div class="col-8">
        <div class="row">
          <div class="card col-md-3" v-for="(image, idx) in images" :key="idx">
            <img
              class="card-img-top"
              :src="require('../assets/' + image.filename)"
              alt="Card image"
            />
            <div class="card-body">
              <h4 class="card-title">{{ image.title }}</h4>
              <p class="card-text">{{ image.description }}</p>
              <a href="#" class="btn btn-primary"  v-on:click = "counter++"
                >Add to Cart ({{ image.price }})</a
              >
            </div>
          </div>
        </div>
      </div>
      <div class="col-4">
        <table class="table m-4">
          <tr class="">
            <td class="font-weight-bold">Title</td>
            <td>qty</td>
            <td>unit price</td>

            <td>total</td>
          </tr>
          <tr
            v-for="(image, idx) in images"
            :key="idx"
            v-show="image.rating > 0"
          >
            <td>{{ image.title }}</td>
            <td>
                <!-- {{counter}} -->
              <input  
                class="form-control"
                style="width: 100px"
                type="text"
                v-model = "counter"
              />
                
             <!-- v-model="image.rating"  line 43 -->

            </td>
            <td>{{ image.price }}</td>

            <td>{{ Math.ceil(counter * image.price) }}</td>
          </tr>
        </table>

        <h3>Grand Total: {{  total }}</h3>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "ShopingList",
  data() {
    return {
        counter:1,
      images: [
        {
          title: "Brown eggs",
          type: "dairy",
          description: "Raw organic brown eggs in a basket",
          filename: "5.jpg",
          height: 600,
          width: 400,
          price: 28.5,
          rating: 4,
        counter: 1,
        
        },
        {
          title: "Sweet fresh stawberry",
          type: "fruit",
          description: "Sweet fresh stawberry on the wooden table",
          filename: "5.jpg",
          height: 450,
          width: 299,
          price: 29.45,
          rating: 4,
        },
        {
          title: "Brown eggs",
          type: "dairy",
          description: "Raw organic brown eggs in a basket",
          filename: "5.jpg",
          height: 600,
          width: 400,
          price: 28.1,
          rating: 4,
          counter: 1,
        },
        {
          title: "Sweet fresh stawberry",
          type: "fruit",
          description: "Sweet fresh stawberry on the wooden table",
          filename: "5.jpg",
          height: 450,
          width: 299,
          price: 29.45,
          rating: 4,
          counter: 1,
        },
        
      ],
      total: 0,
    };
  },
  created() {
    this.calculateTotal();
  },
  methods: {
    calculateTotal() {
      this.total = 0;
      this.images.forEach((x) => {
        this.total = this.total + Math.ceil(this.counter * x.price);
      });
    },
  },
  watch: {
    images: {
      handler() {
        this.calculateTotal();
      },
      deep: true,
    },
  },
};
</script>
