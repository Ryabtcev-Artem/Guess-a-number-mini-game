<template>
  <TheHead />
  <div class="PlayButtons">
    <HundredPlay :LaunchGameHundred="LaunchGameHundred" :showInput="showInput"/>
  </div>
  <GameBar :showInput="showInput" v-model="numValue"/>
  <div v-show="error!=''" class="error">
    <span>{{ error }}</span>
  </div>
  <PlayButton :LaunchGameHundred="LaunchGameHundred" :result="result" :error="error" :coldOrHot="coldOrHot" :checkNumValue="checkNumValue" :showInput="showInput" :numValue="numValue"/>
</template>

<script>
import TheHead from "./components/TheHeader.vue";
import HundredPlay from "./components/HundredPlay.vue";
import GameBar from "./components/ActingGameHundred.vue";
import PlayButton from "./components/PlayButton.vue"
export default {
  components: {
    TheHead,
    HundredPlay,
    GameBar,
    PlayButton,
  },
  data() {
    return {
      showInput: false,
      numValue: 0,
      error: '',
      maxValue: 100,
      theValue:Math.round(Math.random()*100),
      coldOrHot:'',
      cold:['Так не пойдет! Бери побольше.','Скромно как-то... давай-ка побольше!',
      'Ну, это явно недостаточно. Может, прибавим?',
      "Не дотянул! Поставь что-нибудь побольше.","Маловато будет, попробуй ещё раз!"
      ],
      hot:["Перебор, дружище! Сбавь обороты.","Слишком щедро! Попробуй поменьше.",
      "Это чересчур. Давай что-нибудь поскромнее.",
      "Куда так много?","Великовато, у нас тут не аукцион."
      ],
      randomPhrase:0,
      phraseResult:["Эй, кто тут гений? Тебе пора идти в казино.","Дамы и господа, перед нами новый чемпион мира по угадыванию чисел! Аплодисменты!",
        "Поздравляю! Ты разблокировал секретную суперспособность: угадывание чисел. Теперь официально — ты вне матрицы!",
        "ЧТОООО? Как ты это вычислил, шаман с калькулятором?","Ты угадал! Но будь осторожен, такие навыки привлекают внимание спецслужб!"
      ],
      result:"",
    };
  },
  methods: {
    LaunchGameHundred() {
      this.showInput = !this.showInput;
      this.coldOrHot='';
      this.result='';
      this.theValue=Math.round(Math.random()*100);
      this.numValue=0;
    },
    checkNumValue() {
      if (this.numValue > 100 || this.numValue <= 0) {
        this.error = "Число не входит в диапазон";
        return}
      this.error=''
      this.randomPhrase=Math.round(Math.random()*4)
      if (this.numValue>this.theValue){
        this.coldOrHot=this.hot[this.randomPhrase]
      }
      else if (this.numValue<this.theValue){
        this.coldOrHot=this.cold[this.randomPhrase]
      }
      else{
        this.result=this.phraseResult[this.randomPhrase]
      }
  },
  }
}
</script>

<style scoped>
  .PlayButtons {
    display: flex;
    justify-content: center;
  }
  .error{
    width: 100%;
    text-align: center;
    margin-top: 30px;
  }
  span{
    color: red;
    font-size: 24px;
  }
</style>

