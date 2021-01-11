<template>
  <div class="container">
    <form class="row g-3" enctype="multipart/form-data">
      <!-- First part of form -->
      <div v-if="stepper == 1">
        <h1>First part</h1>
        <div class="col-md-6">
          <label for="inputEmail" class="form-label">Email</label>
          <input
            type="email"
            class="form-control"
            id="inputEmail"
            v-model="data.email"
          />
        </div>
        <div class="col-md-6">
          <label for="inputPassword" class="form-label">Password</label>
          <input
            type="password"
            class="form-control"
            id="inputPassword"
            v-model="data.password"
          />
        </div>
        <div class="col-6">
          <label for="inputFirstname" class="form-label">First name</label>
          <input
            type="text"
            class="form-control"
            id="inputFirstname"
            v-model="data.fname"
          />
        </div>
        <div class="col-6">
          <label for="inputLastName" class="form-label">Last name</label>
          <input
            type="text"
            class="form-control"
            id="inputLastName"
            v-model="data.lname"
          />
        </div>
      </div>
      <!-- Second part of form -->
      <div v-else>
        <h1>Second part</h1>
        <div class="col-6">
          <label for="Address" class="form-label">Address</label>
          <input
            type="text"
            class="form-control"
            id="Address"
            v-model="data.address"
          />
        </div>
        <div class="col-md-6">
          <label for="inputCity" class="form-label">City</label>
          <input
            type="text"
            class="form-control"
            id="inputCity"
            v-model="data.city"
          />
        </div>
        <div class="col-md-6">
          <label for="inputState" class="form-label">State</label>
          <select id="inputState" class="form-select" v-model="data.state">
            <option selected>Choose...</option>
            <option>...</option>
          </select>
        </div>
        <div class="col-md-6">
          <label for="inputZip" class="form-label">Zip</label>
          <input
            type="text"
            class="form-control"
            id="inputZip"
            v-model="data.zip"
          />
        </div>
        <div class="col-12">
          <div class="form-check">
            <input
              class="form-check-input"
              type="checkbox"
              id="gridCheck"
              v-model="data.checkout"
            />
            <label class="form-check-label" for="gridCheck">
              Check me out
            </label>
          </div>
        </div>
      </div>

      <div class="d-grid gap-2 d-md-flex">
        <button type="button" class="btn btn-primary" @click="stepperAction()">
          {{ buttonText }}
        </button>
        <button type="button" class="btn btn-success" :disabled="stepper == 1">
          Save
        </button>
      </div>
    </form>
    <br>
    <pre id="json">
      {{ prettyJson }}
    </pre>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      stepper: 1,
      data: {
        email: "",
        password: "",
        fname: "",
        lname: "",
        address: "",
        city: "",
        state: "",
        zip: "",
        checkout: null,
      },
    };
  },
  methods: {
    stepperAction() {
      this.stepper == 1 ? this.stepper++ : this.stepper--;
    }
  },
  computed: {
    buttonText() {
      return this.stepper == 1 ? "Next" : "Back";
    },
    prettyJson(){
      return JSON.stringify(this.data, undefined, 2)
    }
  },
};
</script>

<style>
</style>
