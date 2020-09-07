<template>
  <div class="home">
    <p>{{greetText}}</p>
    <p>挨拶した回数：{{count}}回</p>
    <p v-if="isRegulars">いつもありがとうございます</p>
    <p>
      <MyButton :greet="greetText" @click="onMyButtonClicked"></MyButton>
    </p>
    <p>
      <ResetButton initialValue="Hello" v-model="greetText"></ResetButton>
    </p>
  </div>
</template>

<script lang = "ts">
// @ is an alias to /src
import {Component,Vue, Watch} from "vue-property-decorator";
import MyButton from "@/components/myButton.vue";
import ResetButton from "@/components/ResetButton.vue";

@Component({
  components:{
    MyButton,
    ResetButton,
  }
})

export default class Home extends Vue{
  public greetText = "hello World";
  private count = 0;

  public get isRegulars(): boolean{
    return this.count >= 5;
  }

  @Watch("count")
  public countChanged(){
    if(this.count == 5){
        alert("常連になりました");
    }
  }

  public onMyButtonClicked(count: number){
    this.count = count;
    this.greetText = "こんにちは";
  }
}
</script>
