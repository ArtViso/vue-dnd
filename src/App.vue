<template>
  <div id="app">
    <div class="flex justify-center items-center mt-10">
      <img src="../src/assets/logo.png" style="width: 50px; height: 50px" alt="logo">
      <p class="text-lg">Task Board</p>
    </div>
    <div class="flex justify-center">
      <div class="min-h-screen flex">
        <board
            v-for="column in columns"
            :key="column.title"
            :title="column.title"
            :task-length="column.tasks.length"
        >
          <draggable :list="column.tasks" :animation="200" ghost-class="ghost-card" group="tasks">
            <Card
                v-for="task in column.tasks"
                :key="task.id"
                :task="task"
                :color="colorBoard(column.title)"
                class="mt-3 cursor-move"
            ></Card>
          </draggable>
        </board>
      </div>
    </div>
  </div>
</template>

<script>
import draggable from "vuedraggable";
import Card from "@/components/Card";
import Board from "@/components/Board";

export default {
  name: "App",
  components: {
    Card,
    Board,
    draggable
  },
  data() {
    return {
      columns: [
        {
          title: "Backlog",
          tasks: [
            {
              id: 1,
              avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-Profile-Vector-PNG-Clipart.png',
              nickname: 'John',
              email:'john@gmail.com',
              title: "nisl condimentum id venenatis a condimentum vitae sapien",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Low Priority'
            },
            {
              id: 2,
              avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-Profile-Vector-PNG-Images.png',
              nickname: 'Lucy',
              email:'lucy@gmail.com',
              title: "sit amet tellus cras adipiscing enim eu turpis egestas pretium",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Med Priority'
            },
            {
              id: 3,
              avatar: 'https://cdn-icons-png.flaticon.com/512/147/147142.png',
              nickname: 'Jack',
              email:'jack@gmail.com',
              title: "tincidunt praesent semper feugiat nibh sed pulvinar proin gravida",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
            {
              id: 4,
              avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXfr8scs2y4myxy0TuXFJTmJJVHDP71UUtc5oOKUAaECdyBbV02BsgkNhcyXWATXsw9z4&usqp=CAU',
              nickname: 'Scarlett',
              email: 'scarlett@gamil.com',
              title: "sit amet tellus cras adipiscing enim eu turpis egestas pretium",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
            {
              id: 5,
              avatar: 'https://cdn.icon-icons.com/icons2/2643/PNG/512/male_boy_person_people_avatar_icon_159358.png',
              nickname: 'Robert',
              email: 'robert@gmail.com',
              title: "sagittis eu volutpat odio facilisis mauris sit amet massa vitae",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Med Priority',
            }
          ]
        },
        {
          title: "In Progress",
          tasks: [
            {
              id: 6,
              avatar: 'https://cdn.icon-icons.com/icons2/2643/PNG/512/male_boy_person_people_avatar_icon_159358.png',
              nickname: 'Robert',
              email: 'robert@gmail.com',
              title: "mattis rhoncus urna neque viverra justo nec ultrices dui sapien",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Med Priority',
            },
            {
              id: 7,
              avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-Profile-Vector-PNG-Clipart.png',
              nickname: 'John',
              email:'john@gmail.com',
              title: "habitant morbi tristique senectus et netus et malesuada fames ac",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Low Priority'
            },
            {
              id: 8,
              avatar: 'https://cdn-icons-png.flaticon.com/512/147/147142.png',
              nickname: 'Jack',
              email:'jack@gmail.com',
              title: "morbi quis commodo odio aenean sed adipiscing diam donec adipiscing",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
            {
              id: 9,
              avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXfr8scs2y4myxy0TuXFJTmJJVHDP71UUtc5oOKUAaECdyBbV02BsgkNhcyXWATXsw9z4&usqp=CAU',
              nickname: 'Scarlett',
              email: 'scarlett@gamil.com',
              title: "enim lobortis scelerisque fermentum dui faucibus in ornare quam viverra",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            }
          ]
        },
        {
          title: "Review",
          tasks: [
            {
              id: 10,
              avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXfr8scs2y4myxy0TuXFJTmJJVHDP71UUtc5oOKUAaECdyBbV02BsgkNhcyXWATXsw9z4&usqp=CAU',
              nickname: 'Scarlett',
              email: 'scarlett@gamil.com',
              title: "diam sit amet nisl suscipit adipiscing bibendum est ultricies integer",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
            {
              id: 11,
              avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-Profile-Vector-PNG-Clipart.png',
              nickname: 'John',
              email:'john@gmail.com',
              title: "nam libero justo laoreet sit amet cursus sit amet dictum",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Low Priority'
            },
            {
              id: 12,
              avatar: 'https://cdn-icons-png.flaticon.com/512/147/147142.png',
              nickname: 'Jack',
              email:'jack@gmail.com',
              title: "malesuada nunc vel risus commodo viverra maecenas accumsan lacus vel",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
          ]
        },
        {
          title: "Done",
          tasks: [
            {
              id: 13,
              avatar: 'https://www.pngall.com/wp-content/uploads/12/Avatar-Profile-Vector-PNG-Images.png',
              nickname: 'Lucy',
              email:'lucy@gmail.com',
              title: "id aliquet lectus proin nibh nisl condimentum id venenatis a",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'Med Priority'
            },
            {
              id: 14,
              avatar: 'https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTXfr8scs2y4myxy0TuXFJTmJJVHDP71UUtc5oOKUAaECdyBbV02BsgkNhcyXWATXsw9z4&usqp=CAU',
              nickname: 'Scarlett',
              email: 'scarlett@gamil.com',
              title: "et leo duis ut diam quam nulla porttitor massa id",
              date: new Date().toLocaleDateString('en-US', {year: 'numeric', month: '2-digit', day: '2-digit'}),
              status: 'High Priority'
            },
          ]
        }
      ]
    };
  },
  methods: {
    colorBoard(column) {
      const colorBoard = {
        'Backlog': "grey",
        'In Progress': "blue",
        'Review': 'orange',
        'Done': "green",
      };
      return colorBoard[column];
    }
  }
};
</script>

<style scoped>
.column-width {
  min-width: 320px;
  width: 320px;
}

.ghost-card {
  opacity: 0.5;
  background: #F7FAFC;
  border: 1px solid #4299e1;
}
</style>
