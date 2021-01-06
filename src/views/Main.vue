<template>
  <div class="b-totoblock-main b-totoblock__main">
    <pre>{{data}}</pre>
    <Block class="b-totoblock-main__block" title="Заголовок" type="text"></Block>
    <Block class="b-totoblock-main__block" title="Заголовок" type="title"></Block>
  </div>
</template>

<script>
import Block from "@/components/Block.vue";
import axios from "axios";

export default {
  components: {
    Block
  },
  data() {
    return {
      data: []
    };
  },
  mounted() {
    this.startRequest();
  },
  methods: {
    startRequest() {
      axios
        .get("./store/example.json")
        .then(response => {
          this.data = response.data[0];
        })
        .catch(error => {
          throw new Error(error);
        });
    }
  }
};
</script>