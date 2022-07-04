<template>
  <div class="tasks d-flex justify-content-center">
    <div class="col-md-3">
      <h1>This is an Tasks page</h1>
      <div class="row mt-3">
        <div class="col-4">
          <h5 >Tasks name</h5>
        </div>
        <div class="col-8 mb-3">
          <form @submit.prevent="addTasks" class="d-flex">
            <input
            type="text"
            v-model="tasks"
            placeholder="Task name"
            id="tasks"
            class="form-control"
          />
          <input type="submit" value="add" class="btn btn-primary mx-3">
          </form>
        </div>
        <p class="text-center "
               v-for="(myTask, index) in myTasks"
               v-bind:key="myTask.id">
               {{myTask.msg}}
               <button class="btn btn-sm btn-danger" v-on:click="myTasks.splice(index,1)">Del</button>
            </p>

      </div>
    </div>
  </div>
</template>
<script>
export default {
  data() {
    return {
      tasks:"",
      myTasks:[
        {
          id:1,
          msg:"Vue Js"
        },
        {
          id:2,
          msg:"Nuxt JS"
        }
      ],
      nextTasks:3
    }
  },
  methods:{
    addTasks:function(){
      this.myTasks.push({
        id:this.nextTasks++,
        msg:this.tasks
      })
      this.tasks="";
    }
  }
}
</script>
