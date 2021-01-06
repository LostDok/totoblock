<template>
  <div class="b-totoblock-block">
    <div class="b-totoblock-block__title">{{title}}. Тип: {{type}}</div>

    <BText class="b-totoblock-block__inside" v-if="type === 'text'"></BText>
    <BTitle class="b-totoblock-block__inside" v-if="type === 'title'"></BTitle>
  </div>
</template>

<script>
import BText from "@/components/fields/Text";
import BTitle from "@/components/fields/Title";

export default {
  props: ["title", "type"],
  components: {
    BText,
    BTitle
  },
  data() {
    return {};
  }
};
</script>