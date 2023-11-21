<script setup>
import { reactive, ref } from "vue";
/*
const obj = ref({ count: 0 });
const state = reactive({ count: 0 });

//Non-primitive values are turned into reactive proxies via reactive()
console.log(obj);
//Object { __v_isShallow: false, dep: undefined, __v_isRef: true, _rawValue: {…}, _value: Proxy }
console.log(obj.value); //Proxy { <target>: {…}, <handler>: {…} }
console.log(state); //Proxy { <target>: {…}, <handler>: {…} }

//Reactive Proxy vs. Original
const raw = {};
const proxy = reactive(raw);
console.log(proxy === raw); //false
// calling reactive() on the same object returns the same proxy
console.log(reactive(raw) === proxy); // true
// calling reactive() on a proxy returns itself
console.log(reactive(proxy) === proxy); // true
*/
/*
const count = ref(0);
const state = reactive({
  count,
});
console.log(count.value); //0
console.log(state.count); // 0
count.value++;
console.log(count.value); //1
console.log(state.count); //1
state.count = 3;
console.log(count.value); //3
console.log(state.count); //3
count.value++;
console.log(count.value); //4
console.log(state.count); //4
const newCount = ref(10);
state.count = newCount;
console.log(count.value); //4
console.log(state.count); //10
*/
/*
const books = reactive([ref("Vue 3 Guide"), ref("Vue 3 Guide intro")]);
// need .value here
console.log(books[0].value); //Vue 3 Guide
console.log(books[1].value); //Vue 3 Guide intro
const map = reactive(
  new Map([
    ["count", ref(0)],
    ["age", ref(20)],
  ])
);
// need .value here
console.log(map.get("count").value); //0
console.log(map.get("age").value); //20
*/
const count = ref(0);
const obj = { id: ref(1) };
// because object.id is not unwrapped when evaluating the expression and remains a ref object
//fix
const { id } = obj;
</script>

<template>
  <!-- <button @click="obj.count++">ref click</button><span>{{ obj.count }}</span>
  <button @click="state.count++">reactive click</button
  ><span>{{ state.count }}</span> -->
  <button @click="count++">ref click</button><span>{{ count }}</span>
  <button @click="id++">reactive click</button><span>{{ obj.id }}</span>
  <span>{{ id }}</span>
</template>

<style scoped></style>
