<script setup>
import HelloWorld from './components/HelloWorld.vue'
const tasks=[
  {id:1,title:"Gather related data",status:"Completed"},
  {id:2,title:"Update website content",status:"In Progress"},
  {id:3,title:"Fix bug in user authentication",status:"Pending"},
  {id:4,title:"Prepare presentation slides",status:"Completed"},
  {id:5,title:"test new feature implementation",status:"In Progress"},
  {id:6,title:"complete project task",status:"In Progress"},
  
];
 function getCompletedTask(){
return tasks.filter(task=>"In Progress"==task.status)
}
 function getPendingTask(){
return tasks.filter(task=>"Pending"==task.status)
}
 function getInProgressTask(){
return tasks.filter(task=>"Completed"==task.status)
}

// const filters = ["all", "category-a", "category-b", "category-c"];
//         let currentFilterIndex = 0;

//         const button = document.getElementById("filterBtn");
//         const items = document.querySelectorAll(".item");

//         button.addEventListener("click", () => {
//             currentFilterIndex = (currentFilterIndex + 1) % filters.length;
//             const filter = filters[currentFilterIndex];

//             button.textContent = `Apply Filter: ${filter === "all" ? "All" : filter}`;

//             items.forEach(item => {
//                 if (filter === "all") {
//                     item.classList.remove("hidden");
//                 } else {
//                     item.classList.toggle("hidden", !item.classList.contains(filter));
//                 }
//             });
//         });
</script>

<template>

  
  <section>
    <h1 style="border: 5px solid aquamarine; border-radius: 10px; background-color: aquamarine; padding: 10px; margin-top: 5px;">All the Task details</h1>
    <hr>  
  <section>
    
    <button>Task In Progress</button>
    <div style="border: 3px solid green;border-radius: 10px; background-color: yellow; padding: 10px; margin-top: 8px;" v-for="(task,index) in getInProgressTask()" v-bind:key="task.id">
       {{task.id}}. {{ task.title }}
    </div>
    <button>Task Completed</button>
    <div  style="border: 3px solid yellowgreen;border-radius: 10px; padding: 10px; margin-top: 8px; background-color: yellowgreen;" v-for="(task,index) in getCompletedTask()" v-bind:key="task.id">
      {{task.id}}. {{ task.title }}
    </div>
    <button> Task Pending</button>
    <div style="border: 3px solid deeppink;border-radius: 10px; background-color: deeppink; padding: 10px; margin-top: 8px;" v-for="(task,index) in getPendingTask()" v-bind:key="task.id">
       {{task.id}}. {{ task.title }}
    </div>


  

  </section>
 </section>
</template>

<style scoped>
.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.vue:hover {
  filter: drop-shadow(0 0 2em #42b883aa);
}

/* new styles */
/* .item { display: block; } 
.hidden { display: none; } */
</style>
