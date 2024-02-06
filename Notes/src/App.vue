<template>

<main> 
  
  <div class ="container"> 
    <header>
      <h1> Notes </h1>
      <button>+</button>
    </header>

    <div class="card-container">
      <div class="card">
        <p class = "main-text"> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quisquam dolorum officia corporis aspernatur. Libero sed ut quidem voluptatem ex id cupiditate doloremque! Atque voluptates fuga necessitatibus nobis saepe modi iste!</p>
        <p class="date"> 02/05/2024</p>
      </div>

      <div class="card">
        <p class = "main-text"> Lorem ipsum dolor sit amet, consectetur adipisicing elit. Quisquam dolorum officia corporis aspernatur. Libero sed ut quidem voluptatem ex id cupiditate doloremque! Atque voluptates fuga necessitatibus nobis saepe modi iste!</p>
        <p class="date"> 02/05/2024</p>
    
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


button {
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


</style>