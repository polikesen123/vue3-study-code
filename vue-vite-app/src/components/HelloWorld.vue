
<template>
  <div>
    <h1>{{ msg }}</h1>
    <!-- composition -->
    <Composition></Composition>
    <!-- Teleport  ModalButton-->
    <ModalButton></ModalButton>
    <Emits @my-click="onClick"></Emits>
  </div>
</template>

<script>
import Composition from "./Composition.vue";
import ModalButton from "./ModalButton.vue";
import Emits from "./Emits.vue";
export default {
  name: "HelloWorld",
  props: {
    msg: String
  },
  data() {
    return {
      count: 0
    };
  },
  components: {
    Composition,
    ModalButton,
    Emits
  },
  methods: {
    onClick() {
      console.log("click me!");
    }
  }
};
</script>
