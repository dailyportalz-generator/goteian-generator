<!-- src/App.vue -->
<template>
  <div id="app">
    <template>
      <Question1 key="start" v-if="step === 0" @start="handleStart"/>
      <SlidePreviewTitle key="slidetitle" v-if="step >= 1 && step <= 5"/>
      <Slide1
        key="slide1"
        v-if="step >= 1"
        :anata="this.questions.anata"
        :aite="this.questions.aite"
        :text3a="this.questions.text3a"
        :hiduke="this.questions.hiduke"
      />
      <Question2 key="question2" v-if="step === 1" @start="handleStart2"/>
      <Slide2
        key="slide2"
        v-if="step >= 2"
        :aite="this.questions.aite"
        :text4="this.questions.text4"
      />
      <Question3 key="question3" v-if="step === 2" @start="handleStart3"/>
      <Slide3
        key="slide3"
        v-if="step >= 3"
        :text5a="this.questions.text5a"
        :anata="this.questions.anata"
        :text5b="this.questions.text5b"
        :text3="this.questions.text3"
      />
      <Question4 key="question4" v-if="step === 3" @start="handleStart4"/>
      <Slide4
        key="slide4"
        v-if="step >= 4"
        :anata="this.questions.anata"
        :text6="this.questions.text6"
      />
      <Question5 key="question5" v-if="step === 4" @start="handleStart5"/>
      <Slide5 key="slide5" v-if="step >= 5" :text7="this.questions.text7"/>
      <Question6 key="question6" v-if="step === 5" @start="handleStart6"/>
      <Slide6
        key="slide6"
        v-if="step >= 6"
        :text8="this.questions.text8"
        :aite="this.questions.aite"
        :text3="this.questions.text3"
        :anata="this.questions.anata"
      />
      <Question7 key="question7" v-if="step === 6" />
      <TwitterShare key="twittershare" v-if="step === 6" :questions="this.questions"
      />
    </template>
  </div>
</template>

<script>
import moment from "moment";
import { parse } from "querystring";

import SlidePreviewTitle from "./components/SlidePreviewTitle.vue";
import Slide1 from "./components/Slide1.vue";
import Slide2 from "./components/Slide2.vue";
import Slide3 from "./components/Slide3.vue";
import Slide4 from "./components/Slide4.vue";
import Slide5 from "./components/Slide5.vue";
import Slide6 from "./components/Slide6.vue";
import Question1 from "./components/Question1.vue";
import Question2 from "./components/Question2.vue";
import Question3 from "./components/Question3.vue";
import Question4 from "./components/Question4.vue";
import Question5 from "./components/Question5.vue";
import Question6 from "./components/Question6.vue";
import Question7 from "./components/Question7.vue";
import TwitterShare from "./components/TwitterShare.vue";

