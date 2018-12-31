<template>
  <div>
<vs-row class="title">
  <vs-col vs-w="12">
    <h1 class="P1">Fake<span class="P2">MD</span></h1>
  </vs-col>
</vs-row>
<br />
<vs-row>
  <vs-col vs-offset="3" vs-type="flex" vs-justify="center" vs-align="center" vs-w="5" vs-xs="6">
    <vs-input size="large" placeholder="Why can't you practice?" v-model="text_input" @keyup.enter="submit"/>
  </vs-col>
  <vs-col vs-xs="12" vs-w="1" vs-type="flex" vs-justify="center" vs-align="center">
    <vs-button v-if="text_input"  color="primary" type="filled" icon="search" @click="submit">Get Help</vs-button>
    <vs-button v-else disabled  color="primary" type="filled" icon="search" @click="submit">Get Help</vs-button>
  </vs-col>
</vs-row>
<br />
<br />
<vs-row>
  <vs-col vs-w="12">
    <h3>
      {{output_text}}
    </h3>
  </vs-col>
</vs-row>

  </div>
</template>

<script>
export default {
  name: 'Main',
  data() {
    return {
      text_input: '',
      output_text: '',
      listOfOKs: [
        `You'll be okay.`,
        `I think you'll survive.`,
        `Suck it up.`,
        `You can practice.`,
        `Get out there.`,
        `Yeah, good one... NO.`,
        `Ask again.`,
        `Try asking again`,
        `What does that even mean??`
      ]
    };
  },
  methods: {
    submit() {
      if (this.text_input) {
        this.output_text = this.listOfOKs[
          Math.floor(Math.random() * this.listOfOKs.length)
        ];
      }
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
.title {
  font-family: 'Exo 2', sans-serif;
  font-size: 40px;
}
.title .P1 {
  font-weight: 200;
}
.title .P2 {
  font-weight: 400;
}
.vs-con-input-label {
  width: -webkit-fill-available !important;
}
.vs-button--text {
  font-size: 15px;
}
</style>
