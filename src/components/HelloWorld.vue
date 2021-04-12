<template>
  <div class="hello">
    <ol class="my-5 mx-auto" v-if="list.length > 0">
      <li v-for="(el, i) in list" :key="i">
        {{el.tareas}}
      </li>
    </ol>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  props: {
    list: {
      type: Array,
      default: () => []
    }
  },
  methods:{
 //
  } 

};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
  ol {
    font-family: 'Nanum Pen Script', cursive;
    display: flex;
    flex-direction: column;
    width: 60%;
    font-size: 45px;
    align-items: center;
  }
</style>
