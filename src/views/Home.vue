<template>
  <div class="home d-flex justify-content-center">
    <div class="col-md-3">
      <div class="row">
        <div class="h3">Welcome {{ firstname + " " + lastname }} !</div>
      </div>
      <div class="row">
        <div class="col-4">
          <h5 for="firstname">First name</h5>
        </div>
        <div class="col-8">
          <input
            type="text"
            v-model="firstname"
            placeholder="First name"
            id="firstname"
            class="form-control"
          />
        </div>
      </div>
      <div class="row mt-3">
        <div class="col-4">
          <h5 for="lastname">Last name</h5>
        </div>
        <div class="col-8">
          <input
            type="text"
            v-model="lastname"
            placeholder="Last name"
            id="lastname"
            class="form-control"
          />
        </div>
      </div>
      <div class="row mt-3 ">
        <div class="col-6">
          <input type="radio" id="one" value="0" v-model="picked" />
          <label for="one">One</label>
        </div>
        <div class="col-6">
          <input type="radio" id="two" value="1" v-model="picked" />
          <label for="two">Two</label>
        </div>
      </div>
      <div class="row">
        <img alt="Img"  class="img-fluid"  :src="images[picked]" />
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
export default {
  data() {
    return {
      firstname: "",
      lastname: "",
      picked: 0,
      images: [
        "https://picsum.photos/id/102/1200",
        "https://picsum.photos/id/132/1200",
      ],
    };
  },
};
</script>
<style scoped>
.img-fluid{
  height: 200px !important;
  object-fit: cover;
}
</style>