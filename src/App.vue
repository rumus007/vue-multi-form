<template>
  <!--PEN CONTENT     -->
  <div class="content">
    <!--content inner-->
    <div class="content__inner">
      <div class="container">
        <div class="multisteps-form">
          <!--progress bar-->
          <div class="row">
            <div class="col-12 col-lg-8 ml-auto mr-auto mb-4" style="position: absolute; padding: 0px 130px;">
              <div class="multisteps-form__progress">
                <button
                  class="multisteps-form__progress-btn js-active"
                  type="button"
                  title="User Info"
                >
                  User Info
                </button>
                <button
                  class="multisteps-form__progress-btn"
                  :class="{ 'js-active': stepper >= 2 }"
                  type="button"
                  title="Address"
                >
                  Address
                </button>
                <button
                  class="multisteps-form__progress-btn"
                  :class="{ 'js-active': stepper >= 3 }"
                  type="button"
                  title="Order Info"
                >
                  Order Info
                </button>
                <button
                  class="multisteps-form__progress-btn"
                  :class="{ 'js-active': stepper >= 4 }"
                  type="button"
                  title="Comments"
                >
                  Comments
                </button>
              </div>
            </div>
          </div>
          <!--form panels-->
          <div class="row" style="margin-top: 75px;">
            <div class="col-12 col-lg-8 m-auto">
              <form class="multisteps-form__form">
                <!--single form panel-->
                <div
                  class="multisteps-form__panel shadow p-4 border-round bg-white"
                  :class="{ 'js-active': stepper == 1 }"
                  data-animation="fadeIn"
                >
                  <h3 class="multisteps-form__title">Your User Info</h3>
                  <div class="multisteps-form__content">
                    <div class="form-row mt-4">
                      <div class="col-12 col-sm-6">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="First Name"
                          v-model="data.fname"
                        />
                      </div>
                      <div class="col-12 col-sm-6 mt-4 mt-sm-0">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="Last Name"
                          v-model="data.lname"
                        />
                      </div>
                    </div>
                    <div class="form-row mt-4">
                      <div class="col-12 col-sm-6">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="Username"
                          v-model="data.uname"
                        />
                      </div>
                      <div class="col-12 col-sm-6 mt-4 mt-sm-0">
                        <input
                          class="multisteps-form__input form-control"
                          type="email"
                          placeholder="Email"
                          v-model="data.email"
                        />
                      </div>
                    </div>
                    <div class="form-row mt-4">
                      <div class="col-12 col-sm-6">
                        <input
                          class="multisteps-form__input form-control"
                          type="password"
                          placeholder="Password"
                          v-model="data.password"
                        />
                      </div>
                      <div class="col-12 col-sm-6 mt-4 mt-sm-0">
                        <input
                          class="multisteps-form__input form-control"
                          type="password"
                          placeholder="Repeat Password"
                          v-model="data.repassword"
                        />
                      </div>
                    </div>
                    <div class="button-row d-flex mt-4">
                      <button
                        class="btn btn-primary ml-auto js-btn-next"
                        type="button"
                        title="Next"
                        @click="stepper++"
                      >
                        Next
                      </button>
                    </div>
                  </div>
                </div>
                <!--single form panel-->
                <div
                  class="multisteps-form__panel shadow p-4 border-round bg-white"
                  :class="{ 'js-active': stepper == 2 }"
                  data-animation="fadeIn"
                >
                  <h3 class="multisteps-form__title">Your Address</h3>
                  <div class="multisteps-form__content">
                    <div class="form-row mt-4">
                      <div class="col">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="Address 1"
                          v-model="data.address1"
                        />
                      </div>
                    </div>
                    <div class="form-row mt-4">
                      <div class="col">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="Address 2"
                          v-model="data.address2"
                        />
                      </div>
                    </div>
                    <div class="form-row mt-4">
                      <div class="col-12 col-sm-6">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="City"
                          v-model="data.city"
                        />
                      </div>
                      <div class="col-6 col-sm-3 mt-4 mt-sm-0">
                        <select class="multisteps-form__select form-control" v-model="data.state">
                          <option selected="selected">State...</option>
                          <option>...</option>
                        </select>
                      </div>
                      <div class="col-6 col-sm-3 mt-4 mt-sm-0">
                        <input
                          class="multisteps-form__input form-control"
                          type="text"
                          placeholder="Zip"
                          v-model="data.zip"
                        />
                      </div>
                    </div>
                    <div class="button-row d-flex mt-4">
                      <button
                        class="btn btn-warning js-btn-prev"
                        type="button"
                        title="Previous"
                        @click="stepper--"
                      >
                        Previous
                      </button>
                      <button
                        class="btn btn-primary ml-auto js-btn-next"
                        type="button"
                        title="Next"
                        @click="stepper++"
                      >
                        Next
                      </button>
                    </div>
                  </div>
                </div>
                <!--single form panel-->
                <div
                  class="multisteps-form__panel shadow p-4 border-round bg-white"
                  :class="{ 'js-active': stepper == 3 }"
                  data-animation="fadeIn"
                >
                  <h3 class="multisteps-form__title">Your Order Info</h3>
                  <div class="multisteps-form__content">
                    <div class="row">
                      <div class="col-12 col-md-6 mt-4">
                        <div class="card shadow-sm">
                          <div class="card-body">
                            <h5 class="card-title">Item Title</h5>
                            <p class="card-text">
                              Small and nice item description
                            </p>
                            <a
                              class="btn btn-primary"
                              href="#"
                              title="Item Link"
                              >Item Link</a
                            >
                          </div>
                        </div>
                      </div>
                      <div class="col-12 col-md-6 mt-4">
                        <div class="card shadow-sm">
                          <div class="card-body">
                            <h5 class="card-title">Item Title</h5>
                            <p class="card-text">
                              Small and nice item description
                            </p>
                            <a
                              class="btn btn-primary"
                              href="#"
                              title="Item Link"
                              >Item Link</a
                            >
                          </div>
                        </div>
                      </div>
                    </div>
                    <div class="row">
                      <div class="button-row d-flex mt-4 col-12">
                        <button
                          class="btn btn-warning js-btn-prev"
                          type="button"
                          title="Previous"
                          @click="stepper--"
                        >
                          Previous
                        </button>
                        <button
                          class="btn btn-primary ml-auto js-btn-next"
                          type="button"
                          title="Next"
                          @click="stepper++"
                        >
                          Next
                        </button>
                      </div>
                    </div>
                  </div>
                </div>
                <!--single form panel-->
                <div
                  class="multisteps-form__panel shadow p-4 border-round bg-white"
                  :class="{ 'js-active': stepper == 4 }"
                  data-animation="fadeIn"
                >
                  <h3 class="multisteps-form__title">Additional Comments</h3>
                  <div class="multisteps-form__content">
                    <div class="form-row mt-4">
                      <textarea
                        class="multisteps-form__textarea form-control"
                        placeholder="Additional Comments and Requirements"
                        v-model="data.comments"
                      ></textarea>
                    </div>
                    <div class="button-row d-flex mt-4">
                      <button
                        class="btn btn-warning js-btn-prev"
                        type="button"
                        title="Previous"
                        @click="stepper--"
                      >
                        Previous
                      </button>
                      <button
                        class="btn btn-success ml-auto"
                        type="button"
                        title="Send"
                      >
                        OK
                      </button>
                    </div>
                  </div>
                </div>
              </form>
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      stepper: 1,
      test: "",
      data: {
        email: "",
        password: "",
        repassword: "",
        fname: "",
        uname: "",
        lname: "",
        address1: "",
        address2: "",
        city: "",
        state: "",
        zip: "",
        comments: "",
      },
    };
  },
};
</script>

