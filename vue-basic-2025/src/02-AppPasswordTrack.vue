<script setup>
import {ref,computed} from 'vue';


const textMsg = ref('');



const lengthOfText = computed(()=>{
  return textMsg.value.length;
});

const warningCondition = computed(()=>{
  return textMsg.value.length>10;
});

const weakCondiiton = computed(()=>{
  return textMsg.value.length<3;
});

const goodCondition = computed(()=>{
  return textMsg.value.length>=3&&textMsg.value.length<=10;
})

</script>

<template>
  <div class="text-msg">
    <div class="icons">
      <div :class="['redBox',{activeBox:weakCondiiton}]"></div>
      <p>Weak</p>
      <div :class="['greenBox',{activeBox:goodCondition}]"></div>
      <p>Good</p>
      <div :class="['yellowBox',{activeBox:warningCondition}]"></div>
      <p>Warning</p>
    </div>
    <div>
      <input v-model="textMsg" type="text" placeholder="Enter a text...">
      <p :class="{good: goodCondition,weak:weakCondiiton,warning:warningCondition}">length: {{ lengthOfText }}</p>
    </div>
  </div>
</template>

<style scoped>

.text-msg{
  background-color: rgb(5, 53, 107);
  width: 400px;
  height: 200px;
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  border-radius: 20px;
  box-shadow: 2px 2px 3px 2px rgba(0, 0, 0, 0.3);
}

.text-msg input{
  padding: 10px 15px;
  border-radius: 5px;
  outline: 0;
  font-size: 16px;
  border: 1px solid rgb(103, 4, 4);
}

.good{
  color: green;
}

.warning{
  color: yellow;
}

.weak{
  color: red;
}


.icons{
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.redBox{
  background: red;
  width: 10px;
  height: 10px;
}

.greenBox{
  background: rgb(14, 141, 3);
  width: 10px;
  height: 10px;
  margin-left: 5px;
}

.yellowBox{
  background: rgb(188, 208, 5);
  width: 10px;
  height: 10px;
  margin-left: 5px;
}

.activeBox {
  box-shadow: 0 0 5px white;
  border: 2px solid white;
}




</style>