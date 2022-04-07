<template>
<div>
    <div class="button">
        <button class="btn-button" @click="isActive = !isActive">button</button>
    </div>
    <div class="content">
        <div class="box-left">
             <div class='text-danger' :class='{active: isActive}'>abcdef</div>
        <div :style="{ color: color, fontSize: FontSize + 'px'}">change style</div>
        </div>
        <div class="box-right">
            <div v-if="isActive"> xyz</div>
        <div v-else> Oh no</div>
        <div v-show="isActive"> show show</div>
        </div>
    </div>
</div>
  
</template>

<script>
export default {
    data() {
        return {
            isActive: false,
            color: 'blue',
            FontSize: 30
        }
    }
}
</script>

<style>
.text-danger {
    color: red;
}
.btn-button {
    margin: 0 auto;
    padding: 10px 20px;
    color:blue;
    background: white;
    border-radius: 5px;
    border: 1px solid blue;
    box-shadow: 0 0 5px;
}
.btn-button:hover {
    color:yellowgreen;
    background: blue;
    transform: translateY(2px);
    
}
.button{
    width:100%;
    text-align: center;
    margin: 20px 0;
}
.content {
    text-align: center;
    display: flex;
}
.box-left, .box-right{
    width:50%;
}
</style>