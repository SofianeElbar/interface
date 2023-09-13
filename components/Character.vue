<template>
    <button @click="$emit('character', name, role)" class="card">
      <div class="card-body">
        <h5 class="card-title">{{ name }}</h5>
        <p class="card-text">{{ role }}</p>
      </div>
     
    </button>
   
</template>

<script>
export default {
  name: "Character",
  props: ["name", "role"],
};
</script>