<style>
.content {
  width: 95%;
  margin: 0 auto 50px;
  margin-top: 40px;
}

.multisteps-form__progress {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(0, 1fr));
}

.multisteps-form__progress-btn {
  transition-property: all;
  transition-duration: 0.15s;
  transition-timing-function: linear;
  transition-delay: 0s;
  position: relative;
  padding-top: 20px;
  color: rgba(108, 117, 125, 0.7);
  text-indent: -9999px;
  border: none;
  background-color: transparent;
  outline: none !important;
  cursor: pointer;
}

@media (min-width: 500px) {
  .multisteps-form__progress-btn {
    text-indent: 0;
  }
}

.multisteps-form__progress-btn:before {
  position: absolute;
  top: 0;
  left: 50%;
  display: block;
  width: 13px;
  height: 13px;
  content: "";
  -webkit-transform: translateX(-50%);
  transform: translateX(-50%);
  transition: all 0.15s linear 0s,
    -webkit-transform 0.15s cubic-bezier(0.05, 1.09, 0.16, 1.4) 0s;
  transition: all 0.15s linear 0s,
    transform 0.15s cubic-bezier(0.05, 1.09, 0.16, 1.4) 0s;
  transition: all 0.15s linear 0s,
    transform 0.15s cubic-bezier(0.05, 1.09, 0.16, 1.4) 0s,
    -webkit-transform 0.15s cubic-bezier(0.05, 1.09, 0.16, 1.4) 0s;
  border: 2px solid currentColor;
  border-radius: 50%;
  background-color: #fff;
  box-sizing: border-box;
  z-index: 3;
}

.multisteps-form__progress-btn:after {
  position: absolute;
  top: 5px;
  left: calc(-50% - 13px / 2);
  transition-property: all;
  transition-duration: 0.15s;
  transition-timing-function: linear;
  transition-delay: 0s;
  display: block;
  width: 100%;
  height: 2px;
  content: "";
  background-color: currentColor;
  z-index: 1;
}

.multisteps-form__progress-btn:first-child:after {
  display: none;
}

.multisteps-form__progress-btn.js-active {
  color: #007bff;
}

.multisteps-form__progress-btn.js-active:before {
  -webkit-transform: translateX(-50%) scale(1.2);
  transform: translateX(-50%) scale(1.2);
  background-color: currentColor;
}

.multisteps-form__form {
  position: relative;
}

.multisteps-form__panel {
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 0;
  opacity: 0;
  visibility: hidden;
}

.border-round{
  border-radius: 20px;
}

.js-btn-prev {
  margin-right: 15px;
}

.multisteps-form__panel.js-active {
  height: auto;
  opacity: 1;
  visibility: visible;
}

.multisteps-form__panel[data-animation="fadeIn"] {
  -webkit-transform: scale(0.9);
  transform: scale(0.9);
}

.multisteps-form__panel[data-animation="fadeIn"].js-active {
  transition-property: all;
  transition-duration: 0.2s;
  transition-timing-function: linear;
  transition-delay: 0s;
  -webkit-transform: scale(1);
  transform: scale(1);
}
</style>
