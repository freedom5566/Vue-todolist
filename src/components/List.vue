<!--HTML-->
<template>
    <div class="view">
        <h1 class="title">{{ title }}</h1>
        <input v-model="newStr" @keyup.enter="addData"/>
        <ul>
            <li v-for="item in items" v-bind:class="{finesh:item.isFineshed}" @click="toggleFinish(item)">
                {{ item.text }}
            </li>
        </ul>
    </div>
</template>
<!--JS-->
<script>
  export default {
    name: "List",
    data() {
      return {
        title: "TodoList",
        items: [
          //     {
          //
          //     text: "run",
          //     isFineshed: true
          //   },
          //   {
          //     text: "kobe",
          //     isFineshed: false
          //   },
        ],
        newStr: ""
      }
    },
    methods: {
      toggleFinish: function(item) {
        item.isFineshed = !item.isFineshed;
      },
      addData: function() {
        // console.log(this.newStr);
        this.items.push({
          text: this.newStr,
          isFineshed: false

        }, );
        this.$emit("myMsg", this.newStr);
        //clear
        this.newStr = "";
      }
    }


  }
</script>
<!--CSS-->
<style>
  .view {
    width: 400px;
    border: 1px solid gray;
    margin: 20px auto;
  }

  .view .title {
    border-bottom: 1px solid gray;
  }

  .view ul li {
    margin: 10px 0;
    list-style: none;
  }

  .finesh {
    color: gray;
    text-decoration: line-through;
  }
</style>
