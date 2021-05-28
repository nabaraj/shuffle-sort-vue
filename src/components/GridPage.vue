<template>
  <div>
    <h5 class="text-center headerText">Shuffle and Sort</h5>
    <div class="d-flex">
      <div class="gridContent d-flex">
        <div
          v-for="item in gridArr"
          :key="item.value"
          :style="{
            backgroundColor: item.color,
          }"
          class="box text-center d-flex"
        >
          <span>{{ item.value }}</span>
        </div>
      </div>
      <div class="sidebar">
        <button @click="shuffleGrid">Shuffle</button>
        <button @click="sortGrid">Sort</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "GridPage",
  data: function () {
    return {
      gridArr: [
        { value: 1, color: "#6f98a8" },
        { value: 2, color: "#2b8ead" },
        { value: 3, color: "#2f454e" },
        { value: 4, color: "#2b8ead" },
        { value: 5, color: "#2f454e" },
        { value: 6, color: "#bfbfbf" },
        { value: 7, color: "#bfbfbf" },
        { value: 8, color: "#6f98a8" },
        { value: 9, color: "#2f454e" },
      ],
    };
  },
  methods: {
    shuffleGrid: function () {
      let arr = this.gridArr;
      let arrLen = arr.length;
      for (let i = 0; i < arrLen; i++) {
        arr.push(arr.splice(Math.floor(Math.random() * arrLen), 1)[0]);
      }
      this.gridArr = arr;
    },
    sortGrid: function () {
      let arr = this.gridArr;
      arr.sort((a, b) => a.value - b.value);
      this.gridArr = arr;
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
.headerText {
  background-color: #333333;
  color: #ffffff;
  margin: 0 0 10px;
  padding: 10px 0;
  @media screen and (min-width: 560px) {
    background-color: transparent;
    color: #333333;
  }
}
.gridContent {
  @media screen and (min-width: 560px) {
    width: 70%;
    order: 1;
  }
  width: 100%;
  order: 2;
  padding: 0 15px;
}
.sidebar {
  width: 100%;
  order: 1;
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: center;
  button {
    flex-basis: 20%;
    margin-bottom: 20px;
    background: #72c3dc;
    padding: 10px 5px;
    margin-left: 2px;
    margin: 0 2px 20px;
    border-radius: 8px;
    border: 0;
    font-size: 16px;
    color: #ffffff;
    font-weight: bold;
    box-shadow: 0px 4px 0 0 #3091b0;
    cursor: pointer;
    &:hover {
      background-color: #65b3cb;
    }
  }
  @media screen and (min-width: 560px) {
    width: 30%;
    order: 2;
    display: block;
    text-align: center;
    button {
      display: block;
      width: 120px;
      margin: 0 auto 20px;
    }
  }
}
.box {
  justify-content: center;
  align-items: center;
  flex-basis: 100%;
  color: #333333;
  padding-left: 5px;
  font-weight: bold;
  margin-bottom: 2px;
  span {
    display: block;
    background-color: #dddddd;
    width: 100%;
    padding: 5px;
  }
  @media screen and (min-width: 560px) {
    min-width: 33.33%;
    flex-basis: 33.33%;
    height: 180px;
    font-size: 35px;
    margin-bottom: 0;
    color: #ffffff;
    span {
      background: transparent;
    }
  }
}
</style>
