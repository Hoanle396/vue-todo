<template>
  <div class="units">
    <h1>This is an Units page</h1>
    <div class="container">
      <table class="table mt-3">
      <thead>
        <tr>
          <th scope="col">CODE</th>
          <th scope="col">DESCRIPTION</th>
          <th scope="col">CP</th>
          <th scope="col">TYPE</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="(unit,index) in units" :key="index">
          <th scope="row">{{unit.code}}</th>
          <td>{{unit.desc}}</td>
          <td>{{unit.cp}}</td>
          <td>{{unit.type}}</td>
        </tr>
        
      </tbody>
    </table>
    </div>
  </div>
</template>
<script>
import units from "../assets/units.json";
export default {
  data() {
    return {
      units: units,
    };
  },
  mounted() {
    console.log(this.units);
  },
};
</script>