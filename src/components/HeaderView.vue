<template>
  <IndexBar
    :sticky-offset-top="150"
    :index-list="indexList"
  >
    <div v-for="(item, index) in itemList" :key="index">
      <IndexAnchor :index="item.title">
        <Card
          price="2.00"
          :title="item.title"
          desc="Description"
          :thumb="item.img"
        />
      </IndexAnchor>
      <Cell />
    </div>
  </IndexBar>
</template>

<script>
import { IndexBar, IndexAnchor, Card, Cell } from "vant";
import "vant/lib/index.css";

export default {
  name: "HeaderView",
  components: {
    IndexBar,
    IndexAnchor,
    Card,
    Cell,
  },
  data() {
    return {
      indexList: [
        "Sushi",
        "Italian style pizza",
        "Pita/Kebab",
        "Burgers",
        "Fries",
        "Pasta",
        "Lebanese",
        "Thai",
      ],
      itemList: [
        {
          title: "Sushi",
          img: "https://media-cdn.tripadvisor.com/media/photo-s/1c/3d/7a/28/mix.jpg",
        },
        {
          title: "Italian style pizza",
          img: "https://up.quizlet.com/67zk6-hAbJc-256s.jpg",
        },
        {
          title: "Pita/Kebab",
          img: "https://i.pinimg.com/474x/48/51/1e/48511e0adce09fdfcbb938e9d1c51064.jpg",
        },
        {
          title: "Burgers",
          img: "https://redirect.bigoven.com/pics/rs/256/all-american-burgers-4.jpg",
        },
        {
          title: "Fries",
          img: "https://singleteamachi.com:3001/uploads/thumbnails/1627284863153.jpg",
        },
        {
          title: "Pasta",
          img: "https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRL25TjaoDH6quhTxAGSo6ynC1Q7WWx1mhTjg&usqp=CAU",
        },
        {
          title: "Lebanese",
          img: "https://www.isladelivery.com/wp-content/uploads/2022/11/Hummus.jpeg",
        },
        {
          title: "Thai",
          img: "https://i.pinimg.com/736x/c5/57/80/c55780b5bd5402e7e85dc9a795257d46.jpg",
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
::v-deep .van-index-bar__sidebar {
  transform: none;
  top: 0;
  flex-direction: row;
  left: 0;
  box-shadow: 0px 2px 4px rgba(0, 0, 0, 0.1);
  justify-content: center;
  height: 150px;
  align-items: center;
  position: sticky;
  background-color: white;
  margin-bottom: 20px;
}

::v-deep .van-index-bar {
  margin: 0 auto;
  background-color: black;
}

::v-deep .van-index-bar__index {
  font-size: 16px;
}

::v-deep .van-index-bar div {
  max-width: 800px;
}

::v-deep .van-cell {
  margin: 100px 0;
}

::v-deep .van-card {
  border-radius: 10px;
}
</style>
