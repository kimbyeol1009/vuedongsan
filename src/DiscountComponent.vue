<template>
    <div class="container">
      <div class="discount">지금 클릭하면 {{cnt}}% 할인해줌</div>
    </div>
  </template>
  
  <script>
  export default {
    name: "DiscountComponent",
    props : {
        cnt : Number,
    },
  };
  </script>
  
  <style>
  .container {
    display: flex;
    justify-content: center;
    align-items: center;
    margin : 5px;
  }
  
  .discount {
    background-color: rgb(219, 219, 219);
    width: 50%;
    height: 100px;
    border-radius: 20px;
    color: rgb(0, 0, 20);
    font-weight: bold;
    display: flex;
    justify-content: center;
    align-items: center;
  }
  </style>
  