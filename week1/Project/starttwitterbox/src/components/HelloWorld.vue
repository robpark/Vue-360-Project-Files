<template>
  <div>
    <h1>Project Twitter Box Client</h1>

    <div class="box">
      <div>
        <textarea type="text" v-model="tweet" @input="updateRemaining" />
        <button v-on:click="clicked">Submit</button>
      </div>
      <div class="remaining">{{remaining}}</div>
    </div>

    <div>
      <ul v-for="tweet in tweets" :key="tweet">
        <li>{{ tweet }}</li>
      </ul>
    </div>
  </div>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    const ALLOWED_SIZE = 280;
    return {
      allowedSize: ALLOWED_SIZE,
      remaining: ALLOWED_SIZE,
      tweet: "",
      tweets: []
    };
  },
  methods: {
    clicked() {
      this.tweets.unshift(this.tweet);
      this.tweet = "";
      this.remaining = this.allowedSize;
    },
    updateRemaining(event) {
      let newRemaining = this.allowedSize - event.target.value.length;
      if (newRemaining < 0) {
        this.tweet = this.tweet.substring(0, this.allowedSize);
      } else {
        this.remaining = newRemaining;
      }
    }
  },
  props: {
    msg: String
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.box {
  width: 33%;
  background-color: #b8dcdc;
  height: 100px;
  margin: 0 auto;
  display: flex;
  justify-content: center;
  align-items: center;
  box-shadow: 0 20px 25px -5px rgba(0, 0, 0, 0.1),
  0 10px 10px -5px rgba(0, 0, 0, 0.04);
}

.remaining {
  margin: 20px;
}

button {
  margin-left: 10px;
}

li {
  list-style: none;
}
</style>
