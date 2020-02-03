<template>
  <div>
    <div>
      <button v-on:click="dinamicCmp = 'appA'">A</button>
      <button v-on:click="dinamicCmp = 'appB'">B</button>
      <button v-on:click="dinamicCmp = 'appC'">C</button>
    </div>
    <component v-bind:is="dinamicCmp">
      <h5>Some title</h5>
      <p>
        {{ title }}
      </p>
    </component>
    <app-quote>
      <h5 slot="title">Some title</h5>
      <p slot="content">
        {{ title }}
      </p>
    </app-quote>
  </div>
</template>

<script>
import Quote from "./Quote";
import A from "./A";
import B from "./B";
import C from "./C";

export default {
  data() {
    return {
      dinamicCmp: "appA",
      title:
        "  Lorem, ipsum dolor sit amet consectetur adipisicing elit. At velit dolorexpedita amet. Ad, veritatis obcaecati accusamus deleniti voluptates inminima. Laboriosam odit expedita illum in beatae veniam at similique."
    };
  },
  computed: {
    witch() {
      return this.cmp;
    }
  },
  components: {
    appQuote: Quote,
    appA: A,
    appB: B,
    appC: C
  }
};
</script>
