<template>
  <div>
    <h1 class="display-1">The Matrix</h1>
    <h2>Choose your character</h2>
    <div class="chara">
      <Character
        v-for="character in characters"
        v-bind:name="character.name"
        v-bind:role="character.role"
        v-on:character="chooseCharacter"
      />
    </div>
    <h2>And challenge the GUEST STAR</h2>
    <div class="guest">
      <Character
        v-for="character in guestStar"
        v-bind:name="character.name"
        :role="character.role"
      />
    </div>
  </div>
</template>

<script>
import Character from "@/components/Character.vue";
export default {
  components: {
    Character,
  },
  data() {
    return {
      characters: [
        { name: "Morpheus", role: "Leader of the revolution" },
        { name: "Trinity", role: "The white rabbit" },
        { name: "Neo", role: "the choosen one" },
        { name: "Mr. Smith", role: "the bad guy" },
      ],
      guestStar: [{ name: "Chuck Norris", role: "The detroyer of evil" }],
    };
  },
  methods: {
    chooseCharacter(name, role) {
      this.guestStar.push({ name: name, role: role });
    },
  },
};
</script>

<style>
html {
  height: 100%;
  background-color: aquamarine;
}
body {
  margin-top: 10%;
  background-color: aquamarine;
}
.display-1 {
  text-align: center;
}
h2 {
  text-align: center;
  margin: 30px;
}

.chara {
  display: flex;
  justify-content: space-around;
}

.guest {
  /* width: fit-content; */
  display: flex;
  justify-content: center;
  gap: 10px;
}
</style>
