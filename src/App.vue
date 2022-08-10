<template>
  <div id="app">
    <header>
      <img src="../src/assets/logo.png" style="width: 50px; height: 50px" alt="logo">
      <h1>Task Board</h1>
    </header>
    <main class="flexbox">
      <div class="board">
        <div class="board-title">
          <h1>ToDo</h1>
        </div>
        <Board id="board-1">
          <Card id="card-1" draggable="true">
            <p>Card one</p>
          </Card>
          <Card id="card-2" draggable="true">
            <p>Card two</p>
          </Card>
          <Card id="card-3" draggable="true">
            <p>Card tree</p>
          </Card>
          <Card id="card-4" draggable="true">
            <p>Card four</p>
          </Card>
        </Board>
      </div>
      <div class="board">
        <div class="board-title">
          <h1>In Development</h1>
        </div>
        <Board id="board-2">
          <Card id="card-5" draggable="true">
            <p>Card five</p>
          </Card>
        </Board>
      </div>
      <div class="board">
        <div class="board-title">
          <h1>Task Completed</h1>
        </div>
        <Board id="board-3">
          <Card id="card-6" draggable="true">
            <p>Card six</p>
          </Card>
        </Board>
      </div>
    </main>
  </div>
</template>

<script>
import Board from "@/components/Board";
import Card from "@/components/Card";

export default {
  name: 'App',
  components: {
    Board,
    Card
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  text-align: center;
  color: #2c3e50;
}

* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

header {
  margin: 70px 0 10px 0;
}

.flexbox {
  display: flex;
  justify-content: space-around;
  width: 100%;
  max-width: 950px;
  height: 70vh;
  outline: hidden;
  margin: 0 auto;
  padding: 10px;
}

.flexbox .board {
  display: flex;
  flex-direction: column;
  width: 100%;
  height: 100%;
  max-width: 300px;
  border: 1px solid black;
}

.flexbox .board .card {
  padding: 15px 25px;
  border: 1px solid silver;
  cursor: pointer;
  margin: 20px;
  transition: 1s;
}

.card:hover {
  background: #35495E;
  color: white;
}

.board-title {
  background: #35495E;
  color: white;
  padding: 15px;
}
</style>
