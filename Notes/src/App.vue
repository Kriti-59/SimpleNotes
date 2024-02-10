<script setup>
import { ref } from "vue";

const showModal = ref(false);
const newNote = ref("");
const notes = ref([]);

function getRandomColor() {
  return "hsl(" + Math.random() * 360 + ", 100%, 75%)";
}

const addNote = () => {
  notes.value.push({
    id: Math.floor(Math.random() * 10000000),
    text: newNote.value,
    date: new Date(),
    backgroundColor: getRandomColor()
  });
  showModal.value = false;
  newNote.value = "";
};
</script>

<template>

<main> 
  <div v-if= "showModal" class="overlay">
    <div class="modal"> 
      <textarea v-model= "newNote" name="note" id="note" cols="30" rows="10"></textarea>
      <button @click="addNote">Add Note</button>
      <button class="close" @click = "showModal = false">Close</button>
    </div>
  </div>
  <div class ="container"> 
    <header>
      <h1> Notes </h1>
      <button @click = "showModal = true">+</button>
    </header>

    <div class="card-container">
      <div v-for="note in notes" :key = "note.id" 
      class="card" :style="{ backgroundColor: note.backgroundColor }">
        <p class="main-text">{{ note.text }}</p>
        <p class="date"> {{ note.date.toLocaleDateString("en-US") }}</p>
    </div>

    </div>

  </div>

</main>



</template>


<style scoped >

main{
  height: 100vh;
  width: 100vw;
}

.container{
  max-width: 1000px;
  padding: 10px;
  margin: auto 0;
}

header{
  display: flex;
  justify-content: space-between;
  align-items: center;
}

h1{
  font-weight: bold;
  margin-bottom: 25px;
  font-size: 30px;
}


header button {
  display: inline-block;
  padding: 10px 20px;
  border: 2px solid #ccc;
  border-radius: 5px;
  background-color: #f9f9f9;
  color: #333;
  font-size: 10px;
  text-align: center;
  text-decoration: none;
  cursor: pointer;
  transition: background-color 0.3s, border-color 0.3s, color 0.3s;
}
.card {
  width: 225px;
  height: 225px;
  padding: 20px;
  border-radius: 15px;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  margin: 20px 20px 0 0;
  background-color: #f5f0e6; 
  position: relative;
}

.date{
  font-size: 13px;
  font-weight: bold;
}

.card-container{
  display: flex;
  flex-wrap: wrap;
}

.overlay {
  position: absolute;
  width: 100%;
  height: 100%;
  background-color: rgb(0,0,0,0.77);
  z-index: 10;
  display: flex;
  align-items: center;
  justify-content: center;

}

.modal{
  width: 750px;
  background-color: white;
  border-radius: 10px;
  padding: 30px;
  position: relative;
  display: flex;
  flex-direction:column;

}

.modal button{
  padding: 10px 20px;
  font-size: 20px;
  width: 100%;
  background-color: chocolate;
  border: none;
  margin-top: 15px;
}

.modal.close{
  background-color: rgba(153, 9, 9, 0.584);
  margin-top: 7px;
}

</style>