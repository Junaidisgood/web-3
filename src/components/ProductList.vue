
<template>
  <main>
    <div class="row">
      <div class="col-3 mb-3" v-for="lesson in lessons" :key="lesson.id">
        <div class="card">
          <img v-bind:src="lesson.image" style="height: 200px;">
          <div class="card-body">
            <h5 class="card-title" v-text="lesson.title"></h5>
            <p>Price: {{lesson.price}}</p>
            <p>Number of spaces: {{lesson.availableInventory - cartItemCount}}</p>
            <button v-on:click="addToCart(lesson)" class="btn btn-block btn-info">
              Add to cart
            </button>
          </div>
        </div>
      </div>
    </div>
  </main>
</template>
<script>
  export default {
    name: "LessonList",
    data() {
      return {
        lessons: [
        {
          id: 1001,
          title: "English",
          price: 120,
          image: "images/english.jpg",
          availableInventory: 10,
          rating: 2,
        },
        {
          id: 1002,
          title: "Math",
          price: 250,
          image: "images/math.jpg",
          availableInventory: 7,
          rating: 5,
        },
        {
          id: 1002,
          title: "History",
          price: 150,
          image: "images/history.jpg",
          availableInventory: 5,
          rating: 2,
        },
        {
          id: 1002,
          title: "Science",
          price: 150,
          image: "images/science.jpg",
          availableInventory: 9,
          rating: 3,
        },
        ],
      };
    },
    methods: {
      addToCart(lesson) {
        console.log ('Added lesson', lesson.id);
        this.$emit('addProduct', lesson);
      },
      
    },
  };
</script>
