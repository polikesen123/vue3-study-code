<template>
  <p>{{ counter }}</p>
  <p>{{ doubleCounter }}</p>
  <p ref="desc"></p>
</template>

<script>
import {
  reactive,
  computed,
  ref, //声明一个单值的变量
  onMounted,
  onUnmounted,
  watch,
  toRefs,
  getCurrentInstance
} from "vue";
export default {
  setup() {
    let { counter, doubleCounter } = useCounter();

    //其他数据
    const msg2 = ref("some message");

    //使用元素引用
    const desc = ref(null);

    //侦听器
    watch(counter, (val, oldVal) => {
      const p = desc.value;
      p.textContent = `counter change from ${oldVal} to ${val}`;
    });
    // console.log(this);

    // const instance = getCurrentInstance();
    // console.log(instance);
    return {
      counter,
      doubleCounter,
      msg2,
      desc
    };
  }
};
function useCounter() {
  const data = reactive({
    counter: 1,
    doubleCounter: computed(() => data.counter * 2)
  });
  let timer;
  onMounted(() => {
    timer = setInterval(() => {
      data.counter++;
    }, 1000);
  });
  onUnmounted(() => {
    clearInterval(timer);
  });
  return toRefs(data);
}
</script>

<style scoped lang="">
</style>
