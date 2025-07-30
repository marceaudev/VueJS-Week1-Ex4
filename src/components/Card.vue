<script setup>
import AnimalsInfos from './AnimalsInfos.vue'
// Déclaration de la props qui contient les informations d'un animal
const props = defineProps({
  animalInfos: Object
})
</script>

<template>
  <div :class="['card', { adopted: animalInfos.alreadyAdopted }]">
    <AnimalsInfos :animalInfos="animalInfos" />
    <p class="description">{{ animalInfos.description }}</p>
  </div>
</template>

<style scoped>
.card {
  background-color: var(--main-white);
  padding: 15px;
  border-radius: 5px;
  width: calc((100% - 15px) / 2);
  display: flex;
  gap: 10px;
  box-shadow: 0px 0px 7px var(--main-purple);
}

.adopted {
  opacity: 0.5;
}

.card > div {
  width: 150px;
  display: flex;
  flex-direction: column;
  gap: 10px;
}
.description {
  flex: 1;
}

.card p {
  color: var(--main-blue);
}

@media (max-width: 900px) {
  .card {
    width: 100%;
  }
}

@media (max-width: 500px) {
  .card {
    flex-direction: column;
  }
}
</style>
