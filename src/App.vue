<template>
  <h1>welcome vue shop</h1>
  <h3>product list</h3>
  <ul>
    <!-- <li v-for="(product, id) in products" :key="id">
      제품명 : {{ product.productName }} | 가격: {{product.price}} | 생산연도 {{product.date}}
    </li> -->
    <li v-for="(post, sq) in posts" :key="sq">
      제품명 : {{ post.title }} | 가격: {{post.id}} | 생산연도 {{post.body}}
    </li>
  </ul>
  <button @click="buttonClicked">Click</button>
</template>

<script>
import axios from 'axios'

export default {
  name: 'App',
  created(){
    console.log("created");
    axios.get('https://jsonplaceholder.typicode.com/posts')
      .then(result => {
        this.posts = result.data;
        //console.log(result.data);
      });
  },
  mounted(){
    console.log("mounted");
  },
  updated(){
    console.log("updated");
  },
  methods:{
    buttonClicked(){
      console.log("button clicked..");
      axios.get('https://jsonplaceholder.typicode.com/posts')
        .then(result => {
          this.posts = result.data;
          //console.log(result.data);
        });
    },
  },
  data(){
    return{
      /*products:[
        {
          productName: 'iPhone13',
          price: 140000,
          date: 2021,
        },
        {
          productName: 'galaxi',
          price: 134000,
          date: 2021,
        },
        {
          productName: 'motorola',
          price: 16000,
          date: 2021,
        },
      ],*/
      posts: [],
    }
  }
}
</script>

<style>
</style>
