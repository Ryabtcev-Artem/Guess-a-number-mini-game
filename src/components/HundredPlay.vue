<template>
    <div v-show="!showInput" @click="LaunchGameHundred" class="PlayHundred">
      <img src="https://gas-kvas.com/grafic/uploads/posts/2024-01/gas-kvas-com-p-nadpis-sto-let-na-prozrachnom-fone-35.png" alt="1-100">
      <a>От 1 до 100</a>
    </div>
</template>
  
<script>
export default {
    props:{
    showInput:{
        type:Boolean,
        required:true,},
    LaunchGameHundred:{
        type:Function,
        required:true,
    }
    },
  }
</script>
  
<style scoped>
  .PlayHundred {
    background-color: #006B3C;
    width: 16vw;
    height: 26vh;
    margin-top: 200px;
    display: flex;
    flex-direction: column;
    justify-content: space-around;
    align-items: center;
    border-radius: 20px;
    font-size: 1.6em;
    transition: all 0.3s ease;
}
  
.PlayHundred:hover {
    cursor: pointer;
    transform: scale(1.09);
  }
  
  img {
    width: 14vw;
    height: auto;
    background-color: white;
    border-radius: 18px 18px 0 0;
  }
  </style>
  