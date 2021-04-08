<template>
  <div id="cart">
    <h2>Checkout</h2>
    <h3>Added Lessons</h3>
    <div v-for='(lesson,index) in cart' :key="index">
        {{lesson.title}}
        <button @click="cart.splice(index,1)">x</button>
    </div>
  </div>
</template>
<script>
export default {
name: "Form",
props: ['cart'],
data() {
  return{};
},
};
</script>
