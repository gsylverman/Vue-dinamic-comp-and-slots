<template>
  <div>
    <div>
      <button v-on:click="dinamicCmp = 'appA'">A</button>
      <button v-on:click="dinamicCmp = 'appB'">B</button>
      <button v-on:click="dinamicCmp = 'appC'">C</button>
    </div>
    <keep-alive>
      <component v-bind:is="dinamicCmp">
        <h5>Some title</h5>
        <p>
          {{ title }}
        </p>
      </component>
    </keep-alive>

    <app-quote>
      <h5 slot="title">Some title</h5>
      <p slot="content">
        {{ title }}
      </p>
    </app-quote>

    <div style="{backgound:grey}">
      <keep-alive>
        <app-y v-if="show"></app-y>
      </keep-alive>

      <app-z v-if="!show"></app-z>
    </div>
    <button v-on:click="show = !show">change</button>
  </div>
</template>

<script>
import Quote from "./Quote";
import A from "./A";
import B from "./B";
import C from "./C";
import Y from "./Y";
import Z from "./Z";

export default {
  data() {
    return {
      show: false,
      dinamicCmp: "",
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
    appC: C,
    appY: Y,
    appZ: Z
  }
};
</script>
