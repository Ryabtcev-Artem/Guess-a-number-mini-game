<template>
    <div v-show="error=='' && showInput" class="coldOrHot">
        <span v-show="result==''">{{ coldOrHot }}</span>
        <span>{{ result }}</span>
    </div>
    <div v-show="result==''" class="playButton">
        <button @click="checkNumValue" v-show="showInput">Ввести</button>
    </div>
    <div v-show="result!='' && showInput" class="again">
        <button @click="LaunchGameHundred">Играть заново</button>
    </div>
</template>


<script>
export default{
    props:{
        LaunchGameHundred:{
            type:Function,
            required:true,
        },
        error:{
            type:String,
            required:true,
        },
        showInput:{
            type:Boolean,
            required:true,
        },
        numValue:{
            type:Number,
            required:true,
        },
        checkNumValue:{
            type:Function,
            required:true,
        },
        coldOrHot:{
            type:String,
            required:true,
        },
        result:{
            type:String,
            required:true,
        }
    },
}
</script>


<style scoped>
    .again{
        width: 100%;
        display: flex;
        justify-content: center;
        height: 80px;
        margin-top: 30px;
    }
    .again button{
        width: 170px;
        font-size: 28px;
        background-color: #672b79;
        transition: all 0.2s ease;
        color: #fff;
        border: 2px solid #000;
    }
    .again button:hover{
        background-color: #461d53;
        cursor: pointer;
        transform: scale(1.1);
    }
    .playButton{
        width: 100%;
        height: 70px;
        display: flex;
        justify-content: center;
        margin-top: 40px;
    }
    .playButton button{
        width: 200px;
        height: 70px;
        font-size: 28px;
        transition: all 0.2s ease;
        background-color: #20603D;
        color: #fff;
        border: 2px solid #000;
    }
    .playButton button:hover{
        transform: scale(1.1);
        background-color: #195234;
        cursor: pointer;
    }
    .coldOrHot{
        text-align: center;
        margin-top: 30px;
    }
    .coldOrHot span{
        font-size: 20px;
    }
</style>