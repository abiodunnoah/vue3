<template>
  <div class="m-auto">
    <h1 class="text-center text-2xl">Dc Heroes {{ herosCount }}</h1>
    <ul>
      <li
        class="flex justify-between"
        v-for="(hero, index) in dcHeros"
        :key="hero.name"
      >
        <div>
          {{ hero.name }}
        </div>
        <button v-on:click="remove(index)">x</button>
      </li>
    </ul>

    <form @submit.prevent="addHero">
      <input type="text" v-model="newHero" placeholder="Type Hero Name Here" />
      <button
        class="border rounded bg-gradient-to-r from-red-700 to-pink-500 text-white py-1 px-3"
        type="submit"
      >
        Add Hero
      </button>
    </form>
  </div>
</template>

<script>
export default {
  data() {
    return {
      newHero: "",
      dcHeros: [
        { name: "SuperGirl" },
        { name: "Flash" },
        { name: "BatMan" },
        { name: "Arrow" },
        { name: "SuperMan" },
      ],
    };
  },
  computed: {
    herosCount() {
      return this.dcHeros.length;
    },
  },

  methods: {
    addHero() {
      if (this.newHero != "") {
        this.dcHeros.unshift({ name: this.newHero });
        this.newHero = "";
      }
    },
    remove(index) {
      this.dcHeros = this.dcHeros.filter((hero, i) => i != index);
    },
  },
};
</script>

<style></style>