export default {
  name: "app",
  data() {
    return {
      step: 0,
      questions: {
        aite: "",
        anata: "",
        naiyo: 1,
        text3: "",
        text3a: "",
        hiduke: "" + moment(new Date()).format("YYYY年M月DD日"),
        text4: "",
        text5a: "",
        text5b: "",
        text6: "",
        text7: 1,
        text8: "",

      }
    };
  },
  components: {
    Slide1,
    Slide2,
    Slide3,
    Slide4,
    Slide5,
    Slide6,
    SlidePreviewTitle,
    Question1,
    Question2,
    Question3,
    Question4,
    Question5,
    Question6,
    Question7,
    TwitterShare
  },
  mounted() {
    const params = parse(location.search.replace("?", ""));
    const isValid = ["name", "title", "q1", "q2", "q3", "q4", "q5", "q6"].every(
      val => {
        if (!params[val]) {
          return false;
        }
        if (val != "name" && parseInt(params[val]) < 1) {
          return false;
        }
        return true;
      }
    );
    if (isValid) {
      const questions = {
        name: params.name,
        title: parseInt(params.title),
        q1: parseInt(params.q1),
        q2: parseInt(params.q2),
        q3: parseInt(params.q3),
        q4: parseInt(params.q4),
        q5: parseInt(params.q5),
        q6: parseInt(params.q6)
      };
      this.questions = questions;
      this.step = 7;
    }
  },
  methods: {
    handleNext() {
      this.step++;
    },
    handleStart(startData) {
      this.questions.naiyo = startData.naiyo;
      this.questions.anata = startData.anata;
      this.questions.aite = startData.aite;
      this.questions.text3 = this.text3List[startData.naiyo - 1];
      this.questions.text3a = this.text3aList[startData.naiyo - 1];
      this.handleNext();
    },
    handleStart2(startData) {
      this.questions.text4 = this.text4List[startData.naiyo - 1];
      this.handleNext();
    },
    handleStart3(startData) {
      this.questions.text5a = this.text5aList[startData.naiyo - 1];
      let text5bList = this.text5bList(this.questions.naiyo);
      this.questions.text5b = text5bList[startData.naiyo - 1];
      this.handleNext();
    },
    handleStart4(startData) {
      this.questions.text6 = this.text6List[startData.naiyo - 1];
      this.handleNext();
    },
    handleStart5(startData) {
      this.questions.text7 = startData.naiyo;
      this.handleNext();
    },
    handleStart6(startData) {
      console.log(startData.naiyo);
      this.questions.text8 = this.text8List[startData.naiyo - 1];
      this.handleNext();
    },
    text5bList(naiyo) {
      if (naiyo === 1) {
        return [
          "の採用をご提案します",
          "の採用がお得です！ 12時までの採用に限りもうひとり（弟）ついてきます",
          "の採用をお願いします。死ぬ気でがんばります。",
          "の採用がナウい"
        ];
      } else if (naiyo === 2) {
        return [
          "との結婚によるシナジーをご提案します",
          "との結婚がオススメです。いまならエコポイントもついてきます",
          "と結婚してください。スクワット300回の実力をお確かめください",
          "との結婚がおすすめなのでR"
        ];
      } else if (naiyo === 3) {
        return [
          "に弟子入りしてさらなるインセンティブ拡大をご提案します",
          "への弟子入りが絶対にお得です。いまなら自立式モップがついてきます",
          "への弟子入りしてください。さみしいんです。男に二言はありません",
          "に弟子入りするのがナウ！"
        ];
      } else {
        return [
          "のパン買ってきて",
          "のためにパンを買ってきて損はありません。メタボリックの解消に！",
          "のパン買ってこい",
          "のパンを買ってくるのがE感じ"
        ];
      }
    }
  },

  computed: {
    text3List() {
      return ["就職", "結婚", "弟子", "パン"];
    },
    text3aList() {
      return [
        "採用のご提案",
        "結婚のご提案",
        "弟子入りのご提案",
        "パン買ってきてのご提案"
      ];
    },
    text4List() {
      return [
        "エスタブリッシュメント",
        "ホスピタリティ",
        "モラル厳守のスタンス",
        "ビジュアル訴求"
      ];
    },
    text5aList() {
      return [
        "クラウドコンピューティングないまこそ、",
        "比べてみてください。",
        "私を信じて",
        "いま"
      ];
    },
    text6List() {
      return ["我慢強さ", "愛想笑い", "ごはんを食べるはやさ", "謙虚さ"];
    },
    text7List() {
      return ["7_1.jpg", "7_2.jpg", "7_3.jpg", "7_4.jpg"];
    },
    text8List() {
      return ["本日", "来週", "本年度4Q", "時期未定"];
    },
  }
};
</script>
<style>
* {
  box-sizing: border-box;
}

#app {
  font-family: sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #000;
  max-width: 640px;
  font-size: 12px;
  padding: 0 50px;
}
.slide {
    font-family: "ＭＳ Ｐゴシック", Osaka, "ヒラギノ角ゴ Pro W3", "メイリオ";
}
</style>