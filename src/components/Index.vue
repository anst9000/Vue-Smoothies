<template>
  <div class="index container">
    <div class="card" v-for="smoothie in smoothies" :key="smoothie.id">
      <div class="card-content">
        <i class="material-icons delete" @click="deleteSmoothie(smoothie.id)"
          >delete</i
        >
        <h2 class="indigo-text">{{ smoothie.title }}</h2>
        <ul class="ingredients">
          <li v-for="(ing, index) in smoothie.ingredients" :key="index">
            <span class="chip">{{ ing }}</span>
          </li>
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "Index",
  data() {
    return {
      smoothies: [
        {
          title: "Ninja Brew",
          slug: "ninja-brew",
          ingredients: ["bananas", "coffee", "milk"],
          id: "1"
        },
        {
          title: "Morning Mood",
          slug: "morning-mood",
          ingredients: ["mango", "lime", "juice"],
          id: "2"
        },
        {
          title: "Ninja Brew",
          slug: "ninja-brew",
          ingredients: ["bananas", "coffee", "milk"],
          id: "3"
        },
        {
          title: "Morning Mood",
          slug: "morning-mood",
          ingredients: ["mango", "lime", "juice"],
          id: "4"
        }
      ]
    };
  },
  methods: {
    deleteSmoothie(id) {
      this.smoothies = this.smoothies.filter(smoothie => {
        return smoothie.id !== id;
      });
    }
  }
};

// function convertToSlug(Text)
// {
//     return Text
//         .toLowerCase()
//         .replace(/ /g,'-')
//         .replace(/[^\w-]+/g,'')
//         ;
// }
</script>

<style>
.index {
  display: grid;
  grid-template-columns: 1fr 1fr 1fr;
  grid-gap: 30px;
  margin-top: 60px;
}
.index h2 {
  font-size: 1.8em;
  text-align: center;
  margin-top: 0;
}
.index .ingredients {
  margin: 30px auto;
}
.index .ingredients li {
  display: inline-block;
}
.index .delete {
  position: absolute;
  top: 6px;
  right: 6px;
  cursor: pointer;
  color: #aaa;
  font-size: 1.5em;
  transition: scale 500ms ease-out, color 500ms ease-out;
}
.index .delete:hover {
  color: #777;
}
.index .delete:active {
  transform: scale(0.8);
}
</style>
