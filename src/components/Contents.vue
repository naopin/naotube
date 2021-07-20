<template>
  <div class="forms">
    <form action="cgi-bin/example.cgi" method="post">
            <input class="inputkeyword" type="search" name="search" placeholder="キーワードを入力" />
          <input class="inputsearch" type="submit" name="submit" value="検索" />
        <div class="radio">
          <input type="radio" id="allSearch"  v-model="keyword" value="全て"   name="KeywordSearch" checked="checked"/>
          <label for="allSearch">全て</label> 
          <input type="radio" id="movieSearch"  v-model="keyword" value="動画"  name="KeywordSearch"/>
          <label for="movieSearch">動画</label>
          <input type="radio" id="articleSearch"  v-model="keyword" value="記事"  name="KeywordSearch"/>
          <label for="articleSearch">記事</label>
      </div>
    </form>
        <ul id="contents">
      <transition name="fade">
        <li v-if="isActive == 'JavascriptValue'">
          <p class="title">テスト</p>
          <p>JavascriptValue</p>
        </li>
      </transition>
      <transition name="fade">
        <li v-if="isActive == 'VueValue'">
          <p class="title">テスト2</p>
          <p>VueValue</p>
        </li>
      </transition>
      <transition name="fade">
        <li v-if="isActive == 'ReacValue'">
          <p class="title">テスト3</p>
          <p>ReacValue</p>
        </li>
      </transition>
      <transition name="fade">
        <li v-if="isActive == 'AngularValue'">
          <p class="title">テスト3</p>
          <p>AngularValue</p>
        </li>
      </transition>
      <transition name="fade">
        <li v-if="isActive == 'NodeValue'">
          <p class="title">テスト3</p>
          <p>NodeValue</p>
        </li>
      </transition>
      <transition name="fade">
        <li v-if="isActive == 'OtherValue'">
          <p class="title">テスト3</p>
          <p>NOtherValue</p>
        </li>
      </transition>
    </ul>
    <button @click="click()">click</button>
  </div>
</template>
<script>
export default {
  name: "questionary",
  props: ["value"],
  data() {
    return {
      keyword:"",
      isActive: "JavascriptValue",
    };
  },
  methods: {
    click: function() {
    this.isActive = this.value;
    }
  },
  created() {
    console.log(this.value)
  }
};
</script>
<style scoped>
.forms {
  margin: 0 auto;
  width: 35%;
}
form {
  font-size: 1.8em;
  margin-top:2em;
}
.inputkeyword {
  width: 85%;
}
.inputsearch {
  width: 15%;
}
.radio {
  text-align: left;
}
.fade-enter {
  transform: translate(-350px, 0);
  opacity: 0;
}
.fade-enter-to {
  opacity: 1;
}
.fade-enter-active {
  transition: all 1s .3s ease;
}
.fade-leave {
  transform: translate(0, 0);
  opacity: 1;
}
.fade-leave-to {
  transform: translate(200px, 0);
  opacity: 0;
}
.fade-leave-active {
  transition: all .3s 0s ease;
}
#contents {
  padding: 5px 10px;
  box-shadow: 1px 1px 1px 0 rgba(0, 0, 0, 0.2);
  border: 1px solid #eee;
  text-align: center;
}
#contents p {
  font-size: 15px;
  margin: 0;
}
#contents p.title {
  font-size: 16px;
  font-weight: bold;
}
</style>